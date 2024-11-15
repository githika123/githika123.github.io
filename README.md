<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Support Login</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Welcome to the Support Network</h1>
        <div class="form-container">
            <form id="loginForm">
                <h2>Login</h2>
                <label for="loginEmail">Email:</label>
                <input type="email" id="loginEmail" name="email" required>
                <label for="loginPassword">Password:</label>
                <input type="password" id="loginPassword" name="password" required>
                <button type="submit">Login</button>
            </form>

            <form id="registerForm">
                <h2>Register</h2>
                <label for="registerEmail">Email:</label>
                <input type="email" id="registerEmail" name="email" required>
                <label for="registerPassword">Password:</label>
                <input type="password" id="registerPassword" name="password" required>
                <label for="registerConfirmPassword">Confirm Password:</label>
                <input type="password" id="registerConfirmPassword" name="confirmPassword" required>
                <button type="submit">Register</button>
            </form>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
