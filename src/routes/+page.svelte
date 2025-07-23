<script>
  // Optional: Add logic here if needed
</script>

<div class="header">
  <div class="left">
    <div class="menu-icon">☰</div>
    <div class="logo">MyLogo</div>
  </div>
  <div class="right">
    <button class="login">Login</button>
    <button class="signup">Sign Up</button>
    <div class="user-icon">👤</div>
  </div>
</div>

<main class="main">
  <div class="hero-text">We listen. For You. <br> Ingenious AI</div>
  <button class="record-btn">🎤 Record</button>
  <div class="upload-box">
    <div class="icon">⬆️</div>
    Drag & Drop to upload
  </div>
</main>

<style>
  :global(body) {
    background: #f7efde;
    font-family: "Inter", Arial, sans-serif;
    margin: 0;
  }

  .header {
    background: #7cc3b3;
    height: 60px;
    display: flex;
    align-items: center;
    padding: 0 24px;
    border-bottom: 2px solid #d2d2c7;
    justify-content: space-between;
  }

  .header .left {
    display: flex;
    align-items: center;
  }

  .menu-icon {
    width: 36px;
    height: 36px;
    border: 2px solid #222;
    border-radius: 6px;
    background: none;
    margin-right: 16px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .logo {
    font-weight: bold;
    letter-spacing: 2px;
    font-size: 1.2rem;
    margin-left: 8px;
  }

  .header .right {
    display: flex;
    align-items: center;
    gap: 16px;
  }

  .header .login {
    background: none;
    border: none;
    color: #222;
    font-size: 1rem;
    margin-right: 8px;
    cursor: pointer;
  }

  .header .signup {
    background: #fff;
    border: 2px solid #222;
    border-radius: 8px;
    padding: 7px 20px;
    font-size: 1rem;
    font-weight: bold;
    cursor: pointer;
    margin-right: 8px;
  }

  .header .user-icon {
    width: 32px;
    height: 32px;
    border: 2px solid #222;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #fff;
  }

  .main {
    max-width: 900px;
    margin: 40px auto 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .hero-text {
    background: #fff;
    border: 2px solid #222;
    border-radius: 24px;
    padding: 36px 48px;
    font-size: 2.5rem;
    font-weight: 500;
    margin-bottom: 32px;
    box-sizing: border-box;
    text-align: center;
  }

  .record-btn {
    background: #7cc3b3;
    color: #fff;
    border: 2px solid #222;
    border-radius: 30px;
    padding: 12px 34px;
    font-size: 1.1rem;
    font-weight: 500;
    box-shadow: 2px 2px 4px #c6c6ba;
    display: flex;
    align-items: center;
    gap: 8px;
    cursor: pointer;
    margin-bottom: 36px;
    transition: background 0.2s;
  }

  .record-btn:hover {
    background: #6ab2a1;
  }

  .upload-box {
    width: 500px;
    height: 220px;
    background: #f7efde;
    border: 2px solid #888;
    border-radius: 24px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: #888;
    font-size: 1.1rem;
    margin-top: 12px;
    box-sizing: border-box;
  }

  .upload-box .icon {
    font-size: 2.2rem;
    margin-bottom: 12px;
  }
</style>
