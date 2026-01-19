<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TIKTOK BOOST NP - Login</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
<style>
body{
  margin:0;padding:0;font-family:'Poppins',sans-serif;
  background:#0d0d0d;color:white;display:flex;justify-content:center;align-items:center;height:100vh;
}
.container{
  background:#1a1a1a;padding:40px;border-radius:15px;width:90%;max-width:400px;text-align:center;
  box-shadow:0 0 25px rgba(255,45,45,0.5);
}
h1{color:#FF2D2D;margin-bottom:30px;}
input{width:90%;padding:12px;margin:10px 0;border-radius:10px;border:none;}
button{
  width:95%;padding:12px;margin-top:15px;border:none;border-radius:10px;background:#FF2D2D;color:white;font-weight:600;cursor:pointer;transition:0.3s;
}
button:hover{background:#e60000;}
</style>
</head>
<body>
<div class="container">
<h1>TIKTOK BOOST NP</h1>
<input id="username" placeholder="Enter Username">
<button onclick="login()">Login</button>
</div>

<script>
function login(){
  let name = document.getElementById("username").value;
  if(name==""){
    alert("Please enter your username");
  }else{
    localStorage.setItem("user", name);
    localStorage.setItem("coins", localStorage.getItem("coins")||0);
    window.location="dashboard.html";
  }
}
</script>
</body>
</html><!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dashboard - TIKTOK BOOST NP</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
<style>
body{margin:0;font-family:'Poppins',sans-serif;background:#0d0d0d;color:white;}
.navbar{background:#FF2D2D;padding:15px;text-align:center;font-weight:600;font-size:24px;letter-spacing:1px;}
.container{padding:20px;display:flex;flex-wrap:wrap;justify-content:center;}
.card{
  background:#1a1a1a;width:250px;margin:15px;padding:20px;border-radius:15px;
  box-shadow:0 0 20px rgba(255,45,45,0.4);
  text-align:center;transition:0.3s;cursor:pointer;
}
.card:hover{box-shadow:0 0 30px rgba(255,45,45,0.7);}
button{
  width:80%;margin-top:10px;padding:12px;border:none;border-radius:10px;background:#FF2D2D;color:white;font-weight:600;cursor:pointer;transition:0.3s;
}
button:hover{background:#e60000;}
@media(max-width:500px){.card{width:90%;}}
</style>
</head>
<body>

<div class="navbar">TIKTOK BOOST NP</div>

<div class="container">
  <div class="card">
    <h3>Welcome, <span id="user"></span></h3>
    <p>Balance: <span id="coins">0</span> Coins</p>
    <button onclick="location='buy.html'">Buy Coins</button>
    <button onclick="location='earn.html'">Watch & Earn</button>
  </div>
  <div class="card">
    <h3>Profile</h3>
    <p>Level: Beginner</p>
    <p>Videos Analyzed: 0</p>
    <button onclick="logout()">Logout</button>
  </div>
</div>

<script>
document.getElementById("user").innerText = localStorage.getItem("user") || "Guest";
document.getElementById("coins").innerText = localStorage.getItem("coins") || 0;

function logout(){
  localStorage.removeItem("user");
  localStorage.removeItem("coins");
  window.location="index.html";
}
</script>

</body>
</html><!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Buy Coins - TIKTOK BOOST NP</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
<style>
body{margin:0;font-family:'Poppins',sans-serif;background:#0d0d0d;color:white;text-align:center;}
.container{max-width:400px;margin:40px auto;background:#1a1a1a;padding:25px;border-radius:15px;box-shadow:0 0 20px rgba(255,45,45,0.4);}
select, button{width:90%;padding:12px;margin:10px 0;border-radius:10px;border:none;font-family:'Poppins',sans-serif;}
button{background:#FF2D2D;color:white;font-weight:600;cursor:pointer;transition:0.3s;}
button:hover{background:#e60000;}
</style>
</head>
<body>
<div class="container">
<h2>Buy Coins (Nepal)</h2>
<select id="pack">
<option value="500">500 Coins - NPR 49</option>
<option value="1200">1200 Coins - NPR 99</option>
<option value="2500">2500 Coins - NPR 199</option>
<option value="6000">6000 Coins - NPR 499</option>
</select>
<h3>Pay With</h3>
<button onclick="pay('eSewa')">eSewa</button>
<button onclick="pay('Khalti')">Khalti</button>
<button onclick="pay('Fonepay')">Fonepay</button>
<button onclick="backToDashboard()">Back</button>
</div>

<script>
function pay(method){
  let coins = Number(document.getElementById("pack").value);
  alert("Redirecting to "+method+" payment...");
  let old = Number(localStorage.getItem("coins")||0);
  localStorage.setItem("coins", old + coins);
  setTimeout(()=>{
    alert("Payment Successful! Coins Added.");
    window.location="dashboard.html";
  },1500);
}
function backToDashboard(){ window.location="dashboard.html"; }
</script>

</body>
</html><!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Watch & Earn - TIKTOK BOOST NP</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
<style>
body{margin:0;font-family:'Poppins',sans-serif;background:#0d0d0d;color:white;text-align:center;}
.container{max-width:400px;margin:40px auto;background:#1a1a1a;padding:25px;border-radius:15px;box-shadow:0 0 20px rgba(255,45,45,0.4);}
video{width:90%;border-radius:15px;margin-top:10px;}
button{width:80%;margin-top:15px;padding:12px;background:#FF2D2D;color:white;border:none;border-radius:10px;font-weight:600;cursor:pointer;transition:0.3s;}
button:hover{background:#e60000;}
</style>
</head>
<body>
<div class="container">
<h2>Watch & Earn Coins</h2>
<video controls>
  <source src="sample.mp4" type="video/mp4">
</video>
<button onclick="earnCoins()">Watch Complete & Earn 10 Coins</button>
<button onclick="backToDashboard()">Back</button>
</div>

<script>
function earnCoins(){
  let old = Number(localStorage.getItem("coins")||0);
  localStorage.setItem("coins", old + 10);
  alert("✅ You earned 10 coins!");
  window.location="dashboard.html";
}
function backToDashboard(){ window.location="dashboard.html"; }
</script>

</body>
</html># NP-TT-BOST
Tiktok like and view bot which help you to increase views on your account 
