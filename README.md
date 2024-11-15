<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Describe Your Symptoms</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f7fa;
            margin: 0;
            padding: 0;
        }
        .container {
            width: 100%;
            max-width: 500px;
            margin: auto;
            padding: 20px;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        .form-group {
            margin-bottom: 15px;
        }
        .form-group label {
            display: block;
            margin-bottom: 5px;
        }
        .form-group textarea {
            width: 100%;
            padding: 10px;
            margin: 5px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        .symptom-checkboxes {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }
        .symptom-checkboxes label {
            width: 45%;
        }
        .form-group button {
            padding: 10px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        .form-group button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div class="container" id="symptoms-section">
        <h1>Describe Your Symptoms</h1>
        
        <!-- Symptom Textarea -->
        <div class="form-group">
            <textarea id="symptoms" placeholder="Describe your symptoms..." rows="5" required></textarea>
        </div>

        <!-- Symptom Checkboxes -->
        <div class="symptom-checkboxes">
            <label><input type="checkbox" class="symptom" value="fever"> Fever</label>
            <label><input type="checkbox" class="symptom" value="headache"> Headache</label>
            <label><input type="checkbox" class="symptom" value="cough"> Cough</label>
            <label><input type="checkbox" class="symptom" value="fatigue"> Fatigue</label>
            <label><input type="checkbox" class="symptom" value="sore-throat"> Sore Throat</label>
            <label><input type="checkbox" class="symptom" value="shortness-breath"> Shortness of Breath</label>
        </div>

        <!-- Button to Check Symptoms -->
        <div class="form-group">
            <button id="check-symptoms-button">Check Symptoms</button>
        </div>
    </div>

    <script>
        document.getElementById("check-symptoms-button").addEventListener("click", function() {
            // Collect all the selected symptoms
            const symptoms = [];
            document.querySelectorAll(".symptom:checked").forEach((checkbox) => {
                symptoms.push(checkbox.value);
            });

            // Get the text entered in the symptoms textarea
            const symptomsText = document.getElementById("symptoms").value.trim();

            // Validate input: Check if either the text box is filled or any checkbox is selected
            if (symptomsText || symptoms.length > 0) {
                // Display selected symptoms
                alert("Symptoms entered: " + symptomsText + "\nSelected Symptoms: " + symptoms.join(", "));
                // Proceed to the next step (you can redirect to another page or show a new section)
                alert("Proceeding to the next step...");
            } else {
                alert("Please describe your symptoms or select at least one symptom.");
            }
        });
    </script>
</body>
</html>
