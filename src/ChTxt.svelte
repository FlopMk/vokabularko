<script>
    import { text } from "svelte/internal";
    import App from "./App.svelte";
    let name = "";
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
    <div class="inputName">
        <h2>Кралот лав</h2>
   </div>  <!-- ova so tekstov treba bolje da se smisli za da se integriraat kopchinjata (string lista i na sekoe klikanje ide .pop() ili kako i da se prai-->
    <div class="txt">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus ut nunc et lorem feugiat sollicitudin nec vitae nulla. Duis semper lorem sodales, efficitur ante et, imperdiet erat. Duis ultricies vulputate nisi accumsan tempor. Donec vulputate dui ex, vitae pharetra erat porta eget. Ut interdum augue felis, in elementum diam mattis et. Sed condimentum, ante ac sodales suscipit, libero neque aliquet turpis, ut lobortis nunc quam a elit. Nam rhoncus enim eu quam rhoncus interdum. Sed viverra, massa nec elementum maximus, augue justo molestie justo, ac luctus justo neque at velit. Sed convallis, neque porta hendrerit cursus, sem felis sodales nisl, in malesuada dolor mauris vel dolor. Suspendisse vestibulum blandit dui ac sagittis. Nullam vitae ligula at sem congue ultricies vel sed eros. Praesent aliquam, massa vitae porttitor malesuada, augue eros consequat nunc, non elementum felis dui non massa. Duis venenatis dui at ipsum suscipit tempor. Sed sagittis justo quis bibendum convallis.</div>
    <div class="txt">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus ut nunc et lorem feugiat sollicitudin nec vitae nulla. Duis semper lorem sodales, efficitur ante et, imperdiet erat. Duis ultricies vulputate nisi accumsan tempor. Donec vulputate dui ex, vitae pharetra erat porta eget. Ut interdum augue felis, in elementum diam mattis et. Sed condimentum, ante ac sodales suscipit, libero neque aliquet turpis, ut lobortis nunc quam a elit. Nam rhoncus enim eu quam rhoncus interdum. Sed viverra, massa nec elementum maximus, augue justo molestie justo, ac luctus justo neque at velit. Sed convallis, neque porta hendrerit cursus, sem felis sodales nisl, in malesuada dolor mauris vel dolor. Suspendisse vestibulum blandit dui ac sagittis. Nullam vitae ligula at sem congue ultricies vel sed eros. Praesent aliquam, massa vitae porttitor malesuada, augue eros consequat nunc, non elementum felis dui non massa. Duis venenatis dui at ipsum suscipit tempor. Sed sagittis justo quis bibendum convallis.</div>
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
  