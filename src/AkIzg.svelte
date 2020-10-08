<script>
    import { text } from "svelte/internal";
    import App from "./App.svelte";
    let count;
    let answers = {};
    let questions = [{
        title: "Микрофон",
        id: '1',
        options: [{
            title: "кро",
            value: "кро"
        }, {
            title: "Ми",
            value: "Ми"
        }, {
            title: "фон",
            value: "фон"
        }]
    }, {
        title: "Велосипед",
        id: '2',
        options: [{
            title: "си",
            value: "си"
        }, {
            title: "ло",
            value: "ло"
        }, {
            title: "пед",
            value: "пед"
        }, {
            title: "Ве",
            value: "Ве"
        }]
    }, {
        title: "Кондураџија",
        id: '3',
        options: [{
            title: "Кон",
            value: "Кон"
        }, {
            title: "ду",
            value: "ду"
        }, {
            title: "ра",
            value: "ра"
        }, {
            title: "џи",
            value: "џи"
        }, {
            title: "ја",
            value: "ја"
        }]
    }];
    let activeQuestion = 0;
    $: question = questions[activeQuestion];
    function dec() {
        if (activeQuestion === 0) { return }
        activeQuestion -= 1
    }
    function inc() {
        if (activeQuestion === (questions.length - 1)) { return }
        activeQuestion += 1
    }
    function correctAnswers() {
        if (answers['1']='Лав')
        count++;
        if (answers['2']='Мачка')
        count++
        if (answers['3']='Куче')
        count++
        { return count }
    }

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
    .zbor  {
        text-align:center;
        margin: 0 auto;
        padding-top: 10%;
    }
  </style>
  
  <div class="container">
    <div class="row">
      <div class="col"><img src="./logo.png" alt="Logo" width="75px" /></div>
      <div class="col">
        <h1>Акцентирај и изговарај</h1>
      </div>
      <!-- sakam ushe edno kopche tuka za back ali ne mozham da go namestam ubavo, se unishtuva.....-->
      <div class="col">
        <span><i class="fas fa-question-circle" /></span>
        <p>Помош</p>
      </div>
    </div>
    <div class="row">
        <button type="button" class="btn btn-primary-outline" on:click={dec}>Претходно прашање</button>
        <div class="zbor"><h2>{question.title}</h2></div>
        <!-- nz ova kako  da go zgolemam  osven so fiksni vrednosti sho ne e okej-->
        <!--<button type="button" class="btn btn-primary-outline">Следно прашање</button>-->
        <button type="button" class="btn btn-primary-outline" on:click={inc}>Следно прашање</button>
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
            {#each question.options as option (option.value)}
                <label on:click>
                    <input type=radio 
                                 name={question.id} 
                                 value={option.value}
                                 on:change={() => answers[question.id] = option.value}
                                 checked={answers[question.id] == option.value}
                                 /> 
                    {option.title}
                </label>
            {/each}
            </div>
          </div>
        </div>
        <div class="col-2" />
      </div>
    </div>
  </div>
  