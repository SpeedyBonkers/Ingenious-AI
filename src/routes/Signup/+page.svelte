<script>
    let email = "";
    let password = "";
    let agree = false;
    let message = "";
  
    async function handleSubmit() {
      message = "";
      if (!email || !password || !agree) {
        message = "Please fill all fields and agree to the terms.";
        return;
      }
      try {
        const res = await fetch("http://localhost:3000/signup", {
          method: "POST",
          headers: { "Content-Type": "application/json" },
          body: JSON.stringify({ email, password, agree })
        });
        const data = await res.json();
        message = data.message;
      } catch (err) {
        message = "Server error.";
      }
    }
  </script>
  
  <style>
    body, :global(body) {
      background: #f7efde;
      font-family: 'Inter', Arial, sans-serif;
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
    .left {
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
      font-size: 1.5em;
    }
    .logo {
      font-weight: bold;
      letter-spacing: 2px;
      font-size: 1.2rem;
      margin-left: 8px;
    }
    .right {
      display: flex;
      align-items: center;
      gap: 16px;
    }
    .login, .signup {
      background: none;
      border: none;
      color: #222;
      font-size: 1rem;
      margin-right: 8px;
      cursor: pointer;
    }
    .signup {
      background: #fff;
      border: 2px solid #222;
      border-radius: 8px;
      padding: 7px 20px;
      font-weight: bold;
      margin-right: 8px;
    }
    .user-icon {
      width: 32px;
      height: 32px;
      border: 2px solid #222;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      background: #fff;
      font-size: 1.1em;
    }
    .signup-container {
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-top: 70px;
    }
    .signup-title {
      font-size: 3rem;
      font-weight: 500;
      letter-spacing: 2px;
      text-align: center;
      margin-bottom: 16px;
      margin-top: 24px;
      border-bottom: 3px solid #222;
      width: 370px;
      padding-bottom: 8px;
    }
    .signup-box {
      background: #fff;
      border-radius: 8px;
      box-shadow: 2px 2px 6px #d3d3c7;
      padding: 28px 32px;
      min-width: 320px;
      max-width: 370px;
      margin-bottom: 22px;
      border: 1px solid #d2d2c7;
      display: flex;
      flex-direction: column;
      gap: 14px;
    }
    .signup-box label {
      font-size: 1rem;
      margin-bottom: 2px;
    }
    .signup-box input[type="email"],
    .signup-box input[type="password"] {
      width: 100%;
      padding: 7px 9px;
      border: 1.5px solid #ddd;
      border-radius: 4px;
      font-size: 1rem;
      margin-bottom: 10px;
    }
    .checkbox-row {
      display: flex;
      align-items: center;
      font-size: 0.95rem;
      margin-bottom: 8px;
      gap: 6px;
    }
    .signup-box input[type="checkbox"] {
      accent-color: #222;
      margin-right: 6px;
    }
    .signup-box button {
      background: #222;
      color: #fff;
      border: none;
      border-radius: 6px;
      padding: 8px 0;
      font-size: 1rem;
      font-weight: 500;
      cursor: pointer;
      margin-top: 8px;
      transition: background 0.2s;
    }
    .signup-box button:hover {
      background: #444;
    }
    .divider {
      width: 370px;
      height: 2px;
      background: #bdbdb2;
      margin: 18px 0 10px 0;
    }
    .login-section {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .login-section span {
      color: #222;
      font-size: 1rem;
      margin-bottom: 8px;
    }
    .login-section button {
      background: #222;
      color: #fff;
      border: none;
      border-radius: 8px;
      padding: 7px 18px;
      font-size: 1rem;
      cursor: pointer;
    }
    .message {
      color: #b00;
      margin-bottom: 10px;
      text-align: center;
    }
  </style>
  
  <div class="header">
    <div class="left">
      <button class="menu-icon">&#9776;</button>
      <span class="logo"><span style="font-size: 1.2em;">🎤</span> INGENIOUS</span>
    </div>
    <div class="right">
      <button class="login">Log in</button>
      <button class="signup">Sign up</button>
      <span class="user-icon">👤</span>
    </div>
  </div>
  
  <div class="signup-container">
    <div class="signup-title">Sign up</div>
    <form class="signup-box" on:submit|preventDefault={handleSubmit}>
      <label for="email">Email</label>
      <input id="email" type="email" bind:value={email} required />
  
      <label for="password">Password</label>
      <input id="password" type="password" bind:value={password} required />
  
      <div class="checkbox-row">
        <input id="agree" type="checkbox" bind:checked={agree} required />
        <label for="agree" style="margin-bottom:0;">I agree that my data finna get sold</label>
      </div>
  
      <button type="submit">Register</button>
      {#if message}
        <div class="message">{message}</div>
      {/if}
    </form>
  
    <div class="divider"></div>
  
    <div class="login-section">
      <span>Already have an account?</span>
      <button on:click={() => window.location.href='login.html'}>Log in</button>
    </div>
  </div>
  