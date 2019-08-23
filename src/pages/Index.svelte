<script>
  import DiceFace from '../components/DiceFace.svelte';
  let number;

  function makeFace() {
    number = Math.floor(Math.random() * 6 + 1);
  }
</script>

<style>
  .container {
    width: 100vw;
    height: 100vh;
  }

  .sub-container {
    position: absolute;
    top: 20%;
    width: 100%;
    text-align: center;
  }

  button {
    display: inline-block;
    padding: 0;
    background: transparent;
    margin: 0;
    border: transparent;
  }

  p {
    margin-bottom: 20px;
    font-size: 21px;
    font-weight: 600;
  }
</style>

<div class="container">
  <div class="sub-container">
    <p>You Smoked</p>

    <button on:click={makeFace}>
      <div class="dice-holder">
        <DiceFace name="dice-1" number={number} />
      </div>
    </button>
  </div>
</div>
