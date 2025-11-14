<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Member Dashboard Access</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #a1e3a1, #137a3d);
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    #box {
      padding: 30px;
      border-radius: 20px;
      background: #ffffff;
      box-shadow: 0 6px 25px rgba(0,0,0,0.25);
      text-align: center;
      width: 360px;
    }
    h2 {
      color: #137a3d;
      margin-bottom: 10px;
      font-family: 'Trebuchet MS', sans-serif;
    }
    p {
      color: #444;
      font-size: 14px;
      margin-bottom: 20px;
    }
    input {
      width: 80%;
      padding: 12px;
      font-size: 16px;
      border-radius: 12px;
      border: 2px solid #137a3d;
      text-align: center;
      outline: none;
      margin-bottom: 20px;
    }
    button {
      padding: 12px 20px;
      font-size: 16px;
      background: #137a3d;
      color: white;
      border: none;
      border-radius: 15px;
      cursor: pointer;
      transition: background 0.3s, transform 0.2s;
    }
    button:hover {
      background: #0f5a2d;
      transform: scale(1.05);
    }
    #error {
      color: red;
      font-size: 14px;
      margin-top: 15px;
    }
    #note {
      font-size: 12px;
      color: #555;
      margin-top: 15px;
    }
    a {
      color: #137a3d;
      text-decoration: none;
      font-weight: bold;
    }
    a:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>
  <div id="box">
    <h2>Member Dashboard</h2>
    <p>Enter your Member ID to access your troop page.</p>
    <input id="memberId" maxlength="9" placeholder="Enter up to 9 digits" oninput="this.value=this.value.replace(/[^0-9]/g,'')">
    <br>
    <button onclick="go()">Enter Dashboard</button>
    <p id="error"></p>
    <p id="note">If your ID does not exist, contact <a href="mailto:gs.troop06302@gmail.com">gs.troop06302@gmail.com</a></p>
  </div>

  <script>
    function go() {
      const id = document.getElementById("memberId").value.trim();
      const error = document.getElementById("error");
      if (!id) {
        error.textContent = "Please enter a member ID.";
        return;
      }
      const url = "https://sites.google.com/view/gstroop06302/members/" + id;
      window.location.href = url;
    }
  </script>
</body>
</html>

