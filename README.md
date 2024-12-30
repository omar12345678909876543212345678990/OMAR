<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>أسعار الذهب - الإمارات</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 0;
      padding: 0;
      background-color: #f9f9f9;
      color: #333;
    }

    .gold-bar {
      background-color: #b38226;
      height: 70px;
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 20px;
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
      box-sizing: border-box;
    }

    .gold-bar-content {
      display: flex;
      align-items: center; /* Align logo and text vertically */
    }

    .gold-bar img {
      height: 50px;
    }

    .gold-bar-text {
      color: white;
      font-size: 1.5rem;
      font-weight: bold;
      margin-left: 10px; /* Space between logo and text */
    }

    .language-toggle {
      padding: 10px 20px;
      font-size: 1rem;
      background-color: #fff;
      color: #b38226;
      border: 2px solid #b38226;
      border-radius: 5px;
      cursor: pointer;
      font-weight: bold;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }

    .language-toggle:hover {
      background-color: #b38226;
      color: #fff;
    }

    .container {
      padding: 20px;
      border: 1px solid #ddd;
      border-radius: 10px;
      background: #fff;
      margin: 20px auto;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      max-width: 90%;
      width: 400px;
      box-sizing: border-box;
    }

    .price {
      font-size: 2.5rem;
      color: #b38226;
      font-weight: bold;
      margin: 20px 0;
    }

    .update-time {
      font-size: 1.2rem;
      color: #666;
      margin-top: 10px;
    }

    .converter {
      margin-top: 20px;
      font-size: 1rem;
      color: #444;
    }

    .converter button {
      padding: 10px 15px;
      font-size: 1rem;
      background-color: #b38226;
      color: #fff;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    .converter button:hover {
      background-color: #a0731d;
    }

    .usd-output {
      font-size: 1.5rem;
      color: #444;
      font-weight: bold;
      margin-top: 15px;
    }
  </style>
</head>
<body>
  <div class="gold-bar">
    <div class="gold-bar-content">
      <img src="logo.jpg" alt="Logo">
      <span class="gold-bar-text">UAEGP</span>
    </div>
    <button class="language-toggle" onclick="toggleLanguage()">EN</button>
  </div>

  <div class="container">
    <h1 id="title">سعر الذهب في الإمارات</h1>
    <div id="gold-price" class="price">309.55 AED/g</div>
    <p id="update-time" class="update-time">آخر تحديث: 30 ديسمبر 2024 14:48</p>

    <div class="converter">
      <button id="convert-btn" onclick="convertToUSD()">تحويل السعر إلى الدولار (USD)</button>
      <p id="usd-output" class="usd-output">USD --</p>
    </div>
  </div>

  <script>
    let isArabic = true; // Arabic is the main language

    // Function to toggle the language
    function toggleLanguage() {
      const title = document.getElementById("title");
      const updateTime = document.getElementById("update-time");
      const convertBtn = document.getElementById("convert-btn");
      const langToggleBtn = document.querySelector(".language-toggle");

      if (isArabic) {
        // Switch to English
        title.textContent = "Gold Price in UAE";
        updateTime.textContent = "Last updated: December 30, 2024 14:48";
        convertBtn.textContent = "Convert price to USD";
        langToggleBtn.textContent = "AR";
      } else {
        // Switch back to Arabic
        title.textContent = "سعر الذهب في الإمارات";
        updateTime.textContent = "آخر تحديث: 30 ديسمبر 2024 14:48";
        convertBtn.textContent = "تحويل السعر إلى الدولار (USD)";
        langToggleBtn.textContent = "EN";
      }

      isArabic = !isArabic; // Toggle the language flag
    }

    function convertToUSD() {
      const aedPriceElement = document.getElementById('gold-price');
      const usdOutput = document.getElementById('usd-output');
      const exchangeRate = 3.67;
      
      const aedPrice = parseFloat(aedPriceElement.textContent.split(' ')[0]);
      const usdValue = (aedPrice / exchangeRate).toFixed(2);

      usdOutput.textContent = `$ ${usdValue} /g`;
    }
  </script>
</body>
</html>
