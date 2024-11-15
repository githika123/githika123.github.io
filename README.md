<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Support Registration</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f7fa;
            color: #333;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .registration-container {
            background: #ffffff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            max-width: 400px;
            width: 100%;
        }

        .registration-container h1 {
            font-size: 24px;
            margin-bottom: 10px;
            text-align: center;
        }

        .registration-container form {
            display: flex;
            flex-direction: column;
        }

        .registration-container label {
            margin-bottom: 5px;
            font-weight: bold;
        }

        .registration-container input {
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        .registration-container button {
            padding: 10px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        .registration-container button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div class="registration-container">
        <h1>Join Our Support Group</h1>
        <form id="registrationForm">
            <label for="username">Username</label>
            <input type="text" id="username" name="username" placeholder="Enter your username" required>

            <label for="email">Email</label>
            <input type="email" id="email" name="email" placeholder="Enter your email" required>

            <label for="password">Password</label>
            <input type="password" id="password" name="password" placeholder="Enter your password" required>

            <button type="submit">Register</button>
        </form>
    </div>

    <script>
        document.getElementById("registrationForm").addEventListener("submit", function(event) {
            event.preventDefault(); // Prevent form submission
            
            const username = document.getElementById("username").value;
            const email = document.getElementById("email").value;
            const password = document.getElementById("password").value;

            // For now, just log the credentials (In real-world, send data to server)
            console.log("Username:", username);
            console.log("Email:", email);
            console.log("Password:", password);

            alert("Registration successful! Welcome to the support group.");
        });
    </script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Support Registration & Diagnosis</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f7fa;
            color: #333;
            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background-color: #ffffff;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        h1, h2 {
            text-align: center;
        }
        .form-group {
            margin-bottom: 15px;
        }
        label {
            font-weight: bold;
            margin-bottom: 5px;
            display: block;
        }
        input, textarea, select {
            width: 100%;
            padding: 10px;
            margin: 5px 0 15px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        button {
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            background-color: #007bff;
            color: white;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
        .hidden {
            display: none;
        }
        .diagnosis-result, .doctor-info {
            display: none;
            margin-top: 20px;
        }
        .appointment {
            display: none;
        }
        .confirmed {
            background-color: #28a745;
            color: white;
            padding: 10px;
            text-align: center;
            margin-top: 20px;
            border-radius: 4px;
        }
    </style>
</head>
<body>

<div class="container">
    <div id="registration-section">
        <h1>Register</h1>
        <form id="registrationForm">
            <div class="form-group">
                <label for="username">Username</label>
                <input type="text" id="username" name="username" placeholder="Enter your username" required>
            </div>
            <div class="form-group">
                <label for="email">Email</label>
                <input type="email" id="email" name="email" placeholder="Enter your email" required>
            </div>
            <div class="form-group">
                <label for="password">Password</label>
                <input type="password" id="password" name="password" placeholder="Enter your password" required>
            </div>
            <button type="submit">Register</button>
        </form>
        <p class="hidden" id="already-have-account">
            Already have an account? <a href="javascript:void(0)" id="login-link">Login</a>
        </p>
    </div>

    <div id="login-section" class="hidden">
        <h1>Login</h1>
        <form id="loginForm">
            <div class="form-group">
                <label for="login-username">Username</label>
                <input type="text" id="login-username" name="login-username" placeholder="Enter your username" required>
            </div>
            <div class="form-group">
                <label for="login-password">Password</label>
                <input type="password" id="login-password" name="login-password" placeholder="Enter your password" required>
            </div>
            <button type="submit">Login</button>
        </form>
    </div>

    <div id="symptom-section" class="hidden">
        <h2>Describe Your Symptoms</h2>
        <textarea id="symptoms" placeholder="Enter your symptoms (max 500 words)" maxlength="500"></textarea>
        <button id="check-symptoms-btn">Check Symptoms</button>
    </div>

    <div id="diagnosis-result" class="diagnosis-result">
        <h2>Diagnosis Result</h2>
        <p><b>Diagnosis: Common Cold</b></p>
        <p><i>Common Symptoms:</i></p>
        <div style="display: flex; gap: 10px;">
            <div>Running nose</div>
            <div>Cough</div>
            <div>Sneezing</div>
            <div>Sore throat</div>
            <div>Headache</div>
            <div>Fever</div>
        </div>
        <p class="doctor-info">
            <b>Recommended Specialists:</b><br>
            <p><b>Dr. Sarah Smith</b> - General Medicine (15 years experience)</p>
            <p><b>Dr. James Wilson</b> - Family Medicine (12 years experience)</p>
            <button id="book-appointment-btn">Book Appointment</button>
        </p>
    </div>

    <div id="appointment-section" class="appointment hidden">
        <h2>Book an Appointment</h2>
        <select id="doctor-select">
            <option value="Dr. Sarah Smith">Dr. Sarah Smith</option>
            <option value="Dr. James Wilson">Dr. James Wilson</option>
        </select>
        <br>
        <label for="appointment-date">Choose Date & Time:</label>
        <input type="datetime-local" id="appointment-date">
        <br>
        <button id="confirm-appointment-btn">Confirm Appointment</button>
    </div>

    <div id="confirmation" class="hidden">
        <div class="confirmed">
            Appointment Confirmed with <span id="confirmed-doctor"></span> at <span id="confirmed-time"></span>
        </div>
    </div>
</div>

<script>
    document.getElementById('registrationForm').addEventListener('submit', function(event) {
        event.preventDefault();
        document.getElementById('registration-section').classList.add('hidden');
        document.getElementById('already-have-account').classList.remove('hidden');
    });

    document.getElementById('login-link').addEventListener('click', function() {
        document.getElementById('login-section').classList.remove('hidden');
        document.getElementById('registration-section').classList.add('hidden');
    });

    document.getElementById('check-symptoms-btn').addEventListener('click', function() {
        document.getElementById('symptom-section').classList.add('hidden');
        document.getElementById('diagnosis-result').classList.remove('hidden');
    });

    document.getElementById('book-appointment-btn').addEventListener('click', function() {
        document.getElementById('diagnosis-result').classList.add('hidden');
        document.getElementById('appointment-section').classList.remove('hidden');
    });

    document.getElementById('confirm-appointment-btn').addEventListener('click', function() {
        var doctor = document.getElementById('doctor-select').value;
        var time = document.getElementById('appointment-date').value;
        
        document.getElementById('appointment-section').classList.add('hidden');
        document.getElementById('confirmation').classList.remove('hidden');
        
        document.getElementById('confirmed-doctor').innerText = doctor;
        document.getElementById('confirmed-time').innerText = new Date(time).toLocaleString();
    });
</script>

</body>
</html>
