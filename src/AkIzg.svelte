<script>
    import { text } from "svelte/internal";
    import App from "./App.svelte";
    let count = 0;
    let picked;
    let answers = {};
    let last = 0;
    let questions = [{
        title: "Микрофон",
        id: '1',
        options: [{
            title: "кро",
            value: "кро",
            true: 0
        }, {
            title: "Ми",
            value: "Ми",
            true: 1
        }, {
            title: "фон",
            value: "фон",
            true: 0
        }]
    }, {
        title: "Велосипед",
        id: '2',
        options: [{
            title: "си",
            value: "си",
            true: 0
        }, {
            title: "ло",
            value: "ло",
            true: 1
        }, {
            title: "пед",
            value: "пед",
            true: 0
        }, {
            title: "Ве",
            value: "Ве",
            true: 0
        }]
    }, {
        title: "Кондураџија",
        id: '3',
        options: [{
            title: "ду",
            value: "ду",
            true: 0
        }, {
            title: "Кон",
            value: "Кон",
            true: 0
        }, {
            title: "ра",
            value: "ра",
            true: 1
        }, {
            title: "ја",
            value: "ја",
            true: 0
        }, {
            title: "џи",
            value: "џи",
            true: 0
        }]
    }];
    let activeQuestion = 0;
    $: question = questions[activeQuestion];
    function dec() {
        if (activeQuestion === 0) { return }
        activeQuestion -= 1
        picked = undefined
    }
    function inc() {
        if (activeQuestion === (questions.length - 1)) { last = 1; picked = undefined; correctAnswers(); return }
        activeQuestion += 1
        picked = undefined
    }
    function correctAnswers() {
        for (let i = 0; i < questions.length; i++)
        if (answers[i] == 1)
        count++
    }
    function check(answ) {
        picked = answ
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
    {#if !last}
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
                    <!--<input type=radio 
                                 name={question.id} 
                                 value={option.value}
                                 on:change={() => answers[question.id] = option.value}
                                 checked={answers[question.id] == option.value}
                                 on:click={check(option.true)}
                                 /> -->

                        <input type=radio 
                                 name={question.id} 
                                 value={option.value}
                                 on:change={() => answers[question.id] = option.true}
                                 checked={answers[question.id] == option.true}
                                 on:click={check(option.true)}
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
    {/if}
    {#if picked}
        <div class="col"><h2>Точен одговор!</h2></div>
    {:else if picked == 0}
        <div class="col"><h2>Погрешен одговор!</h2></div>
    {/if}
    {#if last}
        {#if count}
            <div class="col"><h2>Браво точно одговори на {count} прашање</h2></div>
        {:else}
            <div class="col"><h2>Браво точно одговори на {count} прашања</h2></div>
        {/if}
    {/if}
  </div>
  