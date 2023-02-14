<!-- src/routes/index.svelte -->

<script>
  const streams = [
    {
      id: 1,
      title: 'League of Legends Worlds Championship',
      thumbnail: 'https://via.placeholder.com/150',
      category: 'Esports',
      viewers: 200000,
    },
    {
      id: 2,
      title: 'Just Chatting with Friends',
      thumbnail: 'https://via.placeholder.com/150',
      category: 'Just Chatting',
      viewers: 100000,
    },
    // ... more streams
  ];
</script>

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
