<template>
  <main>

    <div class="overlay">
      <div class="overlay__module">
        <textarea class="overlay__text" name="note" id="note" cols="30" rows="10"></textarea>
        <button class="overlay__btn">Add Note</button>
        <button class="overlay__btnClose">Close</button>
      </div>
    </div>

    <div class="container">
      <header>
        <h1>Notes</h1>
        <button>+</button>
      </header>

      <div class="cards__container">
        <div class="card">
          <p class="card__desc">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quasi beatae adipisci distinctio temporibus vero! Tempore autem nesciunt ducimus distinctio illum dolor, inventore placeat tempora sunt?</p>
          <p class="card__date"></p>
        </div>
        <div class="card">
          <p class="card__desc">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quasi beatae adipisci distinctio temporibus vero! Tempore autem nesciunt ducimus distinctio illum dolor, inventore placeat tempora sunt?</p>
          <p class="card__date"></p>
        </div>
      </div>
    </div>
  </main>
</template>





<script setup>

</script>








<style scoped>
  main{
    height: 100v;
    width: 100vw;
  }

  .container{
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  
    max-width: 1000px;
    padding: 10px;
    margin: 0 auto;
    width: 100%;
  }

  header{
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  h1{
    font-weight: bold;
    margin-bottom: 25px;
    font-size: 75px;
    }

  header button{
    border: none;
    font-size: 25px;
    padding: 10px;
    width: 50px;
    height: 50px;
    cursor: pointer;
    background-color: rgb(21, 20, 20);
    border-radius: 100%;
    color: #fff;
  }

  .card{
    width: 225px;
    height: 225px;
    background-color: rgb(2237, 182, 44);
    padding: 10px;
    border-radius: 15px;
    display: flex;
    justify-content: space-between;
    margin-right: 20px;
    margin-bottom: 20px;
  }

  .card__date{
    font-size: 12.5px;
    font-weight: bold;
  }

  .cards__container{
    display: flex;
    flex-wrap: wrap;
  }


  .overlay{
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.77);
    z-index: 10;
    display: flex;
    align-items: center;
    justify-content: center;
    
    display: none;
  }

  .overlay__module{
    width: 750px;
    background-color: #fff;
    border-radius: 10px;
    padding: 30px;
    position: relative;
    display: flex;
    flex-direction: column;

    
  }

  .overlay__btn, .overlay__btnClose{
    border: none;
    padding: 10px 20px;
    font-size: 20px;
    width: 100%;
    background-color: blueviolet;
    cursor: pointer;
    margin-top: 15px;;
  }

  .overlay__btnClose{
    background-color: red;
  }
</style>