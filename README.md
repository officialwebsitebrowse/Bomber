<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>HTML Generator</title>
  <style>
    /* কালো ব্যাকগ্রাউন্ড এবং সবুজ আউটলাইন */
    body {
      background-color: black;
      color: white;
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 50px;
      margin: 0;
    }

    /* ইনপুট ফিল্ডের স্টাইল */
    input {
      padding: 10px;
      margin: 10px;
      border: 2px solid green;
      background-color: black;
      color: white;
      outline: none;
      font-size: 16px;
      width: 300px;
      border-radius: 5px;
    }

    input[type="text"] {
      width: 300px;
    }

    input[type="textarea"] {
      width: 400px;
      height: 100px;
    }

    /* Get Link বাটনের স্টাইল */
    button {
      padding: 12px 20px;
      background-color: green;
      border: none;
      color: white;
      font-size: 18px;
      border-radius: 5px;
      cursor: pointer;
      margin-top: 20px;
    }

    button:hover {
      background-color: #00FF00;
    }

    /* "Made by Akash" এর নিচে রঙ পরিবর্তনের জন্য স্টাইল */
    .made-by {
      font-size: 20px;
      font-weight: bold;
      margin-top: 50px;
      animation: colorChange 5s infinite;
    }

    @keyframes colorChange {
      0% { color: #FF5733; }
      25% { color: #33FF57; }
      50% { color: #5733FF; }
      75% { color: #FF33A1; }
      100% { color: #FF5733; }
    }

    /* Contact বাটনের স্টাইল */
    .contact-button {
      background-color: blue;
      color: white;
      font-size: 16px;
      border-radius: 5px;
      padding: 10px 20px;
      text-decoration: none;
      display: inline-block;
      margin-left: 20px;
    }

    .contact-button:hover {
      background-color: #00BFFF;
    }
  </style>
</head>
<body>

  <h1>Create Your HTML Website</h1>
  
  <div>
    <!-- ফাইল নাম ইনপুট -->
    <input type="text" id="fileName" placeholder="File Name"><br>

    <!-- HTML কোড ইনপুট -->
    <textarea id="htmlCode" placeholder="Enter HTML Code"></textarea><br>

    <!-- Get Link বাটন -->
    <button onclick="generateLink()">Get Link</button>
  </div>

  <!-- "Made by Akash" এবং Contact বাটন -->
  <div class="made-by">
    Made by Akash
    <a href="https://www.facebook.com/profile.php?id=100090690904199" class="contact-button" target="_blank">Contact</a>
  </div>

  <!-- JavaScript কোড -->
  <script>
    function generateLink() {
      // ইনপুট ফিল্ড থেকে ডেটা নিয়ে আসা
      var fileName = document.getElementById('fileName').value;
      var htmlCode = document.getElementById('htmlCode').value;

      // ফাইল নাম এবং HTML কোড চেক করা
      if (fileName === "" || htmlCode === "") {
        alert("Please fill in both fields!");
        return;
      }

      // নতুন URL তৈরি করা
      var blob = new Blob([htmlCode], { type: 'text/html' });
      var link = document.createElement('a');
      link.href = URL.createObjectURL(blob);
      link.download = fileName + ".html";

      // লিঙ্কের ক্লিক করা
      link.click();
    }
  </script>

</body>
</html>
