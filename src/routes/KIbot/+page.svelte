<script>

    // Initialisiere SpeechRecognition, wenn Komponente geladen wird
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
      }, 5000); // 2 seconds pause
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
    <button on:click={startRecognition} disabled={listening}>
        {listening ? 'Spricht...' : 'Sprache erkennen'}
      </button>
      <div>
        <strong>Erkannter Text:</strong>
        <p>{transcript}</p>
      </div>

  </main>



  <style>
    main{
        background-color: #fff;
        height: 100%;
        width: 100%;
    }

  </style>
  