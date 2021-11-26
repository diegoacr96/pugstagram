<div class="Loading">
  <div class="Loading-container">
    <span>Loading</span>
    <span class="dot-collision" />
  </div>
</div>

<style>
  .Loading {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 300px;
  }

  .Loading-container {
    display: flex;
    flex-direction: column;
    height: 100px;
    align-items: center;
    justify-content: space-evenly;
  }

  .dot-collision {
    position: relative;
    width: 10px;
    height: 10px;
    border-radius: 5px;
    background-color: #9880ff;
    color: #9880ff;
  }

  .dot-collision::before,
  .dot-collision::after {
    content: "";
    display: inline-block;
    position: absolute;
    top: 0;
  }

  .dot-collision::before {
    left: -10px;
    width: 10px;
    height: 10px;
    border-radius: 5px;
    background-color: #9880ff;
    color: #9880ff;
    animation: dotCollisionBefore 2s infinite ease-in;
  }

  .dot-collision::after {
    left: 10px;
    width: 10px;
    height: 10px;
    border-radius: 5px;
    background-color: #9880ff;
    color: #9880ff;
    animation: dotCollisionAfter 2s infinite ease-in;
    animation-delay: 1s;
  }

  @keyframes dotCollisionBefore {
    0%,
    50%,
    75%,
    100% {
      transform: translateX(0);
    }
    25% {
      transform: translateX(-15px);
    }
  }

  @keyframes dotCollisionAfter {
    0%,
    50%,
    75%,
    100% {
      transform: translateX(0);
    }
    25% {
      transform: translateX(15px);
    }
  }
</style>
