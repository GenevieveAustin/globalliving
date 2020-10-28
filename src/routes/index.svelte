<script>
  import { stores } from "@sapper/app";
  const { session } = stores();

  import { goto } from "@sapper/app";

  let email = "";
  let mailFormat = /^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/;
  let emailAlertOn = false;

  function toggleEmailAlert() {
    emailAlertOn = !emailAlertOn;
  }

  function validateEmail() {
    if (!email.match(mailFormat)) {
      console.log("ALERT");
      toggleEmailAlert();
    } else if (email === "") {
      toggleEmailAlert();
    } else {
      console.log("GETTING DATA");
      getData();
    }
  }

  async function getData() {
    // let data = localStorage.getItem(email)
    let personDoc = await db
      .collection("People")
      .doc(email)
      .get();
    session.details = personDoc.data();
    if (session.details == undefined) {
      console.log("UNDEF");
      session.details = {
        email: email,
        year: "",
        class: ""
      };
      goto("yearSelect");
    } else {
      console.log("ELSE");
      goto("output");
    }
  }
</script>

<style>
  .box {
    width: 20em;
    margin: auto;
  }
  .next-button {
    margin-left: 210px;
    margin-top: 10px;
  }
</style>

<h1 class="title has-text-centered">Log in</h1>

<div class="box">

  <label>
    Please enter your email address:
    <input class="input" type="email" placeholder="Name" bind:value={email} />
  </label>

  <button class="button next-button is-primary" on:click={validateEmail}>
    Next
  </button>

</div>

<div class="modal" class:is-active={emailAlertOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Error</p>
      <button class="delete" aria-label="close" on:click={toggleEmailAlert} />
    </header>
    <section class="modal-card-body">
      <b>Please enter a valid email address.</b>
      <br />
      You're recieving this error because you haven't entered an email address,
      or you simply have incorrectly entered your address.
    </section>
    <footer class="modal-card-foot">
      <button class="button is-primary" on:click={toggleEmailAlert}>
        Return
      </button>
    </footer>
  </div>
</div>
