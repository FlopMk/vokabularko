<script>
    import { text } from "svelte/internal";
    import App from "./App.svelte";
    let name = "";
  </script>
  
  <style>
    .inputName {
      margin: 0 auto;
      text-align: center;
      margin-top: 20%;
      opacity: 40rem;
    }
    .col {
      text-align: center;
    }
    .row {
        margin: 0 auto;
    }
  
    .container {
      margin: 50px auto;
    }
    .homeButtons {
      margin: auto;
    }
  
    .btn-group {
        margin: 40% auto;
    }
  </style>
  <body>
  <div class="container">
    <div class="row">
      <div class="col"><img src="./logo.png" alt="Logo" width="75px" /></div>
      <div class="col">
        <h1>Граматика и вокабулар</h1>
      </div>
      <div class="col">
        <span><i class="fas fa-question-circle" /></span>
        <p>Помош</p>
      </div>
    </div>
    <div class="homeButtons">
      <div class="row">
        <div class="col-2" />
        <div class="col-8">
          <div
            class="btn-toolbar justify-content-between"
            role="toolbar"
            aria-label="Toolbar with button groups">
            <div class="btn-group" role="group" aria-label="First group">
              <button type="button" class="btn btn-primary-outline">Граматика низ примери</button>
              <button type="button" class="btn btn-primary-outline">Поврзи ја сликата со зборот</button>
            </div>
          </div>
        </div>
        <div class="col-2" />
      </div>
    </div>
  </div>
</body>
  