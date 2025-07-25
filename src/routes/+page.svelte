<script>
  
  function handlepage1() {
    window.location.href = "/Login"
  }
  
function handlepage2() {
  window.location.href = "/Signup"
}

  function handlepage3() {
    window.location.href = "/Record"
  }
  let recognition;
let listening = false;
let transcript = '';
let pauseTimeout;

if (typeof window !== 'undefined') {
  const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
  if (SpeechRecognition) {
    recognition = new SpeechRecognition();
    recognition.lang = 'de-DE';
    recognition.interimResults = false;
    recognition.maxAlternatives = 1;
    recognition.continuous = true;

    recognition.onresult = (event) => {
      transcript = event.results[event.results.length - 1][0].transcript;
      // Reset pause timer on every result
      clearTimeout(pauseTimeout);
      pauseTimeout = setTimeout(() => {
        recognition.stop();
        listening = false;
      }, 2000); // 2 seconds pause
    };

    recognition.onerror = (event) => {
      transcript = 'Fehler: ' + event.error;
      listening = false;
      clearTimeout(pauseTimeout);
    };

    recognition.onend = () => {
      listening = false;
      clearTimeout(pauseTimeout);
    };
  }
}

function startRecognition() {
  if (recognition) {
    transcript = '';
    listening = true;
    recognition.start();
  } else {
    transcript = 'Web Speech API wird von diesem Browser nicht unterstützt.';
  }
}

</script>

<main>
  <div class="header">
 
  <div class="left">
    <div class="menu-icon">☰</div>
    <div class="logo">
      <main>
        <img src="/Ingenious.png" alt="Ingenious AI" />
      </main>
    </div>
  </div>
  
  <div class="right">
    <button class="login" on:click={handlepage1}>Login</button>
    <button class="signup" on:click={handlepage2}>Sign Up</button>
    <div class="user-icon">👤</div>
  </div>
  
</div>

<main class="main">

    {#if transcript != ""}
    <div class="hero-text">  {transcript} </div>
    {:else}
     <div class="hero-text"> We listen. For You. <br /> Ingenious AI</div>
    {/if}

  <button class="record-btn"  on:click= {startRecognition} disabled={listening}>🎤 Record</button>
  <div class="upload-box">
    <div class="icon">⬆️</div>
    Drag & Drop to upload
  </div>
</main>
</main>

<style>
  :global(body) {
    background-color: #efe9e0;
    font-family: "Numans", Arial, sans-serif;
    margin: 0;
    overflow-y: auto;
  }

  .main {
    background-color: #efe9e0;
    max-width: auto;
    height: auto;
    padding-top: 5%;
    padding-bottom: 5%;
    display: flex;
    flex-direction: column;
    align-items: center;
    overflow-y: auto;
  }

  .header {
    background: #0f9e99;
    min-height: 60px;
    display: flex;
    align-items: center;
    padding: 0px 24px;
    border-bottom: 2px solid #efe9e0;
    justify-content: space-between;
  }

  .header .left {
    display: flex;
    align-items: left;
  }

  .menu-icon {
    width: 36px;
    height: 36px;
    border: 2px solid #222;
    border-radius: 6px;
    background: none;
    margin-right: 16px;
    margin-top: auto;
    margin-bottom: auto;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
  }

  .logo {
    width: 30%;
    cursor: pointer;
  }

  .header .right {
    display: flex;
    align-items: center;
    gap: 20px;
  }

  .header .login {
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
    height: 35px;
    width: 100px;
    border-radius: 8px;
    padding: 5px 16px;
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
    background: #0f9e99;
    color: #fff;
    border: 2px solid #222;
    border-radius: 30px;
    padding: 12px 34px;
    font-size: 1.1rem;
    font-weight: 500;
    box-shadow: 2px 2px 4px #4f4f4f;
    display: flex;
    align-items: center;
    gap: 8px;
    cursor: pointer;
    margin-bottom: 36px;
    transition: background 0.3s;
  }

  .record-btn:hover {
    background: #0a6865;
  }

  .upload-box {
    width: 500px;
    height: 220px;
    background: #d0d0d0;
    border: 2px solid #888;
    border-radius: 24px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: #000000;
    font-size: 1.5rem;
    margin-top: 12px;
    box-sizing: border-box;
  }

  .upload-box .icon {
    font-size: 2.6rem;
    margin-bottom: 12px;
  }
</style>
