<script>
  const randomFace = () => Math.floor(Math.random() * 6 + 1);
  let number = randomFace();

  function rollDice() {
    number = randomFace();
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
    transition: transform 600ms;
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
    background: radial-gradient(circle, rgba(231,76,60,1) 0%, rgba(252,133,121,.8) 100%);
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

  .dot {
    width: 50px;
    height: 50px;
    background: #fff;
    display: inline-block;
    border-radius: 50%;
  }

  .face-inner {
    position: relative;
    display: flex;
    padding: 10px;
    height: 100%;
  }

  /* Face 1 */
  .front .face-inner {
    justify-content: center;
    align-items: center;
  }

  /* Face 2 */
  .top .face-inner .dot:nth-child(2) {
    position: absolute;
    right: 10px;
    bottom: 10px;
  }

  /* Face 3 */
  .left .face-inner .dot:nth-child(2) {
    position: absolute;
    top: calc(50% - 25px);
    left: calc(50% - 25px);
  }

  .left .face-inner .dot:nth-child(3) {
    position: absolute;
    right: 10px;
    bottom: 10px;
  }

  /* Face 4 */
  .right .face-inner .dot:nth-child(2) {
    position: absolute;
    right: 10px;
    top: 10px;
  }

  .right .face-inner .dot:nth-child(3) {
    position: absolute;
    left: 10px;
    bottom: 10px;
  }

  .right .face-inner .dot:nth-child(4) {
    position: absolute;
    right: 10px;
    bottom: 10px;
  }

  /* Face 5 */
  .bottom .face-inner .dot:nth-child(2) {
    position: absolute;
    right: 10px;
    top: 10px;
  }

  .bottom .face-inner .dot:nth-child(3) {
    position: absolute;
    top: calc(50% - 25px);
    left: calc(50% - 25px);
  }

  .bottom .face-inner .dot:nth-child(4) {
    position: absolute;
    left: 10px;
    bottom: 10px;
  }

  .bottom .face-inner .dot:nth-child(5) {
    position: absolute;
    right: 10px;
    bottom: 10px;
  }

  /* Face 6 */
  .back .face-inner .dot:nth-child(2) {
    position: absolute;
    top: 10px;
    left: calc(50% - 25px);
  }

  .back .face-inner .dot:nth-child(3) {
    position: absolute;
    right: 10px;
    top: 10px;
  }

  .back .face-inner .dot:nth-child(4) {
    position: absolute;
    left: 10px;
    bottom: 10px;
  }

  .back .face-inner .dot:nth-child(5) {
    position: absolute;
    left: calc(50% - 25px);
    bottom: 10px;
  }

  .back .face-inner .dot:nth-child(6) {
    position: absolute;
    right: 10px;
    bottom: 10px;
  }
</style>

<div class="scene">
  <div class="cube" on:click={rollDice} style={`transform: translateZ(-100px) ${faces[number.toString()]};`}>
    <div class="face front">
      <div class="face-inner">
        <span class="dot"></span>
      </div>
    </div>
    <div class="face back">
      <div class="face-inner">
        <span class="dot"></span>
        <span class="dot"></span>
        <span class="dot"></span>
        <span class="dot"></span>
        <span class="dot"></span>
        <span class="dot"></span>
      </div>
    </div>
    <div class="face right">
      <div class="face-inner">
        <span class="dot"></span>
        <span class="dot"></span>
        <span class="dot"></span>
        <span class="dot"></span>
      </div>
    </div>
    <div class="face left">
      <div class="face-inner">
        <span class="dot"></span>
        <span class="dot"></span>
        <span class="dot"></span>
      </div>
    </div>
    <div class="face top">
      <div class="face-inner">
        <span class="dot"></span>
        <span class="dot"></span>
      </div>
    </div>
    <div class="face bottom">
      <div class="face-inner">
        <span class="dot"></span>
        <span class="dot"></span>
        <span class="dot"></span>
        <span class="dot"></span>
        <span class="dot"></span>
      </div>
    </div>
  </div>
</div>
