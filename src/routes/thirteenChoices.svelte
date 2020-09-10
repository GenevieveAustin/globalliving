<script>
  import { stores } from "@sapper/app";
  const { session } = stores();

  /* Sets up modals for buttons
  All toggle 'true' when button is pressed
  */
  let perfTechModalOn = false;
  let specialModalOn = false;
  let enterpriseModalOn = false;
  let iceModalOn = false;
  let recModalOn = false;
  let ddModalOn = false;
  let btgModalOn = false;
  let leadershipModalOn = false;
  let tikangaModalOn = false;
  //Individual functions for each modal toggle
  function togglePerfTechModal() {
    perfTechModalOn = !perfTechModalOn;
  }
  function toggleSpecialModal() {
    specialModalOn = !specialModalOn;
  }
  function toggleEnterpriseModal() {
    enterpriseModalOn = !enterpriseModalOn;
  }
  function toggleICEModal() {
    iceModalOn = !iceModalOn;
  }
  function toggleRecModal() {
    recModalOn = !recModalOn;
  }
  function toggleDdModal() {
    ddModalOn = !ddModalOn;
  }
  function toggleBtgModal() {
    btgModalOn = !btgModalOn;
  }
  function toggleLeadershipModal() {
    leadershipModalOn = !leadershipModalOn;
  }
  function toggleTikangaModal() {
    tikangaModalOn = !tikangaModalOn;
  }
  // Sets the class selection of the student for output
  function selectBtg() {
    session.details.class = "Beyond the Gates";
  }
  function selectDefDrive() {
    session.details.class = "Defensive Driving";
  }
  function selectEnterprise() {
    session.details.class = "Enterprise";
  }
  function selectIce() {
    session.details.class = "ICE Productions";
  }
  function selectLeadership() {
    session.details.class = "Leadership and Communication";
  }
  function selectPerfTech() {
    session.details.class = "Performance Technology";
  }
  function selectRec() {
    session.details.class = "Recreation";
  }
  function selectSpecial() {
    session.details.class = "Special Project";
  }
  function selectTikanga() {
    session.details.class = "Tikanga";
  }
</script>

<style>
  .title {
    margin-right: auto;
    margin-left: auto;
    text-align: centre;
  }
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

<a href="yearSelect">
  <img src="/back.png" alt="Back" />
</a>

<h1 class="title has-text-centered">Year Thirteen Selection</h1>
<button class="button is-primary" on:click={toggleBtgModal}>
  Beyond The Gates
</button>
<button class="button is-primary" on:click={toggleDdModal}>
  Defensive Driving
</button>
<button class="button is-primary" on:click={toggleEnterpriseModal}>
  Enterprise
</button>
<button class="button is-primary" on:click={toggleICEModal}>
  ICE Productions
</button>
<button class="button is-primary" on:click={toggleLeadershipModal}>
  Leadership and Communication
</button>
<button class="button is-primary" on:click={togglePerfTechModal}>
  Performance Technology
</button>
<button class="button is-primary" on:click={toggleRecModal}>Recreation</button>
<button class="button is-primary" on:click={toggleSpecialModal}>
  Special Project
</button>
<button class="button is-primary" on:click={toggleTikangaModal}>Tikanga</button>

