<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Social Media Comparison</title>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <style>
    /* General Styling */
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
  </style>
</head>
<body>

  <h1>Comparison of Social Media Platforms</h1>
  
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

  <script>
    // Chart.js Pie Chart
    const ctx = document.getElementById('timeSpentChart').getContext('2d');
    const timeSpentChart = new Chart(ctx, {
      type: 'pie',
      data: {
        labels: ['Facebook', 'Instagram', 'Twitter', 'LinkedIn', 'Snapchat', 'TikTok'],
        datasets: [{
          label: 'Time Spent (%)',
          data: [25, 20, 15, 10, 10, 20], // Sample percentage data for each platform
          backgroundColor: [
            '#3b5998', // Facebook
            '#e4405f', // Instagram
            '#1da1f2', // Twitter
            '#0077b5', // LinkedIn
            '#fffc00', // Snapchat
            '#69c9d0'  // TikTok
          ],
          hoverOffset: 5
        }]
      },
      options: {
        responsive: true,
        plugins: {
          legend: {
            position: 'top',
          },
          tooltip: {
            callbacks: {
              label: function(tooltipItem) {
                return tooltipItem.label + ': ' + tooltipItem.raw + '%';
              }
            }
          }
        }
      }
    });
  </script>

</body>
</html>
