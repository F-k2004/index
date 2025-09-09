<!-- index.html -->
<!DOCTYPE html>
<html lang="fa">
<ead>
  <meta charset="UTF-8">
  <title>🌐 بررسی وضعیت وبسایت</title>
  <style>
    body {
      font-family: sans-serif;
      text-align: center;
      background: linear-gradient(135deg, #89f7fe, #66a6ff);
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
    h1 {
      color: #222;
      margin-bottom: 20px;
    }
    input {
      width: 300px;
      padding: 10px;
      border-radius: 8px;
      border: 1px solid #ccc;
      margin-bottom: 10px;
      font-size: 16px;
    }
    button {
      padding: 10px 20px;
      border: none;
      border-radius: 8px;
      background: #333;
      color: white;
      font-size: 16px;
      cursor: pointer;
      transition: 0.3s;
    }
    button:hover {
      background: #555;
    }
    #result {
      margin-top: 20px;
      font-size: 18px;
      font-weight: bold;
      color: #222;
    }
  </style>
</head>
<body>
  <h1>🌐 بررسی وضعیت وبسایت</h1>
  <input type="text" id="url" placeholder="مثال: https://google.com">
  <button onclick="checkWebsite()">بررسی کن</button>
  <div id="result">نتیجه اینجا نمایش داده می‌شود...</div>

  <script>
    async function checkWebsite() {
      const url = document.getElementById("url").value.trim();
      const resultDiv = document.getElementById("result");

      if (!url) {
        resultDiv.textContent = "❌ لطفا آدرس وارد کنید.";
        return;
      }

      try {
        const response = await fetch(url, { mode: "no-cors" });
        resultDiv.textContent = `✅ ${url} در دسترس است.`;
      } catch (error) {
        resultDiv.textContent = `❌ ${url} در دسترس نیست.`;
      }
    }
  </script>
</body>
</html>
