<script>
    import { text } from "svelte/internal";
    import App from "./App.svelte";
    let name = "";
    let txt = "";
  </script>
  
  <style>
    .inputName {
      margin: 0 auto;
      text-align: center;
      margin-top: 10%;
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
        margin: 0 auto;
    }

    div.txt {
        font-size: 16px;
        margin: 0 auto;
    }
    input.naslov {
        background-color: beige;
        font-size: 26px;
        text-align: center;
    }
    textarea {
        width: 100%;
        height: 300px;
    }
  </style>
  
  <div class="container">
    <div class="row">
      <div class="col"><img src="./logo.png" alt="Logo" width="75px" /></div>
      <div class="col">
        <h1>Прочитај краток текст</h1>
      </div>
      <!-- sakam ushe edno kopche tuka za back ali ne mozham da go namestam ubavo, se unishtuva.....-->
      <div class="col">
        <span><i class="fas fa-question-circle" /></span>
        <p>Помош</p>
      </div>
    </div>
    <div class="inputName"><input class="naslov" bind:value={name} placeholder='Внеси наслов' type="text" /></div>
    <!-- nz ova kako  da go zgolemam  osven so fiksni vrednosti sho ne e okej-->
    <div class="inputName"><textarea bind:value={txt} placeholder='Пишувај тука'></textarea></div>
    <div class="homeButtons">
      <div class="row">
        <div class="col-2" />
        <div class="col-8">
          <div
            class="btn-toolbar justify-content-between"
            role="toolbar"
            aria-label="Toolbar with button groups">
            <div class="btn-group" role="group" aria-label="First group">
              <button type="button" class="btn btn-primary-outline">Претходна страна</button>
              <button type="button" class="btn btn-primary-outline">Следна страна</button>
            </div>
          </div>
        </div>
        <div class="col-2" />
      </div>
    </div>
  </div>
  