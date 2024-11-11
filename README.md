<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Social Media Time Control</title>
  <style>
    /* Basic Styling */
    body {
      font-family: Arial, sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      background-color: #f4f4f9;
      margin: 0;
      padding: 20px;
    }

    h1, h2 {
      color: #333;
    }

    /* Control Form Styling */
    .control-form {
      width: 80%;
      max-width: 600px;
      margin-top: 20px;
      padding: 20px;
      background-color: #fff;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      border-radius: 8px;
    }

    .control-form label, .control-form input {
      display: inline-block;
      margin-bottom: 10px;
    }

    .control-form input[type="number"] {
      width: 60px;
      padding: 5px;
      margin-right: 10px;
    }

    .control-form button {
      padding: 10px;
      background-color: #4CAF50;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
      margin-top: 10px;
    }

    .control-form .platform-controls {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin: 5px 0;
    }
  </style>
</head>
<body>

  <h1>Social Media Usage Control</h1>
  
  <!-- Control Form -->
  <div class="control-form">
    <h2>Set Daily Time Limits (Minutes)</h2>
    <div class="platform-controls">
      <label for="facebookTime">Facebook:</label>
      <input type="number" id="facebookTime" value="60">
      <button onclick="startTimer('Facebook')">Start</button>
      <button onclick="stopTimer('Facebook')">Stop</button>
      <span id="facebookRemaining">Remaining: 60 mins</span>
    </div>
    
    <div class="platform-controls">
      <label for="instagramTime">Instagram:</label>
      <input type="number" id="instagramTime" value="45">
      <button onclick="startTimer('Instagram')">Start</button>
      <button onclick="stopTimer('Instagram')">Stop</button>
      <span id="instagramRemaining">Remaining: 45 mins</span>
    </div>
    
    <div class="platform-controls">
      <label for="twitterTime">Twitter:</label>
      <input type="number" id="twitterTime" value="30">
      <button onclick="startTimer('Twitter')">Start</button>
      <button onclick="stopTimer('Twitter')">Stop</button>
      <span id="twitterRemaining">Remaining: 30 mins</span>
    </div>
    
    <div class="platform-controls">
      <label for="linkedinTime">LinkedIn:</label>
      <input type="number" id="linkedinTime" value="20">
      <button onclick="startTimer('LinkedIn')">Start</button>
      <button onclick="stopTimer('LinkedIn')">Stop</button>
      <span id="linkedinRemaining">Remaining: 20 mins</span>
    </div>
    
    <div class="platform-controls">
      <label for="snapchatTime">Snapchat:</label>
      <input type="number" id="snapchatTime" value="25">
      <button onclick="startTimer('Snapchat')">Start</button>
      <button onclick="stopTimer('Snapchat')">Stop</button>
      <span id="snapchatRemaining">Remaining: 25 mins</span>
    </div>
    
    <div class="platform-controls">
      <label for="tiktokTime">TikTok:</label>
      <input type="number" id="tiktokTime" value="50">
      <button onclick="startTimer('TikTok')">Start</button>
      <button onclick="stopTimer('TikTok')">Stop</button>
      <span id="tiktokRemaining">Remaining: 50 mins</span>
    </div>
  </div>

  <script>
    const timeLimits = {};
    const timers = {};
    const remainingTime = {};

    // Initialize time limits and remaining time
    function initializeTimes() {
      const platforms = ['Facebook', 'Instagram', 'Twitter', 'LinkedIn', 'Snapchat', 'TikTok'];
      platforms.forEach(platform => {
        const inputTime = document.getElementById(`${platform.toLowerCase()}Time`).value;
        timeLimits[platform] = parseInt(inputTime);
        remainingTime[platform] = parseInt(inputTime);
        updateRemainingTimeDisplay(platform);
      });
    }

    // Update remaining time display
    function updateRemainingTimeDisplay(platform) {
      document.getElementById(`${platform.toLowerCase()}Remaining`).innerText = `Remaining: ${remainingTime[platform]} mins`;
    }

    // Start timer for platform
    function startTimer(platform) {
      if (remainingTime[platform] <= 0) {
        alert(`${platform} time limit reached!`);
        return;
      }
      
      if (!timers[platform]) {
        timers[platform] = setInterval(() => {
          if (remainingTime[platform] > 0) {
            remainingTime[platform]--;
            updateRemainingTimeDisplay(platform);
          } else {
            clearInterval(timers[platform]);
            timers[platform] = null;
            alert(`${platform} time limit reached!`);
          }
        }, 60000); // 1 minute interval
      }
    }

    // Stop timer for platform
    function stopTimer(platform) {
      if (timers[platform]) {
        clearInterval(timers[platform]);
        timers[platform] = null;
      }
    }

    // Update time limits when user changes input values
    document.querySelectorAll('.control-form input[type="number"]').forEach(input => {
      input.addEventListener('change', (event) => {
        const platform = event.target.id.replace('Time', '');
        const newLimit = parseInt(event.target.value);
        timeLimits[platform] = newLimit;
        remainingTime[platform] = newLimit;
        updateRemainingTimeDisplay(platform);
      });
    });

    // Initialize on page load
    initializeTimes();
  </script>

</body>
</html>
