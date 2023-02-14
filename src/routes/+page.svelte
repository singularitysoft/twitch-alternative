<!-- src/routes/index.svelte -->

<script>
  const streams = [
    {
      id: 1,
      title: 'League of Legends Worlds Championship',
      thumbnail: 'https://via.placeholder.com/150',
      category: 'Esports',
      viewers: 69,
    },
    {
      id: 2,
      title: 'Just Chatting with Friends',
      thumbnail: 'https://via.placeholder.com/150',
      category: 'Just Chatting',
      viewers: 420,
    },
    // ... more streams
  ];
</script>

<header class="header">
  <img class="logo" src="https://www.twitch.tv/p/assets/uploads/glitch_474x356.png" alt="Twitch.tv logo" />
  <input type="text" placeholder="Search" class="search-bar" />
</header>

<nav class="navbar">
  <a href="#" class="navbar-link">Browse</a>
  <a href="#" class="navbar-link">Esports</a>
  <a href="#" class="navbar-link">Music</a>
</nav>

<main>
  <h1>Popular Streams</h1>

  {#each streams as stream}
    <a href={`/channel/${stream.id}`} class="stream-card">
      <img src={stream.thumbnail} alt={stream.title} />
      <div>
        <h2>{stream.title}</h2>
        <p>{stream.category} - {stream.viewers} viewers</p>
      </div>
    </a>
  {/each}
</main>

<footer class="footer">
  <div class="footer-links">
    <a href="#">Community</a>
    <a href="#">Resources</a>
    <a href="#">Social</a>
  </div>
</footer>

<style>
  /* Reset */
  /**,
  *::before,
  *::after {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }*/

  /* Globals */
  /*body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }*/

  /* Header */
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px;
    background-color: #6441a5;
  }

  .logo {
    height: 30px;
  }

  .search-bar {
    width: 240px;
    height: 28px;
    border-radius: 3px;
    border: none;
    padding: 4px 8px;
    font-size: 14px;
  }

  /* Navbar */
  .navbar {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    background-color: #9147ff;
    height: 48px;
    padding: 0 16px;
  }

  .navbar-link {
    color: #FFFFFF;
    font-size: 14px;
    font-weight: 600;
    text-decoration: none;
    margin-right: 16px;
  }

  /* Main */
  main {
    max-width: 800px;
    margin: 0 auto;
    padding: 0 16px;
  }

  .stream-card {
    display: flex;
    align-items: center;
    padding: 10px;
  }
</style>
