<script>
  import { stores } from "@sapper/app";
  const { session } = stores();

  import { goto } from "@sapper/app";

  let email = "";

  async function getDataFromLocal() {
    // let data = localStorage.getItem(email)
    let personDoc = await db.collection('People').doc(email).get()
    session.details = personDoc.data()
    if (session.details == undefined) {
      console.log("UNDEF")
      session.details = {
        email: email,
        year: "",
        class: ""
      };
      goto("yearSelect")
    } else {
      console.log("ELSE") 
      goto("output")
    }
  }

  function saveAndGo() {
    getDataFromLocal();
  }

</script>

<style>
  div {
    width: 20em;
    margin: auto;
  }
  .button {
    margin-left: 210px;
    margin-top: 10px;
  }
</style>

<h1 class="title has-text-centered">Log in</h1>

<div class="box">

  <label>
    Please enter your email address:
    <input class="input" type="text" placeholder="Name" bind:value={email} />
  </label>

  <button class="button is-primary" on:click={saveAndGo}>Next</button>

</div>
