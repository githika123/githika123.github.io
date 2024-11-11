<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Website</title>
  <style>
    /* CSS Styling */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: Arial, sans-serif;
      color: #333;
      background-color: #f9f9f9;
    }

    header, main, footer {
      max-width: 800px;
      margin: auto;
      padding: 20px;
    }

    header {
      text-align: center;
      padding: 40px 20px;
      background-color: #4CAF50;
      color: white;
    }

    h1 {
      font-size: 2.5em;
    }

    section {
      margin: 20px 0;
    }

    h2 {
      color: #4CAF50;
    }

    footer {
      text-align: center;
      padding: 10px;
      background-color: #333;
      color: white;
      font-size: 0.9em;
    }
  </style>
</head>
<body>
  <header>
    <h1>Welcome to My Website</h1>
    <p>This is a simple webpage created using HTML, CSS, and JavaScript.</p>
  </header>
  
  <main>
    <section id="about">
      <h2>About Me</h2>
      <p>Hello! I'm creating a yin yang website.</p>
    </section>
    <section id="contact">
      <h2>Contact</h2>
      <p>Email me at <a href="mailto:example@example.com">example@example.com</a></p>
    </section>
  </main>

  <footer>
    <p>© 2023 My Website</p>
  </footer>
  
  <script>
    // JavaScript for interactivity
    window.onload = function() {
      alert("Welcome to My Website!");
    };
  </script>
</body>
</html>
