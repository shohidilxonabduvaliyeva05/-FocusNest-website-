# -FocusNest-website-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>FocusNest - Sleep & Habit Tracker</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      padding: 0;
      background: #f2f2f2;
      color: #333;
      transition: background 0.3s, color 0.3s;
    }
    .dark-mode {
      background: #121212;
      color: #eee;
    }
    header {
      text-align: center;
      padding: 20px;
      background-color: #4a90e2;
      color: white;
    }
    .container {
      padding: 20px;
      max-width: 600px;
      margin: auto;
    }
    .section {
      margin-bottom: 30px;
    }
    .habit-list input {
      margin-right: 10px;
    }
    .mood-log input {
      width: 100%;
      padding: 8px;
      margin-top: 8px;
    }
    .nest {
      margin-top: 20px;
      text-align: center;
      font-size: 60px;
      transition: transform 0.3s;
    }
    .dark-toggle {
      position: absolute;
      top: 20px;
      right: 20px;
      background: none;
      border: 1px solid white;
      color: white;
      padding: 5px 10px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <header>
    <h1>🌙 FocusNest</h1>
    <p>Build Better Sleep & Focus Habits</p>
    <button class="dark-toggle" onclick="toggleDarkMode()">🌓</button>
  </header>
  <div class="container">
    <div class="section">
      <h2>✅ Tiny Habit Checklist</h2>
      <div class="habit-list">
        <label><input type="checkbox" onchange="updateNest()"> No screen 30 mins before bed</label><br>
        <label><input type="checkbox" onchange="updateNest()"> Meditate for 2 minutes</label><br>
        <label><input type="checkbox" onchange="updateNest()"> Write one gratitude note</label><br>
      </div>
    </div>

    <div class="section">
      <h2>📓 Mood Log</h2>
      <input type="text" placeholder="How are you feeling tonight?" id="moodInput">
    </div>

    <div class="section nest" id="nest">🐣</div>
  </div>

  <script>
    function updateNest() {
      const checks = document.querySelectorAll('.habit-list input:checked').length;
      const nest = document.getElementById('nest');
      if (checks === 0) nest.textContent = '🐣';
      else if (checks === 1) nest.textContent = '🐤';
      else if (checks === 2) nest.textContent = '🐥';
      else nest.textContent = '🕊️';
    }

    function toggleDarkMode() {
      document.body.classList.toggle('dark-mode');
    }
  </script>
</body>
</html>
