<script>
  import Nav from "./Nav.svelte";
  let hex = "#";
  $: cleanedHEX = hex.replace(/#/, "");
  $: r = parseInt("0x" + cleanedHEX.slice(0, 2));
  $: g = parseInt("0x" + cleanedHEX.slice(2, 4));
  $: b = parseInt("0x" + cleanedHEX.slice(4, 6));
  $: a =
    Math.round((parseInt("0x" + cleanedHEX.slice(6, 8)) / 256) * 100, 2) / 100;

  $: rgba = `rgb${a ? "a" : ""}(${r ? r : 0}, ${g ? g : 0}, ${b ? b : 0}${
    a ? `, ${a}` : ""
  })`;
</script>

<style lang="scss">
  @import "../scss/_definition.scss";
  .container {
    width: 100%;
    min-height: 100%;
    background-color: #292931;
    @include custom-flex(center, flex-start, column);

    section.sass {
      width: 1040px;
      margin-top: 32px;
      @include custom-flex(flex-start, space-between);
      .box {
        width: 500px;
        padding: 24px;
        background-color: rgba(255, 255, 255, 0.1);

        .title {
          color: white;
          margin-bottom: 16px;
          font-size: 24px;
          font-weight: 100;
        }
        label {
          margin-bottom: 4px;
          width: fit-content;
          background: var(--background);
          background-clip: text;
          font-size: 20px;
          font-weight: 100;
          -webkit-background-clip: text;
          color: transparent;
          background-size: 100%;
          background-position: center;
        }
        input {
          background-color: rgba(255, 255, 255, 0.1);
          width: 100%;
          height: 48px;
          font-weight: 100;
          font-size: 20px;
          color: white;
          &:focus {
            outline: none;
            background-color: rgba(255, 255, 255, 0.2);
          }
        }
        textarea {
          background-color: rgba(255, 255, 255, 0.1);
          width: 100%;
          height: 48px;
          font-weight: 100;
          font-size: 20px;
          color: white;
          &:focus {
            outline: none;
            background-color: rgba(255, 255, 255, 0.2);
          }
        }
      }
    }
  }
</style>

<div class="container">
  <Nav />
  <section class="sass">
    <div class="box">
      <div class="title">HEX</div>
      <input type="text" bind:value={hex} />
    </div>
    <div class="box">
      <div class="title">RGBA</div>

      <label
        style="--background: linear-gradient(90deg, rgb(255,69,58) 0%, rgb(255,55,95) 100%);">red</label>
      <textarea readonly class="line">{r ? r : 0}</textarea>
      <label
        for=""
        style="--background: linear-gradient(90deg, rgb(48,209,88) 0%, rgb(52,199,89) 100%);">green</label>
      <textarea readonly class="line">{g ? g : 0}</textarea>
      <label
        for=""
        style="--background: linear-gradient(90deg, rgb(10,132,255) 0%, rgb(94,92,230) 100%);">blue</label>
      <textarea readonly class="line">{b ? b : 0}</textarea>
      <label
        for=""
        style="--background: linear-gradient(90deg, #ffffff 0%, #aaaaaa 100%);">alpha</label>
      <textarea readonly class="line">{a ? a : 0}</textarea>
      <label
        for=""
        style="--background: linear-gradient(90deg, rgb(100,210,255) 0%, rgb(255,214,10) 50%, rgb(191,90,242) 100%);">rgba</label>
      <textarea readonly>{rgba}</textarea>
    </div>
  </section>
</div>
