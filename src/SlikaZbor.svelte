<script>
    import { text } from "svelte/internal";
    import App from "./App.svelte";
    let count;
    let answers = {};
    let questions = [{
        title: "./lav.png",
        id: '1',
        options: [{
            title: "Мачка",
            value: "Мачка"
        }, {
            title: "Куче",
            value: "Куче"
        }, {
            title: "Лав",
            value: "Лав"
        }, {
            title: "Тигар",
            value: "Тигар"
        }]
    }, {
        title: "./cat.png",
        id: '2',
        options: [{
            title: "Мачка",
            value: "Мачка"
        }, {
            title: "Куче",
            value: "Куче"
        }, {
            title: "Лав",
            value: "Лав"
        }, {
            title: "Тигар",
            value: "Тигар"
        }]
    }, {
        title: "./kuche.png",
        id: '3',
        options: [{
            title: "Мачка",
            value: "Мачка"
        }, {
            title: "Куче",
            value: "Куче"
        }, {
            title: "Лав",
            value: "Лав"
        }, {
            title: "Тигар",
            value: "Тигар"
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
    textarea {
        width: 100%;
        height: 300px;
    }
  </style>
  
  <div class="container">
    <div class="row">
      <div class="col"><img src="./logo.png" alt="Logo" width="75px" /></div>
      <div class="col">
        <h1>Поврзи ја сликата со зборот</h1>
      </div>
      <!-- sakam ushe edno kopche tuka za back ali ne mozham da go namestam ubavo, se unishtuva.....-->
      <div class="col">
        <span><i class="fas fa-question-circle" /></span>
        <p>Помош</p>
      </div>
    </div>
    <div class="row">
        <button type="button" class="btn btn-primary-outline" on:click={dec}>Претходно прашање</button>
        <div class="col"><img src={question.title} alt="pogodi" style="width:40%;"/></div>
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
  