<script>
    let fileType = 'txt';
  </script>
  
  <div class="header">
    <div class="menu-icon">&#9776;</div>
    <div class="logo">
      <span style="margin-right:8px;">🎤</span>
      INGENIOUS
    </div>
    <div class="header-buttons">
      <button>Log in</button>
      <button class="signup-btn">Sign up</button>
      <span style="margin-left:10px;">&#9679;</span>
    </div>
  </div>
  
  <div class="main-title">
    We listen. For you.<br>
    Ingenious AI.
  </div>
  
  <div class="download-options">
    <div class="download-option">
      <div class="icon txt">&#128196;</div>
      <label>
        <input type="radio" bind:group={fileType} value="txt">
        Download as .txt file
      </label>
    </div>
    <div class="download-option">
      <div class="icon pdf" style="color:#ff2222;">&#128196;</div>
      <label>
        <input type="radio" bind:group={fileType} value="pdf">
        Download as .pdf file
      </label>
    </div>
  </div>
  
  <button class="download-btn">
    <span style="font-size:1.5em;vertical-align:middle;">&#8681;</span>
    Download files
  </button>
  
  <style>
    .body {
      background: #f8f1e1;
      font-family: 'Montserrat', Arial, sans-serif;
      margin: 0;
      padding: 0;
    }
    .header {
      background: #77c3be;
      border: 2px solid #333;
      border-bottom: none;
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 70px;
      padding: 0 30px;
      box-sizing: border-box;
    }
    .logo {
      display: flex;
      align-items: center;
      font-family: 'Montserrat', Arial, sans-serif;
      font-weight: bold;
      font-size: 1.2em;
      letter-spacing: 2px;
    }
    .menu-icon {
      font-size: 2em;
      margin-right: 15px;
      cursor: pointer;
    }
    .header-buttons {
      display: flex;
      gap: 10px;
      align-items: center;
    }
    .header-buttons button,
    .header-buttons .signup-btn {
      background: #fff;
      border: 1px solid #333;
      border-radius: 8px;
      padding: 8px 18px;
      font-size: 1em;
      cursor: pointer;
      transition: background 0.2s;
    }
    .header-buttons .signup-btn {
      background: #fff;
      font-weight: bold;
    }
    .header-buttons button:hover,
    .header-buttons .signup-btn:hover {
      background: #e6e6e6;
    }
    .main-title {
      margin: 60px auto 30px auto;
      max-width: 700px;
      background: #fff8f0;
      border: 2px solid #333;
      border-radius: 32px;
      padding: 40px 30px;
      text-align: center;
      font-size: 3em;
      font-family: 'Montserrat', Arial, sans-serif;
      font-weight: 500;
      letter-spacing: 2px;
      box-sizing: border-box;
    }
    .download-options {
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 30px auto 0 auto;
      max-width: 600px;
      background: #fff8f0;
      border: 2px solid #333;
      border-radius: 32px;
      box-sizing: border-box;
      overflow: hidden;
    }
    .download-option {
      flex: 1;
      text-align: center;
      padding: 40px 0 30px 0;
      position: relative;
    }
    .download-option:not(:last-child) {
      border-right: 2px solid #333;
    }
    .download-option .icon {
      font-size: 2.5em;
      margin-bottom: 10px;
      display: block;
      color: #8000ff;
    }
    .download-option .icon.pdf {
      color: #ff2222;
    }
    .download-option label {
      font-size: 0.95em;
      color: #222;
    }
    .download-btn {
      display: block;
      margin: 40px auto 0 auto;
      background: #77c3be;
      border: 2px solid #333;
      border-radius: 24px;
      padding: 16px 40px;
      font-size: 1.1em;
      color: #fff;
      font-weight: 500;
      cursor: pointer;
      box-shadow: 2px 4px 6px #8883;
      transition: background 0.2s, box-shadow 0.2s;
    }
    .download-btn:hover {
      background: #5ea7a0;
      box-shadow: 2px 6px 12px #8885;
    }
  </style>
  