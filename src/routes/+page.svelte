<script>
  const projects = [
    {
      name: "Boicchi",
      link: "https://discord.com/oauth2/authorize?client_id=1341807220500729969",
      desc: "is a bot discord where you can download video from many platform like youtube, twitter and more! (made with bun!!)",
    },
    {
      name: "Capybara",
      link: "https://github.com/39choko/Capybara",
      desc: "is a minecraft mod that adds a new mob, the capybara! only on fabric for now! (it's kinda dead because of school but i try to update it when i have time!)",
    },
    {
      name: "@39choko/lastfm",
      link: "https://github.com/39choko/lastfm",
      desc: "is my first npm project! This package allows you to use lastfm's api in javascript! (if there is something that you want to add or improve please make a PR)",
    },
    {
      name: "SEKAI-Stories",
      link: "https://github.com/lezzthanthree/SEKAI-Stories",
      desc: "it's not really my project but i contributed to it by making some french localization. It's a really cool project give it a try.",
    },
  ];

  const colors = [
    {
      label: "bg",
      bg: "var(--bg)",
      txt: "var(--txt)",
      border: "1px solid var(--txt)",
    },
    { label: "txt", bg: "var(--txt)", txt: "var(--bg)" },
    { label: "pink", bg: "var(--pink)", txt: "var(--bg)" },
    { label: "kanade", bg: "var(--kanade)", txt: "var(--bg)" },
    { label: "mafuyu", bg: "var(--mafuyu)", txt: "var(--bg)" },
    { label: "mizuki", bg: "var(--mizuki)", txt: "var(--bg)" },
    { label: "ena", bg: "var(--ena)", txt: "var(--bg)" },
  ];
</script>

<main>
  <section>
    <h1>ABOUT</h1>

    <p>
      hey! I'm Choko (or Sankyu), a student interested in web development and
      programming. When you see 39Choko, 39 stands for Miku! Because I love
      vocaloid (especially GUMI and Luka) since i was a kid. (and I forgot to
      say but I LOVEEE Project Sekai!!!)
    </p>
  </section>

  <section>
    <h1>PROJECTS</h1>

    {#each projects as project}
      <p>
        <a href={project.link}>{project.name}</a>
        {project.desc}
      </p>
      <br />
    {/each}
  </section>

  <section>
    <h1>TECH</h1>
    <p>Languages: JS/TS, HTML, Python, Java, Rust</p>
    <p>Tools: VSCode, Git, Bun</p>
    <p>Font: Montserrat</p>
  </section>

  <section>
    <h1>CONTACT</h1>
    <p>EMAIL: 39choko@proton.me</p>
    <p>DISCORD: 39choko</p>
    <p>GITHUB: 39Choko</p>
    <p>X/TWITTER: sankyuchoko</p>
    <p>SPOTIFY: fwlkyvcm6qu6zzyy51nbebx4t</p>
  </section>

  <section>
    <h1>BONUS</h1>
    {#each colors as color}
      <span
        class="color"
        style="background: {color.bg}; color: {color.txt}; border: {color.border ||
          'none'}"
      >
        {color.label}
      </span>
    {/each}
  </section>
</main>
<footer>
  <h1>Choko ♡</h1>
  <p>they/them/any <a href="https://en.pronouns.page/@39choko">[...]</a></p>
</footer>

<style>
  @font-face {
    font-family: "Montserrat";
    src: url("$lib/assets/fonts/Montserrat.ttf");
    font-display: swap;
  }

  @media only screen and (min-width: 300px) {
    main {
      max-width: 90%;
      margin-top: 20px;
    }
  }

  @media only screen and (min-width: 600px) {
    main {
      max-width: 90%;
      margin-top: initial;
    }
  }

  @media only screen and (min-width: 1200px) {
    main {
      max-width: 50%;
    }
  }

  :root {
    --bg: #232333;
    --txt: #bfbdb6;
    --pink: #da91c7;

    --kanade: #bb6688;
    --mafuyu: #8888cc;
    --mizuki: #ddaacc;
    --ena: #ccaa88;
  }

  * {
    margin: 0;
  }

  :global(body) {
    font-family: "Montserrat", sans-serif;
    line-height: 1.5;
    unicode-bidi: isolate;
    background-color: var(--bg);
    color: var(--txt);
  }

  main {
    margin-left: auto;
    margin-right: auto;
  }

  section {
    padding: 2ch;
  }

  footer {
    bottom: 0px;
    padding: 50px;
    z-index: 1000;
    position: sticky;
    background: linear-gradient(transparent, var(--bg));
  }

  a,
  a:visited {
    color: var(--pink);
    text-decoration: none;
  }

  a:hover {
    color: var(--pink);
    text-decoration: underline;
  }

  .color {
    cursor: help;
    display: inline-block;
    padding: 0 0.5rem;
    margin-bottom: 2px;
    margin-right: 4px;
    width: 5rem;
    text-align: center;
    box-sizing: border-box;
  }
</style>
