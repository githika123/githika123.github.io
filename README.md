<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Social Media Usage Control</title>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
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

    /* Table Styling */
    .comparison-table {
      width: 80%;
      max-width: 1000px;
      border-collapse: collapse;
      margin: 20px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    .comparison-table thead {
      background-color: #4CAF50;
      color: white;
    }

    .comparison-table th, .comparison-table td {
      padding: 12px;
      border: 1px solid #ddd;
      text-align: center;
    }

    .comparison-table tr:nth-child(even) {
      background-color: #f9f9f9;
    }

    /* Chart Container */
    .chart-container {
      width: 80%;
      max-width: 600px;
      margin-top: 40px;
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
  </style>
</head>
<body>

  <h1>Social Media Usage Control</h1>
  
  <!-- Comparison Table -->
  <table class="comparison-table">
    <thead>
      <tr>
        <th>Platform</th>
        <th>Advantages</th>
        <th>Disadvantages</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Facebook</td>
        <td>Large user base, versatile platform (text, photos, video), groups and marketplace.</td>
        <td>Privacy concerns, misinformation, high ad content.</td>
      </tr>
      <tr>
        <td>Instagram</td>
        <td>Photo and video-centric, popular with younger demographics, strong influencer presence.</td>
        <td>Highly visual (limited text), can lead to negative self-image, prone to over-filtering.</td>
      </tr>
      <tr>
        <td>Twitter</td>
        <td>Real-time news updates, hashtag trends, concise content, direct communication.</td>
        <td>Character limit can restrict depth, prone to misinformation and toxicity.</td>
      </tr>
      <tr>
        <td>LinkedIn</td>
        <td>Professional networking, job hunting, industry-specific groups.</td>
        <td>Less casual, primarily work-related content, can feel impersonal.</td>
      </tr>
      <tr>
        <td>Snapchat</td>
        <td>Ephemeral content, popular with younger users, fun filters and AR features.</td>
        <td>Content is temporary, limited reach for businesses, privacy issues.</td>
      </tr>
      <tr>
        <td>TikTok</td>
        <td>Highly engaging, short videos, popular with Gen Z, creative editing tools.</td>
        <td>Privacy concerns, content can be addictive, can encourage trends with risk.</td>
      </tr>
    </tbody>
  </table>

  <!-- Chart Container -->
  <div class="chart-container">
    <h2>Percentage of Time Spent on Each Platform</h2>
    <canvas id="timeSpentChart"></canvas>
  </div>

  <!-- Control Form -->
  <div class="control-form">
    <h2>Set Daily Time Limit (Minutes)</h2>
    <form id="timeLimitForm">
      <label for="facebookTime">Facebook:</label>
      <input type="number" id="facebookTime" value="60">
      
      <label for="instagramTime">Instagram:</label>
      <input type="number" id="instagramTime" value="45">
      
      <label for="twitterTime">Twitter:</label>
      <input type="number" id="twitterTime" value="30">
      
      <label for="linkedinTime">LinkedIn:</label>
      <input type="number" id="linkedinTime" value="20">
      
      <label for="snapchatTime">Snapchat:</label>
      <input type="number" id="snapchatTime" value="25">
      
      <label for="tiktokTime">TikTok:</label>
      <input type="number" id="tiktokTime" value="50">
      
      <button type="button" onclick="setTimeLimits()">Set Limits</button>
    </form>
    <p id="remainingTimeMessage"></p>
  </div>

  <script>
    // Chart.js Pie Chart for Time Spent on Social Media
    const ctx = document.getElementById('timeSpentChart').getContext('2d');
    const timeSpentChart = new Chart(ctx, {
      type: 'pie',
      data: {
        labels: ['Facebook', 'Instagram', 'Twitter', 'LinkedIn', 'Snapchat', 'TikTok'],
        datasets: [{
          label: 'Time Spent (%)',
          data: [25, 20, 15, 10, 10, 20],
          backgroundColor: [
            '#3b5998', '#e4405f', '#1da1f2', '#0077b5', '#fffc00', '#69c9d0'
          ],
          hoverOffset: 5
        }]
      },
      options: {
        responsive: true,
        plugins: {
          legend: { position: 'top' },
          tooltip: {
            callbacks: {
              label: tooltipItem => `${tooltipItem.label}: ${tooltipItem.raw}%`
            }
          }
        }
      }
    });

    // Time limit controls
    const timeLimits = {
      Facebook: 60,
      Instagram: 45,
      Twitter: 30,
      LinkedIn: 20,
      Snapchat: 25,
      TikTok: 50
    };

    function setTimeLimits() {
      timeLimits.Facebook = parseInt(document.getElementById('facebookTime').value);
      timeLimits.Instagram = parseInt(document.getElementById('instagramTime').value);
      timeLimits.Twitter = parseInt(document.getElementById('twitterTime').value);
      timeLimits.LinkedIn = parseInt(document.getElementById('linkedinTime').value);
      timeLimits.Snapchat = parseInt(document.getElementById('snapchatTime').value);
      timeLimits.TikTok = parseInt(document.getElementById('tiktokTime').value);

      const totalTime = Object.values(timeLimits).reduce((acc, time) => acc + time, 0);
      document.getElementById('remainingTimeMessage').innerText = 
        `Total time limit across platforms: ${totalTime} minutes per day.`;
    }
  </script>

</body>
</html>
