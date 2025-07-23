<script>
  function click() {
    alert("404");
  }
</script>

<main>
  <div class="clickMe"></div>
  <button class="juli" on:click={click}>click</button>

  <div class="test">test test</div>

  <div class="moin">example</div>
  <div>baum</div>
</main>

<style>
  main {
    background: #ffffff;
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: space-around;
    padding: 0.4%;
    box-sizing: border-box;
  }

  .hallo {
    height: 20%;
    width: 50%;
    background-color: aqua;
    align-items: center;
    justify-content: space-around;
    display: flex;
  }

  .moin {
    background-color: #de1717;
    justify-content: center;
    align-items: center;
    height: 30%;
    width: 20%;
    display: flex;
  }

  .juli {
    height: 10%;
    justify-content: center;
  }
</style>
