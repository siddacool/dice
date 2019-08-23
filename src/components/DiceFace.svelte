<script>
  export let number = 1;
  export let name = 'dice-1';

  const faces = {
    '1': [ {top: '33', left: '33'} ],
    '2': [ {top: '55', left: '10'}, { top: '10', left: '56'} ],
    '3': [ {top: '55', left: '10'}, { top: '33', left: '33' }, { top: '10', left: '56'} ],
    '4': [ {top: '10', left: '10'}, { top: '10', left: '56'}, {top: '55', left: '10'}, { top: '55', left: '56'} ],
    '5': [ {top: '10', left: '10'}, { top: '10', left: '56'}, { top: '33', left: '33' }, {top: '55', left: '10'}, { top: '55', left: '56'} ],
    '6': [ {top: '10', left: '10'}, { top: '10', left: '32' }, { top: '10', left: '56'}, {top: '55', left: '10'}, { top: '55', left: '32' }, { top: '55', left: '56'} ],
  };
</script>

<style>
  .face {
    width: 80px;
    height: 80px;
    background: #bcbcbc;
    border-radius: 7px;
    display: inline-flex;
    justify-content: center;
    align-items: center;
    font-weight: 600;
    font-size: 20px;
    position: relative;
  }

  .dot {
    width: 15px;
    height: 15px;
    background: #000;
    border-radius: 50%;
    display: inline-block;
    position: absolute;
  }
</style>

<div class="face" data-name={name} data-number={number}>
  {#each faces[number.toString()] as face}
    <span class="dot" style={`top:${face.top}px; left:${face.left}px;`}></span>
  {/each}
</div>
