<script lang="ts">
  import { onMount } from "svelte";
  import { renderMarkdown } from "../lib/markdown";

  type BlogEntry = {
    slug: string;
    title: string;
    date: string;
    excerpt: string;
    file: string;
  };

  let entries: BlogEntry[] = [];
  let selectedEntry: BlogEntry | undefined;
  let renderedPost = "";
  let loading = true;
  let errorMessage = "";

  function getSelectedSlug() {
    const match = window.location.pathname.match(/^\/blog\/([^/]+)/);
    return match?.[1] ? decodeURIComponent(match[1]) : "";
  }

  async function loadBlog() {
    loading = true;
    errorMessage = "";

    try {
      const manifestResponse = await fetch("/blog-content/manifest.json", { cache: "no-cache" });

      if (!manifestResponse.ok) {
        throw new Error("Could not load the blog manifest.");
      }

      const manifestEntries: BlogEntry[] = await manifestResponse.json();
      entries = manifestEntries.sort(
        (left, right) => Date.parse(right.date) - Date.parse(left.date),
      );
      const selectedSlug = getSelectedSlug();
      selectedEntry = selectedSlug ? entries.find((entry) => entry.slug === selectedSlug) : undefined;

      if (selectedSlug && !selectedEntry) {
        errorMessage = "That blog entry could not be found.";
      }

      if (selectedEntry) {
        const postResponse = await fetch(selectedEntry.file, { cache: "no-cache" });

        if (!postResponse.ok) {
          throw new Error("Could not load the selected blog entry.");
        }

        renderedPost = renderMarkdown(await postResponse.text());
      } else {
        renderedPost = "";
      }
    } catch (error) {
      errorMessage = error instanceof Error ? error.message : "Something went wrong loading the blog.";
      entries = [];
      selectedEntry = undefined;
      renderedPost = "";
    } finally {
      loading = false;
    }
  }

  function openEntry(event: MouseEvent, entry: BlogEntry) {
    event.preventDefault();
    window.history.pushState({}, "", `/blog/${entry.slug}`);
    window.dispatchEvent(new CustomEvent("routechange"));
    loadBlog();
  }

  function openBlogIndex(event: MouseEvent) {
    event.preventDefault();
    window.history.pushState({}, "", "/blog");
    window.dispatchEvent(new CustomEvent("routechange"));
    loadBlog();
  }

  onMount(() => {
    loadBlog();
    window.addEventListener("popstate", loadBlog);

    return () => {
      window.removeEventListener("popstate", loadBlog);
    };
  });
</script>

<main>
  <h1>Bennett's Blog</h1>

  {#if loading}
    <p class="status">Loading posts...</p>
  {:else if errorMessage}
    <p class="status error">{errorMessage}</p>
    {#if entries.length > 0}
      <a href="/blog" class="back-link" on:click={openBlogIndex}>Back to all posts</a>
    {/if}
  {:else if selectedEntry}
    <article class="post">
      <a href="/blog" class="back-link" on:click={openBlogIndex}>Back to all posts</a>
      <p class="post-date">{selectedEntry.date}</p>
      {@html renderedPost}
    </article>
  {:else}
    <div class="post-list">
      {#each entries as entry (entry.slug)}
        <a
          class="post-card-link"
          href={`/blog/${entry.slug}`}
          on:click={(event) => openEntry(event, entry)}
        >
          <article class="post-card">
            <div class="post-card-content">
              <p class="post-date">{entry.date}</p>
              <h2>{entry.title}</h2>
              <p>{entry.excerpt}</p>
            </div>
          </article>
        </a>
      {/each}
    </div>
  {/if}
</main>

<style>
  main {
    max-width: 900px;
    margin: 0 auto;
    text-align: left;
  }

  h1 {
    text-align: center;
  }

  .status {
    max-width: 620px;
    margin: 0 auto 2rem;
    font-size: 1.15rem;
    text-align: center;
  }

  .error {
    color: #ff8a65;
  }

  .post-list {
    display: grid;
    gap: 0.85rem;
  }

  .post-card-link {
    color: inherit;
    text-decoration: none;
    border-radius: 8px;
  }

  .post-card-link:focus-visible {
    outline: 2px solid #ff7e3e;
    outline-offset: 4px;
  }

  .post-card {
    overflow: hidden;
    border: 1px solid #444;
    border-radius: 8px;
    background: #2d2d2d;
    transition:
      transform 0.2s ease,
      box-shadow 0.2s ease,
      border-color 0.2s ease;
  }

  .post-card-link:hover .post-card,
  .post-card-link:focus-visible .post-card {
    transform: scale(1.03);
    box-shadow: 0 6px 15px rgba(0, 0, 0, 0.4);
    border-color: #ff3e00;
  }

  .post-card-content {
    padding: 0.8rem 1rem;
  }

  .post-card h2 {
    margin: 0.1rem 0 0.4rem;
    font-size: 1.5rem;
    line-height: 1.2;
    color: #ff7e3e;
  }

  .post-card p:last-child {
    margin: 0;
  }

  .back-link,
  :global(.post a) {
    color: #ff7e3e;
    text-decoration: none;
  }

  .back-link:hover,
  :global(.post a:hover) {
    color: #ffab86;
  }

  .post-date {
    color: #b8b8b8;
    font-size: 1.3rem;
    margin: 0;
  }

  .back-link {
    display: inline-block;
    margin-bottom: 1.5rem;
    font-weight: 700;
  }

  .post {
    max-width: 760px;
    margin: 0 auto;
    font-size: 1.08rem;
    line-height: 1.75;
  }

  :global(.post h1),
  :global(.post h2),
  :global(.post h3) {
    color: #fff;
    line-height: 1.2;
    margin-top: 1.6rem;
    margin-bottom: 0.65rem;
  }

  :global(.post h1) {
    text-align: left;
    margin-top: 0.25rem;
  }

  :global(.post img) {
    display: block;
    max-width: 100%;
    height: auto;
    margin: 1.25rem auto;
    border-radius: 8px;
    border: 1px solid #444;
  }

  :global(.post blockquote) {
    margin: 1.25rem 0;
    padding: 0.25rem 0 0.25rem 1rem;
    border-left: 4px solid #ff3e00;
    color: #ddd;
    background: #2b2b2b;
  }

  :global(.post pre) {
    overflow-x: auto;
    padding: 1rem;
    border-radius: 8px;
    background: #171717;
    border: 1px solid #3d3d3d;
  }

  :global(.post code) {
    padding: 0.1rem 0.3rem;
    border-radius: 4px;
    background: #171717;
    color: #ffd0bf;
  }

  :global(.post pre code) {
    padding: 0;
    background: transparent;
  }

  :global(.post table) {
    width: 100%;
    border-collapse: collapse;
    margin: 1.25rem 0;
  }

  :global(.post th),
  :global(.post td) {
    padding: 0.65rem;
    border: 1px solid #4d4100;
  }

  :global(.post th) {
    background: #333;
    color: #fff;
  }
</style>
