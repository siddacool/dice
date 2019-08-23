<script>
  let number = 1;

  function rollDice() {
    number = Math.floor(Math.random() * 6 + 1);
  }

  const faces = {
    '1': 'rotateY(0deg)',
    '2': 'rotateX(-90deg)',
    '3': 'rotateY(90deg)',
    '4': 'rotateY(-90deg)',
    '5': 'rotateX(90deg)',
    '6': 'rotateY(-180deg)',
  };
</script>

<style>
  .scene {
    width: 200px;
    height: 200px;
    perspective: 600px;
    position: absolute;
    left: calc(50% - 100px);
    top: 18%;
  }

  .cube {
    width: 100%;
    height: 100%;
    position: relative;
    transform-style: preserve-3d;
    transform: translateZ(-100px);
    transition: transform 1s;
  }

  .face {
    display: inline-block;
    width: 200px;
    height: 200px;
    line-height: 200px;
    font-size: 40px;
    font-weight: bold;
    text-align: center;
    position: absolute;
    background: rgb(231,76,60);
    background: radial-gradient(circle, rgba(231,76,60,1) 0%, rgba(252,133,121,.7) 100%);
    border-radius: 10px;
    color: #fff;
  }

  .front {
    transform: rotateY(0deg) translateZ(100px);
  }

  .right {
    transform: rotateY( 90deg) translateZ(100px);
  }

  .back {
    transform: rotateY(180deg) translateZ(100px);
  }

  .left {
    transform: rotateY(-90deg) translateZ(100px);
  }

  .top {
    transform: rotateX( 90deg) translateZ(100px);
  }

  .bottom {
    transform: rotateX(-90deg) translateZ(100px);
  }
</style>

<div class="scene">
  <div class="cube" on:click={rollDice} style={`transform: translateZ(-100px) ${faces[number.toString()]};`}>
    <div class="face front">1</div>
    <div class="face back">6</div>
    <div class="face right">4</div>
    <div class="face left">3</div>
    <div class="face top">2</div>
    <div class="face bottom">5</div>
  </div>
</div>
