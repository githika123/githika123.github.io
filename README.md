<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Login Page</title>
  <style>
    /* Basic Reset */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    /* Body Styling */
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      font-family: Arial, sans-serif;
      background-color: #f0f2f5;
    }

    /* Form Container */
    .login-container {
      width: 100%;
      max-width: 400px;
      padding: 20px;
      background-color: #fff;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      border-radius: 8px;
      text-align: center;
    }

    /* Form Heading */
    .login-container h2 {
      margin-bottom: 20px;
      color: #333;
    }

    /* Input Fields */
    .login-container input[type="text"],
    .login-container input[type="password"] {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #ddd;
      border-radius: 4px;
      font-size: 1em;
    }

    /* Login Button */
    .login-container button {
      width: 100%;
      padding: 10px;
      background-color: #4CAF50;
      color: white;
      font-size: 1em;
      border: none;
      border-radius: 4px;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    .login-container button:hover {
      background-color: #45a049;
    }

    /* Footer Text */
    .login-container p {
      margin-top: 20px;
      font-size: 0.9em;
      color: #777;
    }

    .login-container a {
      color: #4CAF50;
      text-decoration: none;
    }
  </style>
</head>
<body>

  <div class="login-container">
    <h2>Login</h2>
    <form>
      <input type="text" placeholder="Username" required>
      <input type="password" placeholder="Password" required>
      <button type="submit">Login</button>
    </form>
    <p>Don't have an account? <a href="#">Sign up</a></p>
  </div>

</body>
</html>
