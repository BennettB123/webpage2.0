<script context="module" lang="ts">
  import MandelbrotSetImg1 from "../assets/projectImgs/Mandelbrot-set1.jpg";
  import MandelbrotSetImg2 from "../assets/projectImgs/Mandelbrot-set2.png";
  import passwordVaultImg from "../assets/projectImgs/Password-vault.png";
  import pythonMazeImg from "../assets/projectImgs/pythonMaze.png";
  import slidePuzzleImg1 from "../assets/projectImgs/slidePuzzle1.png";
  import slidePuzzleImg2 from "../assets/projectImgs/slidePuzzle2.png";
  import stickyNoteBoardImg from "../assets/projectImgs/StickyNoteBoard.jpg";
  import stockMarketReturnsImg from "../assets/projectImgs/stockMarketReturns.png";
  import universeExplorerGif from "../assets/projectImgs/universeExplorer.gif";

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
      images: [
        MandelbrotSetImg1,
        MandelbrotSetImg2,
      ],
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
      images: [
        slidePuzzleImg1,
        slidePuzzleImg2,
      ],
      githubLink: "https://github.com/BennettB123/Slide-Puzzle",
      techUsed: ["C++", "Curses Library"],
    },
  ];
</script>
