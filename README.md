# Telebot-user-guess-
A bot can guess a username 
from zipfile import ZipFile

import os



# Create HTML content

html_content = """

<!DOCTYPE html>

<html lang="ar">

<head>

  <meta charset="UTF-8">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>تخمين يوزر</title>

  <style>

    body {

      font-family: sans-serif;

      text-align: center;

      background: #f5f5f5;

      padding: 20px;

    }

    button {

      padding: 15px 25px;

      background: #0088cc;

      color: white;

      font-size: 18px;

      border: none;

      border-radius: 10px;

      cursor: pointer;

      margin-top: 20px;

    }

    .username {

      font-size: 24px;

      margin-top: 40px;

    }

  </style>

</head>

<body>

  <h1>تخمين يوزر عشوائي</h1>

  <div class="username" id="result">---</div>

  <button onclick="guessUsername()">خمن الآن</button>



  <script>

    function guessUsername() {

      const chars = "abcdefghijklmnopqrstuvwxyz0123456789_";

      let username = "";

      for (let i = 0; i < 4; i++) {

        username += chars.charAt(Math.floor(Math.random() * chars.length));

      }

      document.getElementById("result").textContent = "@" + username;

    }

  </script>

</body>

</html>

"""



# Save the HTML file

project_dir = "/mnt/data/telegram_webapp"

os.makedirs(project_dir, exist_ok=True)

html_path = os.path.join(project_dir, "index.html")

with open(html_path, "w", encoding="utf-8") as f:

    f.write(html_content)



# Create a ZIP file

zip_path = "/mnt/data/telegram_webapp.zip"

with ZipFile(zip_path, "w") as zipf:

    zipf.write(html_path, arcname="index.html")



zip_path
