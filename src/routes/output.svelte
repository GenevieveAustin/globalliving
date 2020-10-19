<script>
  import { stores } from "@sapper/app";
  const { session } = stores();

  function savePerson() {
    console.log(JSON.stringify(session.details))
    //let data = JSON.stringify(session.details)
    //localStorage.setItem(session.details.email, data)
    db.collection('People').doc(session.details.email).set(session.details)
  }

</script>

<style>
  img {
    width: 32px;
    height: 32px;
  }
  div {
    width: 20em;
    margin: auto;
  }
  .button{
      margin-left: 200px;
      margin-right: 10px;
      margin-top: 10px;
  }
</style>

{#if session.year == 'Year Twelve'}
  <a href="twelveChoices">
    <img src="/back.png" alt="Back" />
  </a>
{:else}
  <a href="thirteenChoices">
    <img src="/back.png" alt="Back" />
  </a>
{/if}

<div class="box">
  <h1>Email: {session.details.email}</h1>
  <h1>Year Level: {session.details.year}</h1>
  <h1>Class Selection: {session.details.class}</h1>
  <a class="button is-primary" on:click={savePerson} href=".">Confirm</a>
</div>


