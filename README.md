# rozebot gamehub
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Game Hub</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f4f4;
    }
    header {
      background-color: #333;
      color: #fff;
      padding: 1rem;
      text-align: center;
    }
    .search-bar {
      margin: 1rem auto;
      text-align: center;
    }
    .search-bar input {
      padding: 0.5rem;
      width: 300px;
      font-size: 1rem;
    }
    .games-container {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 1rem;
      padding: 1rem;
    }
    .game-card {
      background: white;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      padding: 1rem;
      text-align: center;
      transition: transform 0.2s;
    }
    .game-card:hover {
      transform: scale(1.05);
    }
    .game-frame {
      width: 100%;
      height: 150px;
      border: none;
    }
  </style>
</head>
<body>
  <header>
    <h1>Game Hub</h1>
    <p>Click and play your favorite games!</p>
  </header>

  <div class="search-bar">
    <input type="text" id="searchInput" placeholder="Search for a game...">
  </div>

  <div class="games-container" id="gamesContainer">
    <div class="game-card" data-title="Cookie Clicker">
      <h3>Cookie Clicker</h3>
      <iframe class="game-frame" src="https://orteil.dashnet.org/cookieclicker/"></iframe>
    </div>
    <div class="game-card" data-title="2048">
      <h3>2048</h3>
      <iframe class="game-frame" src="https://play2048.co/"></iframe>
    </div>
    <!-- Add more game cards here -->
  </div>

  <script>
    const searchInput = document.getElementById('searchInput');
    const gameCards = document.querySelectorAll('.game-card');

    searchInput.addEventListener('input', () => {
      const query = searchInput.value.toLowerCase();
      gameCards.forEach(card => {
        const title = card.getAttribute('data-title').toLowerCase();
        if (title.includes(query)) {
          card.style.display = '';
        } else {
          card.style.display = 'none';
        }
      });
    });
  </script>
</body>
</html>