<div class="modal" class:is-active={btgModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button class="delete" aria-label="close" on:click={toggleBtgModal} />
    </header>
    <section class="modal-card-body">
      <b>You have selected Beyond the Gates.</b>
      <br />
      Allows students to plan their future, including guidance with scholarship
      applications, choosing references, and choosing courses.
    </section>
    <footer class="modal-card-foot">
      <a class="button is-primary" href="output" on:click={selectBtg}>
        Continue
      </a>
      <button class="button" on:click={toggleBtgModal}>Cancel</button>
    </footer>
  </div>
</div>

<div class="modal" class:is-active={ddModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button class="delete" aria-label="close" on:click={toggleDdModal} />
    </header>
    <section class="modal-card-body">
      <b>You have selected Defensive Driving.</b>
      <br />
      This is an AA 8 hour course run by an AA instructor. For more information
      please click
      <a
        href="https://www.aa.co.nz/drivers/learn-to-drive-the-aa-way/defensive-driving-courses/"
        target="_blank">
        here
      </a>
      .
      <br />
      <em>
        (Requirement: You must hold a current learner's license, and must pay
        the fee of $230)
      </em>
    </section>
    <footer class="modal-card-foot">
      <a class="button is-primary" href="output" on:click={selectDefDrive}>
        Continue
      </a>
      <button class="button" on:click={toggleDdModal}>Cancel</button>
    </footer>
  </div>
</div>

<div class="modal" class:is-active={enterpriseModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button
        class="delete"
        aria-label="close"
        on:click={toggleEnterpriseModal} />
    </header>
    <section class="modal-card-body">
      <b>You have selected Enterprise.</b>
      <br />
      This course allows you to take part in a Young Enterprise team for 1-3
      terms.
    </section>
    <footer class="modal-card-foot">
      <a class="button is-primary" href="output" on:click={selectEnterprise}>
        Continue
      </a>
      <button class="button" on:click={toggleEnterpriseModal}>Cancel</button>
    </footer>
  </div>
</div>

<div class="modal" class:is-active={iceModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button class="delete" aria-label="close" on:click={toggleICEModal} />
    </header>
    <section class="modal-card-body">
      <b>You have selected ICE Productions.</b>
      <br />
      An opportunity to share your voice with an audience. Examples include
      working on Shelter, Rangi News, film competitions, journalism etc.
    </section>
    <footer class="modal-card-foot">
      <a class="button is-primary" href="output" on:click={selectIce}>
        Continue
      </a>
      <button class="button" on:click={toggleICEModal}>Cancel</button>
    </footer>
  </div>
</div>

<div class="modal" class:is-active={leadershipModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button
        class="delete"
        aria-label="close"
        on:click={toggleLeadershipModal} />
    </header>
    <section class="modal-card-body">
      <b>You have selected Leadership and Communication.</b>
      <br />
      This three term course will support our student leaders in strengthening
      their skills towards effective leadership and communication.
      <br />
      <em>(Requirement: You must be a student leader to select this option)</em>
    </section>
    <footer class="modal-card-foot">
      <a class="button is-primary" href="output" on:click={selectLeadership}>
        Continue
      </a>
      <button class="button" on:click={toggleLeadershipModal}>Cancel</button>
    </footer>
  </div>
</div>

<div class="modal" class:is-active={perfTechModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button
        class="delete"
        aria-label="close"
        on:click={togglePerfTechModal} />
    </header>
    <section class="modal-card-body">
      <b>You have selected Performance Technology.</b>
      <br />
      This course will provide opportunities to work with lighting, sound,
      moving images or SFX make up.
    </section>
    <footer class="modal-card-foot">
      <a class="button is-primary" href="output" on:click={selectPerfTech}>
        Continue
      </a>
      <button class="button" on:click={togglePerfTechModal}>Cancel</button>
    </footer>
  </div>
</div>

<div class="modal" class:is-active={recModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button class="delete" aria-label="close" on:click={toggleRecModal} />
    </header>
    <section class="modal-card-body">
      <b>You have selected Recreation.</b>
      <br />
      An optional course for students to partake in physical activities of their
      choice. The focus is giving you the opportunity to enhance aspects of your
      wellbeing.
    </section>
    <footer class="modal-card-foot">
      <a class="button is-primary" href="output" on:click={selectRec}>
        Continue
      </a>
      <button class="button" on:click={toggleRecModal}>Cancel</button>
    </footer>
  </div>
</div>

<div class="modal" class:is-active={specialModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button class="delete" aria-label="close" on:click={toggleSpecialModal} />
    </header>
    <section class="modal-card-body">
      <b>You have selected Special Project.</b>
      <br />
      This is a course for students who wish to undertake a academic or personal
      project.
    </section>
    <footer class="modal-card-foot">
      <a class="button is-primary" href="output" on:click={selectSpecial}>
        Continue
      </a>
      <button class="button" on:click={toggleSpecialModal}>Cancel</button>
    </footer>
  </div>
</div>

<div class="modal" class:is-active={tikangaModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button class="delete" aria-label="close" on:click={toggleTikangaModal} />
    </header>
    <section class="modal-card-body">
      <b>You have selected Tikanga.</b>
      <br />
      Together we will approach our local marae, to learn and practice living
      tikanga. We organise weekly visits to support whanau.
    </section>
    <footer class="modal-card-foot">
      <a class="button is-primary" href="output" on:click={selectTikanga}>
        Continue
      </a>
      <button class="button" on:click={toggleTikangaModal}>Cancel</button>
    </footer>
  </div>
</div>
