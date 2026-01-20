index.html
ff-login-spin-demo.html
<!DOCTYPE html>
<html>
<head>
  <title>FF Login & Spin (Demo)</title>
  <style>
    body {
      margin: 0;
      background: #000;
      font-family: Arial, sans-serif;
      color: white;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .box {
      width: 320px;
      background: #1a1a1a;
      padding: 20px;
      border-radius: 15px;
      text-align: center;
      box-shadow: 0 0 20px #ff9900;
    }

    h2 {
      color: #ff9900;
    }

    input {
      width: 90%;
      padding: 8px;
      margin: 6px 0;
      border-radius: 6px;
      border: none;
    }

    button {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      background: #ff9900;
      border: none;
      border-radius: 10px;
      font-weight: bold;
      cursor: pointer;
    }

    .wheel {
      width: 160px;
      height: 160px;
      border-radius: 50%;
      border: 8px solid #00c3ff;
      margin: 15px auto;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 32px;
      transition: transform 2s ease-out;
    }

    .result {
      font-size: 18px;
      margin-top: 10px;
      color: #00eaff;
    }

    .note {
      font-size: 11px;
      color: #aaa;
      margin-top: 10px;
    }

    .hidden {
      display: none;
    }
  </style>
</head>
<body>

<!-- LOGIN -->
<div class="box" id="loginBox">
  <h2>FREE FIRE</h2>
  <input type="text" id="user" placeholder="Player ID (Demo)">
  <input type="password" id="pass" placeholder="Password (Demo)">
  <button onclick="login()">LOGIN</button>
  <div class="note">Login demo • bukan akun FF asli</div>
</div>

<!-- SPIN -->
<div class="box hidden" id="spinBox">
  <h2>SPIN DIAMOND</h2>
  <div class="wheel" id="wheel">💎</div>
  <button onclick="spin()">SPIN</button>
  <div class="result" id="hasil">Tekan SPIN</div>
  <div class="note">Diamond palsu • demo UI</div>
</div>

<script>
  function login() {
    let user = document.getElementById("user").value;
    let pass = document.getElementById("pass").value;

    if (user !== "" && pass !== "") {
      document.getElementById("loginBox").classList.add("hidden");
      document.getElementById("spinBox").classList.remove("hidden");
    } else {
      alert("Isi ID & Password dulu!");
    }
  }

  let deg = 0;
  const hadiah = [10, 50, 100, 250, 500, 1000];

  function spin() {
    const wheel = document.getElementById("wheel");
    const hasil = document.getElementById("hasil");

    deg += 720 + Math.floor(Math.random() * 360);
    wheel.style.transform = "rotate(" + deg + "deg)";

    const dapat = hadiah[Math.floor(Math.random() * hadiah.length)];
    setTimeout(() => {
      hasil.innerText = "Kamu dapat 💎 " + dapat;
    }, 2000);
  }
</script>

</body>
</html>
