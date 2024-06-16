<template>
  <main>

    <div v-if="showModal" class="overlay">
      <div class="overlay__module">
        <textarea v-model="textArea" class="overlay__text" name="note" id="note" cols="30" rows="10"></textarea>
        <button class="overlay__btn" @click="addToArray(), showModal= !showModal ">Add Note</button>
      </div>
    </div>

    <div class="container">
      <header>
        <h1>Notes</h1>
        <button class="header__btn" ref="btn" @click="showModal = !showModal, rotateBtn(showModal)">+</button>
      </header>

      <div class="cards__container">
        <div v-for="el, index in textArray" :style="'background-color:'+ el.bg " :key="index" class="card">
          <p class="card__desc">{{ el.text }}</p>
          <p class="card__date">{{ el.date }}</p>
        </div>
      </div>
    </div>
  </main>
</template>





<script setup>
  import { ref, defineModel } from "vue";

  const showModal = ref(false)
  const btn = ref(null)
  let num = 1
  
  let textArea = defineModel()
  let textArray = ref([
    
  ])
  
  function rotateBtn(el){
    btn.value.style.transition = `o.5sec`
    btn.value.style.transform = `rotateZ(${45*num}deg)`
    num++
  }
  
  function addToArray(){

    if (textArea.value.length <= 5){
      alert('please, add a meaningful note')
    }
    else{
      const date = new Date()
  
      let valueToPush = ref({
        date: `${date.getUTCDate()}/${date.getMonth()}/${date.getFullYear()}`,
        text: textArea.value,
        bg: getRandomColor()
      })
  
      textArray.value.push(valueToPush.value)
      textArea.value = ""
      console.log(valueToPush.value.date);
    }

  }

  function getRandomColor() {
    return "hsl(" + Math.random() * 360 + ", 100%, 75%)";
  }

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

  .header__btn{
    border: none;
    font-size: 25px;
    padding: 10px;
    width: 50px;
    height: 50px;
    cursor: pointer;
    background-color: rgb(21, 20, 20);
    border-radius: 100%;
    color: #fff;
    z-index: 99;
  }

  .card{
    width: 225px;
    height: 225px;
    background-color: rgb(2237, 182, 44);
    padding: 10px;
    border-radius: 15px;
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    margin-right: 20px;
    margin-bottom: 20px;
    color: rgb(76, 76, 76);
  }
  
  .card__desc{
    font-family: 'Roboto';
    font-weight: bold;
  }
  
  .card__date{
    font-size: 12.5px;
    font-weight: bold;
  }

  .cards__container{
    display: flex;
    flex-wrap: wrap;
    font-weight: bold;
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