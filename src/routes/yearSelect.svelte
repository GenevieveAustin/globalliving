<script>
  import { stores } from "@sapper/app";
  const { session } = stores();

  //Sets up modals for button toggle
  let thirteenModalOn = false;
  let twelveModalOn = false;
  //Toggles modals on button click
  function toggleThirteenModal() {
    thirteenModalOn = !thirteenModalOn;
  }
  function toggleTwelveModal() {
    twelveModalOn = !twelveModalOn;
  }
  //Sets year selection for output
  function clickTwelve() {
    session.details.year = "Year Twelve";
  }

  function clickThirteen() {
    session.details.year = "Year Thirteen";
  }
</script>

<style>
  .button {
    display: block;
    margin: 10px auto;
    width: 20em;
  }
  img {
    width: 32px;
    height: 32px;
  }
</style>

<a href=".">
  <img src="/back.png" alt="Back" />
</a>

<h1 class="title has-text-centered">Year Level</h1>
<button class="button is-primary" on:click={toggleTwelveModal}>Year 12</button>
<button class="button is-primary" on:click={toggleThirteenModal}>
  Year 13
</button>

<div class="modal" class:is-active={twelveModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button class="delete" aria-label="close" on:click={toggleTwelveModal} />
    </header>
    <section class="modal-card-body">You have selected Year 12.</section>
    <footer class="modal-card-foot">
      <a class="button is-primary" href="twelveChoices" on:click={clickTwelve}>
        Continue
      </a>
      <button class="button" on:click={toggleTwelveModal}>Cancel</button>
    </footer>
  </div>
</div>

<div class="modal" class:is-active={thirteenModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button
        class="delete"
        aria-label="close"
        on:click={toggleThirteenModal} />
    </header>
    <section class="modal-card-body">You have selected Year 13.</section>
    <footer class="modal-card-foot">
      <a
        class="button is-primary"
        href="thirteenChoices"
        on:click={clickThirteen}>
        Continue
      </a>
      <button class="button" on:click={toggleThirteenModal}>Cancel</button>
    </footer>
  </div>
</div>
