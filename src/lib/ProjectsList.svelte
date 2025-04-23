<script context="module" lang="ts">
  import TodoImg from "../assets/projectImgs/Todo.png";
  import Arduboy2DMinigolfGif from "../assets/projectImgs/Arduboy-2DMinigolf.gif";
  import ArduboyGoFetchGif from "../assets/projectImgs/Arduboy-GoFetch.gif";
  import freshImg from "../assets/projectImgs/Fresh.png";
  import rayCastingDemoImg from "../assets/projectImgs/Raycasting-demo.png";
  import stickyNoteBoardImg from "../assets/projectImgs/StickyNoteBoard.jpg";
  import passwordVaultImg from "../assets/projectImgs/Password-vault.png";
  import MandelbrotSetImg1 from "../assets/projectImgs/Mandelbrot-set1.jpg";
  import MandelbrotSetImg2 from "../assets/projectImgs/Mandelbrot-set2.png";
  import universeExplorerGif from "../assets/projectImgs/universeExplorer.gif";
  import stockMarketReturnsImg from "../assets/projectImgs/stockMarketReturns.png";
  import pythonMazeImg from "../assets/projectImgs/pythonMaze.png";
  import slidePuzzleImg1 from "../assets/projectImgs/slidePuzzle1.png";
  import slidePuzzleImg2 from "../assets/projectImgs/slidePuzzle2.png";

  type Project = {
    name: string;
    description: string;
    year: number;
    images: string[];
    githubLink: string;
    demoLink?: string;
    techUsed: string[];
    notes?: string;
  };

  export const projectList: Project[] = [
    {
      name: "todo",
      description: "A simple command-line TODO list manager written with Go. " +
        "The program allows you to add, remove, complete, un-complete, archive, and delete tasks from anywhere in your terminal using an easy syntax. " +
        "Tasks are persisted in a SQLite3 database at '<code>%Home%/.todo/data.sqlite3</code>'.",
      year: 2025,
      images: [TodoImg],
      githubLink: "https://github.com/BennettB123/todo/",
      demoLink: "",
      techUsed: ["Go"],
      notes: "",
    },
    {
      name: "Arduboy - 2D Minigolf",
      description:
        'A 2D minigolf game for the <a href="https://arduboy.com" target="_blank">Arduboy FX</a>, an open-source, 8-bit game system. ' +
        "The game features (semi)realistic physics, a variety of obstacle types, and currently 9 maps. " +
        "Play through all the maps in order, or select any map to play individually.",
      year: 2025,
      images: [Arduboy2DMinigolfGif],
      githubLink: "https://github.com/BennettB123/Arduboy-2DMiniGolf",
      demoLink: "https://community.arduboy.com/t/2d-minigolf/12604",
      techUsed: ["C++"],
      notes: "",
    },
    {
      name: "Arduboy - Go Fetch",
      description:
        'Go Fetch is a simple game for the <a href="https://arduboy.com" target="_blank">Arduboy</a>, an open-source, 8-bit game system. ' +
        "The premise of the game is to collect balls while avoiding squirrels. " +
        "You also have the ability to bark the squirrels away if you get into a bad situation.",
      year: 2024,
      images: [ArduboyGoFetchGif],
      githubLink: "https://github.com/BennettB123/Arduboy-GoFetch",
      demoLink:
        "https://community.arduboy.com/t/go-fetch-a-game-about-dogs-balls-and-squirrels/12377",
      techUsed: ["C++"],
      notes: "",
    },
    {
      name: "Fresh",
      description:
        "Fresh is a dotnet library that makes it easy to customize console output utilizing common ANSI Escape Sequences (colors, bold, underline, etc). It also allows you to wrap text with borders. The package supports a fluent API with method-chaining",
      year: 2024,
      images: [freshImg],
      githubLink: "https://github.com/BennettB123/Fresh",
      demoLink: "",
      techUsed: [".NET", "C#"],
      notes: "",
    },
    {
      name: "simplehttp",
      description:
        "A bare-bones HTTP/1.0 web framework for Go. " +
        "The framework allows you to setup handlers for GET, POST, PUT, and DELETE requests made to specific URL paths. " +
        "It also provides helpful methods to respond to requests with JSON, HTML, or files. " +
        'The package is fully documented in Go\'s official package site, <a href="https://pkg.go.dev/github.com/BennettB123/simplehttp" target="_blank">https://pkg.go.dev/github.com/BennettB123/simplehttp</a>.',
      year: 2024,
      images: [],
      githubLink: "https://github.com/BennettB123/simplehttp",
      demoLink: "",
      techUsed: ["Go"],
      notes:
        "This package probably should not be used in a production environment. It was purely created as a learning opportunity to gain experience with Go.",
    },
    {
      name: "Raycasting Demo",
      description:
        'My attempt at a basic FPS-style game demo using <a href="https://en.wikipedia.org/wiki/Ray_casting" target="_blank">ray-casting</a>. ' +
        'Written completely in rust using the <a href="https://github.com/not-fl3/macroquad" target="_blank">macroquad</a> game library. ' +
        'The game supports player movement around a 2D map. Walk around using the "WASD" keys and look around using the left and right arrow keys.',
      year: 2023,
      images: [rayCastingDemoImg],
      githubLink: "https://github.com/BennettB123/raycasting-game-demo",
      demoLink: "",
      techUsed: ["Rust"],
      notes: "",
    },
    {
      name: "Sticky Note Board",
      description:
        "This is a web app to create sticky notes in your browser. I use this app every day at work to keep track of my todo list and any other quick notes I need to remember. " +
        "The notes can be edited, moved around the board, resized, and colored. The notes even support basic MarkDown syntax so they can be styled however you want.",
      year: 2022,
      images: [stickyNoteBoardImg],
      githubLink: "https://github.com/BennettB123/sticky-note-board",
      demoLink: "https://dbballentine.com/sticky-notes/",
      techUsed: ["React", "Javascript", "HTML", "CSS"],
    },
    {
      name: "Password Vault",
      description:
        "In school, I took a Cybersecurity class that required me to develop a program related to computer security. I decided to create a command-line based password manager. This program " +
        "allows you to store username/password combinations that are encrypted with your master password. You can also use it to generate secure passwords. The Crypto algorithms used are " +
        "SHA-256 and salted PBKDF2 key derivation.",
      year: 2021,
      images: [passwordVaultImg],
      githubLink: "https://github.com/BennettB123/password-vault",
      techUsed: ["Python"],
      notes:
        "Use this program at your own discretion! I developed it strictly as a research project and it has not been evaluated or tested by any Cybersecurity experts.",
    },

    {
      name: "Mandelbrot Set Viewer",
      description:
        "Ever since I learned about the Mandelbrot Set I have been amazed by its elaborate and infinite complexity. I created this web application to explore " +
        "the Mandelbrot Set in a browser. You can zoom into any part of the image by click+dragging to form a new view. The controls at the bottom of the page can be used to " +
        "change the image quality, redo your last zoom, or reset the entire view.",
      year: 2020,
      images: [MandelbrotSetImg1, MandelbrotSetImg2],
      githubLink: "https://github.com/BennettB123/Mandelbrot-Set",
      demoLink: "https://dbballentine.com/mandelbrot/",
      techUsed: ["Javascript", "HTML", "CSS"],
    },

    {
      name: "Infinite Universe Explorer",
      description:
        "This is a javascript application to navigate around a procedurally generated 'Universe'. Left & right arrows rotate the ship, " +
        "while the spacebar activates the thrusters. Use the mouse scroll-wheel to zoom in and out. I had many more plans for this project but lost interest in it :(",
      year: 2020,
      images: [universeExplorerGif],
      githubLink: "https://github.com/BennettB123/Universe-Explorer",
      demoLink: "https://bennettb123.github.io/Universe-Explorer/",
      techUsed: ["Python", "Curses Library"],
      notes:
        "The only controls that have been implemented for mobile devices is zooming in & out. This can be done by pinching with 2 fingers",
    },

    {
      name: "Stock Market Returns Calculator",
      description:
        "This is a command-line application, written in Go, that calculates and displays your returns from the stock market. " +
        "Enter your stock information in a JSON file, and the application will use a market data API (Tiingo) to pull current stock prices " +
        "and calculate how much you have earned or lossed",
      year: 2020,
      images: [stockMarketReturnsImg],
      githubLink: "https://github.com/BennettB123/StockMarketReturnsCalculator",
      techUsed: ["Go"],
    },

    {
      name: "Maze Generator",
      description:
        "Navigate a randomly generated maze in your terminal! This is a Python script that uses a depth-first search algorithm to " +
        "create a maze within your terminal. Use arrow keys to move the smiley face to the end of the maze",
      year: 2019,
      images: [pythonMazeImg],
      githubLink: "https://github.com/BennettB123/Python-Maze-Generator",
      techUsed: ["Python", "Curses Library"],
    },

    {
      name: "15 Puzzle",
      description:
        "Play with a 15-puzzle in your terminal! This was one of the first programs I created outside of my school work. It allows you to select the width and height of your puzzle (2 through 10 for each) and use " +
        "the arrow keys to 'slide' the pieces around to get them in order",
      year: 2018,
      images: [slidePuzzleImg1, slidePuzzleImg2],
      githubLink: "https://github.com/BennettB123/Slide-Puzzle",
      techUsed: ["C++", "Curses Library"],
    },
  ];
</script>
