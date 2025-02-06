<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Will You Be My Valentine, Isingizwe? 💖</title>
    <style>
      body {
        text-align: center;
        font-family: Arial, sans-serif;
        background-image: url("images/heart\ hands.JPEG"); /* Set your local background image here */
        background-size: cover; /* Ensures the image covers the entire background */
        background-position: center; /* Centers the image */
        transition: background-image 1s; /* Smooth transition for background image change */
      }
      .container {
        margin-top: 100px;
      }
      h1 {
        color: #ff3366;
      }
      .image {
        width: 250px;
        border-radius: 15px;
        margin: 20px 0;
      }
      .buttons {
        margin-top: 20px;
      }
      button {
        font-size: 20px;
        padding: 10px 20px;
        margin: 10px;
        border: none;
        cursor: pointer;
        border-radius: 8px;
      }
      .yes {
        background-color: #ff3366;
        color: white;
      }
      .no {
        background-color: #ccc;
        color: black;
        position: relative;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <h1>Will you be my Valentine again Isingizwe? 💕</h1>
      <!-- Default Image, change this to your own -->
      <img src="images/flower.JPEG" class="image" alt="Cute Couple" />

      <div class="buttons">
        <button class="yes" onclick="acceptProposal()">Yes! 😍</button>
        <button class="no" onclick="handleNo()">No 😢</button>
      </div>
      <p id="message"></p>
    </div>

    <script>
      let noCount = 0; // Counter for "No" clicks
      let userChoice = ""; // Variable to store user's answer

      // Function for Yes click
      function acceptProposal() {
        document.getElementById("message").innerHTML =
          "Yay! I knew you'd say yes! ❤️🥰";
        document.querySelector(".image").src = "images/kissing.JPEG"; // Change this image to your own happy one
        document.body.style.backgroundImage = "url('images/mine.JPEG')"; // Change to your local happy background image
      }

      // Function for No click
      function handleNo() {
        noCount++; // Increase the "No" counter

        if (noCount === 1) {
          userChoice = "No (1st time)";
          // Change image to a sad one on the first "No" click
          document.querySelector(".image").src = "images/sad one.JPEG"; // Replace with your own sad image URL
          document.body.style.backgroundImage =
            "url('your-local-sad-background.jpg')"; // Set a local sad background image
        } else if (noCount === 2) {
          userChoice = "No (2nd time)";
          document.querySelector(".image").src = "images/sad one.JPEG";
          document.getElementById("message").innerHTML =
            "Are you sure about that? 😢"; // Ask if she's sure
          document.body.style.backgroundImage =
            "url('your-local-yellow-background.jpg')"; // Set a yellow background image locally
        } else if (noCount === 3) {
          userChoice = "No (3rd time)";
          // Change background to black and show a heartbreaking message
          document.body.style.backgroundImage =
            "url('images/broken heart.avif')"; // Set a heartbroken background image locally
          document.querySelector(".image").src =
            "https://source.unsplash.com/300x300/?heartbroken,couple"; // Replace with your own heartbroken image
          document.body.innerHTML =
            "<h1 style='color: black; margin-top: 20%;'>💔 You broke my heart...again </h1>"; // Show sad message
        }

        // Store the answer in localStorage (you can check later)
        localStorage.setItem("valentineResponse", userChoice);
      }

      // Optionally, you can add a function to retrieve the stored response (for debugging or checking later)
      function getResponse() {
        return localStorage.getItem("valentineResponse");
      }
    </script>
  </body>
</html>
