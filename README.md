# freefire-topup
Free Fire Diamond Top-Up Website
<!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Free Fire Top Up</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #10111b;
      color: white;
    }

    header {
      background: #ff6b00;
      padding: 20px;
      text-align: center;
      font-size: 23px;
      font-weight: bold;
    }

    .container {
      max-width: 500px;
      margin: auto;
      padding: 20px;
    }

    .banner {
      background: linear-gradient(135deg, #ff6b00, #ff1744);
      border-radius: 15px;
      padding: 25px;
      text-align: center;
      margin-bottom: 20px;
    }

    .banner h1 {
      margin-top: 0;
    }

    .card {
      background: #202131;
      border-radius: 12px;
      padding: 18px;
      margin-bottom: 15px;
    }

    input, select, button {
      width: 100%;
      padding: 13px;
      margin-top: 12px;
      border-radius: 8px;
      border: none;
      font-size: 16px;
    }

    input, select {
      background: #303246;
      color: white;
    }

    button {
      background: #ff6b00;
      color: white;
      font-weight: bold;
      cursor: pointer;
    }

    .package {
      display: block;
      width: 100%;
      text-align: left;
      background: #303246;
      margin-top: 10px;
      border: 2px solid transparent;
    }

    .package.selected {
      border-color: #ff6b00;
    }

    footer {
      text-align: center;
      color: #aaa;
      padding: 20px;
      font-size: 13px;
    }
  </style>
</head>
<body>

<header>🔥 FREE FIRE TOP UP</header>

<div class="container">
  <div class="banner">
    <h1>💎 Diamond Top-Up</h1>
    <p>তোমার পছন্দের প্যাকেজ নির্বাচন করো!</p>
  </div>

  <div class="card">
    <h3>১. Player UID</h3>
    <input id="uid" type="text"
      placeholder="তোমার Player UID লেখো"
      inputmode="numeric">
  </div>

  <div class="card">
    <h3>২. Diamond Package</h3>

    <button class="package" onclick="choose(25, this)">
      💎 25 Diamonds
    </button>

    <button class="package" onclick="choose(50, this)">
      💎 50 Diamonds
    </button>

    <button class="package" onclick="choose(115, this)">
      💎 115 Diamonds
    </button>

    <button class="package" onclick="choose(240, this)">
      💎 240 Diamonds
    </button>
  </div>

  <div class="card">
    <h3>৩. Payment Method</h3>
    <select id="payment">
      <option value="">পেমেন্ট নির্বাচন করো</option>
      <option value="bKash">bKash</option>
      <option value="Nagad">Nagad</option>
    </select>

    <button onclick="order()">অর্ডার করুন</button>
    <p id="result"></p>
  </div>
</div>

<footer>
  Fan-made Top-Up Website Demo
  <br>অর্ডার ও পেমেন্ট এখনো চালু নয়।
</footer>

<script>
  let diamonds = 0;

  function choose(amount, button) {
    diamonds = amount;

    document.querySelectorAll(".package")
      .forEach(item => item.classList.remove("selected"));

    button.classList.add("selected");
  }

  function order() {
    const uid = document.getElementById("uid").value.trim();
    const payment = document.getElementById("payment").value;
    const result = document.getElementById("result");

    if (!/^\d{5,20}$/.test(uid)) {
      result.textContent = "সঠিক Player UID লেখো।";
      return;
    }

    if (!diamonds || !payment) {
      result.textContent = "Diamond Package ও Payment নির্বাচন করো।";
      return;
    }

    result.textContent =
      "এটি শুধু ডেমো। কোনো অর্ডার বা পেমেন্ট সম্পন্ন হয়নি।";
  }
</script>

</body>
</html>
