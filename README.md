### Assignment: Building a Multimedia Webpage and a Registration Form  

#### Objective: 
The goal of this assignment is to create a multimedia-rich webpage featuring audio and video elements and design a simple registration form with built-in HTML validation.  

---

### Part 1: Multimedia Webpage 
Create an HTML webpage that includes the following:  
1. **Audio Element**:  
   - Add an audio file using the `<audio>` tag.  
   - Provide controls to play, pause, and adjust the volume.  
   - Use at least one source format (e.g., `.mp3` or `.ogg`).  

2. **Video Element**:  
   - Add a video file using the `<video>` tag.  
   - Provide controls to play, pause, and adjust the volume.  
   - Include at least two source formats for compatibility (e.g., `.mp4` and `.webm`).  
   - Add a poster image that displays before the video plays.  

**Example Output:**  
A webpage where users can play an audio track and watch a video.  

---

### **Part 2: Registration Form **  
Design a user registration form with the following requirements:  

1. **Form Elements**:  
   - Full Name (Text input)  
   - Email Address (Input of type `email`)  
   - Password (Input of type `password`)  
   - Age (Input of type `number`, with a minimum value of 18)  
   - Gender (Radio buttons for Male, Female, Other)  
   - Terms and Conditions (Checkbox to agree before submitting)  

2. **Validation**:  
   - Use HTML5 validation attributes such as `required`, `min`, `maxlength`, etc.  
   - Ensure the email field has proper validation for email format.  
   - Make the password field require at least 8 characters.  

3. **Submit Button**:  
   - Include a "Register" button to submit the form.  

**Example Output:**  
A user-friendly registration form that prevents submission if required fields are not filled correctly.  

---





<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Multimedia Webpage and Registration Form</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            padding: 20px;
        }
        h1 {
            text-align: center;
            color: #333;
        }
        .container {
            max-width: 800px;
            margin: 0 auto;
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .media-section {
            margin-bottom: 40px;
            text-align: center;
        }
        .form-section {
            margin-top: 30px;
        }
        label {
            font-weight: bold;
            margin-top: 10px;
            display: block;
        }
        input[type="text"],
        input[type="email"],
        input[type="password"],
        input[type="number"],
        input[type="radio"],
        input[type="checkbox"] {
            width: 100%;
            padding: 10px;
            margin: 10px 0 20px 0;
            border-radius: 4px;
            border: 1px solid #ccc;
        }
        button {
            width: 100%;
            padding: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>

    <h1>Multimedia Webpage with Registration Form</h1>

    <div class="container">

        <!-- Multimedia Section -->
        <div class="media-section">
            <h2>Listen to Audio</h2>
            <audio controls>
                <source src="audio-track.mp3" type="audio/mp3">
                <source src="audio-track.ogg" type="audio/ogg">
                Your browser does not support the audio element.
            </audio>

            <h2>Watch Video</h2>
            <video controls poster="video-poster.jpg" width="600">
                <source src="video-file.mp4" type="video/mp4">
                <source src="video-file.webm" type="video/webm">
                Your browser does not support the video element.
            </video>
        </div>

        <!-- Registration Form Section -->
        <div class="form-section">
            <h2>User Registration</h2>
            <form action="#" method="POST" id="registration-form">

                <label for="fullname">Full Name:</label>
                <input type="text" id="fullname" name="fullname" required maxlength="100" placeholder="Enter your full name">

                <label for="email">Email Address:</label>
                <input type="email" id="email" name="email" required placeholder="Enter your email">

                <label for="password">Password:</label>
                <input type="password" id="password" name="password" required minlength="8" placeholder="Enter your password">

                <label for="age">Age:</label>
                <input type="number" id="age" name="age" required min="18" placeholder="Enter your age">

                <label>Gender:</label>
                <input type="radio" id="male" name="gender" value="Male" required> Male
                <input type="radio" id="female" name="gender" value="Female" required> Female
                <input type="radio" id="other" name="gender" value="Other" required> Other

                <label for="terms">
                    <input type="checkbox" id="terms" name="terms" required> I agree to the Terms and Conditions
                </label>

                <button type="submit">Register</button>
            </form>
        </div>

    </div>

    <script>
        document.getElementById("registration-form").addEventListener("submit", function(event) {
            if (!document.getElementById("terms").checked) {
                alert("You must agree to the terms and conditions before submitting the form.");
                event.preventDefault();
            }
        });
    </script>

</body>
</html>

