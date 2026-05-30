⚽ Soccer Knockout Challenge 2025 – Team Registration Website

🌐 Live Website: https://samiksha2707.github.io/skc-website-1/

A modern, responsive one-page website for Soccer Knockout Challenge 2025, built using HTML, CSS (Bootstrap), and JavaScript.

The website features an interactive Team Registration Form that automatically stores submissions in Google Sheets using Google Apps Script.


🚀 Features

🎨 Responsive Bootstrap 5 design
⚽ Modern sports-themed landing page
🧑‍🤝‍🧑 Team Registration Modal Form
📱 Mobile-friendly interface
🔗 Google Sheets Integration via Google Apps Script
⏰ Automatic timestamp recording
📊 Real-time registration data storage
🧾 Easy customization for college, school, or sports events
🛠️ Technologies Used
Technology	Purpose
HTML5	Website structure
CSS3	Custom styling
Bootstrap 5	Responsive design
JavaScript (ES6)	Form handling and API requests
Google Apps Script	Backend processing
Google Sheets	Registration database

📂 Project Structure

Soccer-Knockout-Challenge/
│
├── index.html
├── css/
│   └── style.css
├── js/
│   └── script.js
├── assets/
│   ├── images/
│   └── icons/
└── README.md
🧠 Google Sheets Integration
1️⃣ Create a Google Sheet

Create a new Google Sheet and add the following headers:

Timestamp | Team Name | College Name | Captain Name | Contact | Email | Players
2️⃣ Create Google Apps Script
Open the Google Sheet.
Navigate to Extensions → Apps Script.
Replace the default code with:
function doPost(e) {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  var data = JSON.parse(e.postData.contents);

  sheet.appendRow([
    new Date(),
    data.team_name,
    data.college_name,
    data.captain_name,
    data.contact,
    data.email,
    data.players
  ]);

  return ContentService.createTextOutput("Success");
}

Save the project.

3️⃣ Deploy the Script
Click Deploy → New Deployment
Select Web App
Configure:
Execute as: Me
Who has access: Anyone
Click Deploy
Authorize the required permissions.
Copy the generated Web App URL.

Example:

https://script.google.com/macros/s/AKfycbxxxxxxxxxxxxxxxxxxxx/exec
4️⃣ Connect the Website

Inside script.js, add your Web App URL:

const SCRIPT_URL =
  "https://script.google.com/macros/s/AKfycbxxxxxxxxxxxxxxxxxxxx/exec";

Example submission code:

document
  .getElementById("registrationForm")
  .addEventListener("submit", async (e) => {
    e.preventDefault();

    const formData = {
      team_name: document.getElementById("team_name").value,
      college_name: document.getElementById("college_name").value,
      captain_name: document.getElementById("captain_name").value,
      contact: document.getElementById("contact").value,
      email: document.getElementById("email").value,
      players: document.getElementById("players").value
    };

    try {
      await fetch(SCRIPT_URL, {
        method: "POST",
        body: JSON.stringify(formData)
      });

      alert("Registration Successful!");
      document.getElementById("registrationForm").reset();
    } catch (error) {
      console.error(error);
      alert("Failed to submit registration.");
    }
  });

  
▶️ Running the Project
Clone the repository:
git clone https://github.com/your-username/soccer-knockout-challenge.git
Open the project folder.
Launch index.html in your browser.
📋 Registration Data

All registrations are automatically stored in Google Sheets with:

Timestamp
Team Name
College Name
Captain Name
Contact Number
Email Address
Team Members
🎯 Customization

You can easily modify:

Tournament name
Theme colors
Registration fields
Hero section content
Google Sheet columns
Team size requirements
📸 Preview

A modern football tournament registration website featuring:

Hero banner
Tournament information
Registration modal
Responsive design
Google Sheets integration

📄 License

This project is open-source and available under the MIT License.

Developed for Soccer Knockout Challenge 2025 ⚽
