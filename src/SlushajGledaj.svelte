<script>
    import { text } from "svelte/internal";
    import App from "./App.svelte";
    let name = "";
    let txt = "";

    let videos = [{
        title: "Звучни и безвучни согласки",
        link: "https://www.youtube.com/embed/gtdpugeC4BY"
    }, {
        title: "Главни членови во реченицата",
        link: "https://www.youtube.com/embed/oJj4RzyfGFw"
    }, {
        title: "Правопис",
        link: "https://www.youtube.com/embed/x0SYmY2Z5ug"
    }];
    let activeVid = 0;
    $: video = videos[activeVid];
    function dec() {
        if (activeVid === 0) { return }
        activeVid -= 1
    }
    function inc() {
        if (activeVid === (videos.length - 1)) { return }
        activeVid += 1
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
    .videoCont {
        position: relative;
        width: 60%;
        height: 0;
        padding-bottom: 56.25%;
        margin: 0 auto;
    }
    .vid {
    position: absolute;
    width: 100%;
    height: 70%;
    text-align: center;
    margin-top: 0px;
    margin-right: auto;
    margin-bottom: 0px;
    margin-left: auto;
}
  </style>
  
  <div class="container">
    <div class="row">
      <div class="col"><img src="./logo.png" alt="Logo" width="75px" /></div>
      <div class="col">
        <h1>Слушај и Гледај</h1>
      </div>
      <!-- sakam ushe edno kopche tuka za back ali ne mozham da go namestam ubavo, se unishtuva.....-->
      <div class="col">
        <span><i class="fas fa-question-circle" /></span>
        <p>Помош</p>
      </div>
    </div>
    <div class="inputName"><h2>{video.title}</h2></div>
        <!-- nz ova kako  da go zgolemam  osven so fiksni vrednosti sho ne e okej-->
    <div class="row">
        <button type="button" class="btn btn-primary-outline" on:click={dec}>Претходно видео</button>
        <div class="videoCont"><iframe title={video.title} src={video.link} class="vid"></iframe></div>
        <button type="button" class="btn btn-primary-outline" on:click={inc}>Следно видео</button>
    </div>

  </div>
  