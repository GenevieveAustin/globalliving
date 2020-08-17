<script>
  import { stores } from "@sapper/app";
  const { session } = stores();

  //Sets up modals for toggles
  let perfTechModalOn = false;
  let specialModalOn = false;
  let enterpriseModalOn = false;
  let ICEModalOn = false;
  let recModalOn = false;
  let svaModalOn = false;
  let sustainabilityModalOn = false;
  //Toggles modals on button click
  function togglePerfTechModal() {
    perfTechModalOn = !perfTechModalOn;
  }
  function toggleSpecialModal() {
    specialModalOn = !specialModalOn;
  }
  function toggleEnterpriseModal(){
    enterpriseModalOn = !enterpriseModalOn;
  }
  function toggleICEModal(){
    ICEModalOn = !ICEModalOn;
  }
  function toggleRecModal(){
    recModalOn = !recModalOn;
  }
  function toggleSvaModal(){
    svaModalOn = !svaModalOn;
  }
  function toggleSustainabilityModal(){
    sustainabilityModalOn = !sustainabilityModalOn;
  }
  //Sets class selection for output
  function selectEnterprise(){
    session.class = "Enterprise"
  }
  function selectIce(){
    session.class = "ICE Productions"
  }
  function selectPerfTech(){
    session.class = "Performance Technology"
  }
  function selectRec(){
    session.class = "Recreation"
  }
  function selectSpecial(){
    session.class = "Special Project"
  }
  function selectSustainability(){
    session.class = "Sustainability"
  }
  function selectSva(){
    session.class = "SVA"
  }
</script>

<style>

.button{
    display: block;
    margin: 10px;
}

</style>

<h1 class="title">Year Twelve Selection</h1>
<button class="button" on:click={toggleEnterpriseModal}>Enterprise</button>
<button class="button" on:click={toggleICEModal}>ICE Productions</button>
<button class="button" on:click={togglePerfTechModal}>Performance Technology</button>
<button class="button" on:click={toggleRecModal}>Recreation</button>
<button class="button" on:click={toggleSpecialModal}>Special Project</button>
<button class="button" on:click={toggleSustainabilityModal}>Sustainability</button>
<button class="button" on:click={toggleSvaModal}>SVA</button>

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
    <section class="modal-card-body"><b>You have selected Enterprise.</b>
    <br> This course allows you to take part in a Young Enterprise team for 1-3 terms.
    </section>
    <footer class="modal-card-foot">
      <a class="button is-success" href="output" on:click={selectEnterprise}>Continue</a>
      <button class="button" on:click={toggleEnterpriseModal}>Cancel</button>
    </footer>
  </div>
</div>

<div class="modal" class:is-active={ICEModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button
        class="delete"
        aria-label="close"
        on:click={toggleICEModal} />
    </header>
    <section class="modal-card-body"><b>You have selected ICE Productions.</b>
    <br> An opportunity to share your voice with an audience. Examples include working on Shelter, Rangi News, film competitions, journalism etc.
    </section>
    <footer class="modal-card-foot">
      <a class="button is-success" href="output" on:click={selectIce}>Continue</a>
      <button class="button" on:click={toggleICEModal}>Cancel</button>
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
    <section class="modal-card-body"><b>You have selected Performance Technology.</b>
    <br> This course will provide opportunities to work with lighting, sound, moving images or SFX make up.
    </section>
    <footer class="modal-card-foot">
      <a class="button is-success" href="output" on:click={selectPerfTech}>Continue</a>
      <button class="button" on:click={togglePerfTechModal}>Cancel</button>
    </footer>
  </div>
</div>

<div class="modal" class:is-active={recModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button
        class="delete"
        aria-label="close"
        on:click={toggleRecModal} />
    </header>
    <section class="modal-card-body"><b>You have selected Recreation.</b>
    <br> An optional course for students to partake in physical activities of their choice. The focus is giving you the opportunity to enhance aspects of your wellbeing.
    </section>
    <footer class="modal-card-foot">
      <a class="button is-success" href="output" on:click={selectRec}>Continue</a>
      <button class="button" on:click={toggleRecModal}>Cancel</button>
    </footer>
  </div>
</div>

<div class="modal" class:is-active={specialModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button
        class="delete"
        aria-label="close"
        on:click={toggleSpecialModal} />
    </header>
    <section class="modal-card-body"><b>You have selected Special Project.</b>
    <br>This is a course for students who wish to undertake a academic or personal project.
    </section>
    <footer class="modal-card-foot">
      <a class="button is-success" href="output" on:click={selectSpecial}>Continue</a>
      <button class="button" on:click={toggleSpecialModal}>Cancel</button>
    </footer>
  </div>
</div>

<div class="modal" class:is-active={svaModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button
        class="delete"
        aria-label="close"
        on:click={toggleSvaModal} />
    </header>
    <section class="modal-card-body"><b>You have selected SVA.</b>
    <br>SVA in Year 12 allows students the time and space to collaboratively plan and implement service initiatives for our local and wider community.
    </section>
    <footer class="modal-card-foot">
      <a class="button is-success" href="output" on:click={selectSva}>Continue</a>
      <button class="button" on:click={toggleSvaModal}>Cancel</button>
    </footer>
  </div>
</div>

<div class="modal" class:is-active={sustainabilityModalOn}>
  <div class="modal-background" />
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Success</p>
      <button
        class="delete"
        aria-label="close"
        on:click={toggleSustainabilityModal} />
    </header>
    <section class="modal-card-body"><b>You have selected Sustainability.</b>
    <br>This course allows students to work on a sustainable project or initiative for our local or wider community.
    </section>
    <footer class="modal-card-foot">
      <a class="button is-success" href="output" on:click={selectSustainability}>Continue</a>
      <button class="button" on:click={toggleSustainabilityModal}>Cancel</button>
    </footer>
  </div>
</div>