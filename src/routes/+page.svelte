<script lang="ts">
  import { onMount } from 'svelte';
  import { goto } from '$app/navigation';
  onMount(() => goto('/about-me'));
</script>

<p>Redirecting to About Me...</p>
