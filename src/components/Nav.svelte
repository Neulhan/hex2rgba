<script>
</script>

<style lang="scss">
  @import "../scss/_definition.scss";
  nav {
    width: 1040px;
    .title {
      display: flex;
      font-size: 72px;
      font-weight: 900;
      color: white;
      .grd {
        background-clip: text;
        -webkit-background-clip: text;
        color: transparent;
        background-position: 58% 50%;
        background-size: 200%;
        animation: gradientMove;
        animation-duration: 30s;
        animation-iteration-count: infinite;
        animation-direction: alternate;
      }
      .hex {
        background: linear-gradient(
          120deg,
          #ff0000 0%,
          #292931 30%,
          #ff0000 100%
        );
        background-clip: text;
        -webkit-background-clip: text;
        color: transparent;
        background-position: 0% 50%;
        background-size: 1000%;
      }
      .rgba {
        background: linear-gradient(
          120deg,
          rgb(41, 41, 49) 10%,
          rgb(10, 132, 255) 20%,
          rgb(48, 209, 88) 30%,
          rgb(94, 92, 230) 40%,
          rgb(255, 159, 10) 50%,
          rgb(255, 55, 95) 60%,
          rgb(191, 90, 242) 70%,
          rgb(255, 69, 58) 80%,
          rgb(100, 210, 255) 90%,
          rgb(255, 214, 10) 100%
        );
        background-clip: text;
        -webkit-background-clip: text;
        color: transparent;
        background-position: 0% 50%;
        background-size: 1000%;
      }
    }
  }
  @keyframes gradientMove {
    from {
      background-position: 0% 50%;
    }
    to {
      background-position: 100% 50%;
    }
  }
</style>

<nav>
  <div class="title">
    <div class="hex grd">HEX</div>
    <div class="to">2</div>
    <div class="rgba grd">RGBA</div>
  </div>
</nav>
