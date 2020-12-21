<template>
<h1>ROCK PAPER SCISSORS GAME</h1>
<div class="choosen">
  <button @click="choosePick('Rock')" class="button"><img src="./assets/rock.png" class="choose1"></button>
  <button @click="choosePick('Paper')" class="button"><img src="./assets/paper.png" class="choose2"></button>
  <button @click="choosePick('Scissor')"  class="button"><img src="./assets/scissors.png" class="choose3"></button>
</div>
<div class="score">
<div>
  Person
  <span class="score-d">{{person}}</span>
  </div>
  <div>
  Computer
  <span class="score-d">{{computer}}</span>
  </div>
  <div>
  {{yourPick}}
  </div>
  <div>
 {{computerPick}}
  </div>
  </div>
</template>

<script>


export default {
  data() {
    return {
    options: ['Rock', 'Paper', 'Scissors'],
    person: 0,
    computer: 0,
    computerPick: '',
    yourPick: '',
  }
  },
  methods: {
    choosePick(pick) {
   this.yourPick = pick
   
   this.fight(),
   this.setScore()
   
    },
  fight() {
    this.computerPick = this.options[Math.floor(Math.random() * this.options.length)];
    
  },
  setScore() {
if(this.computerPick === 'Rock' && this.yourPick === 'Paper') {
  return this.person++;
} else if (this.computerPick === 'Paper' && this.yourPick === 'Rock') {
  return this.computer++;
} else if (this.computerPick === 'Scissors' && this.yourPick === 'Rock') {
  return this.person++;
} else if (this.computerPick === 'Rock' && this.yourPick === 'Scissors') {
  return this.computer++;
} else if (this.computerPick === 'Paper' && this.yourPick === 'Scissors') {
  return this.person++;
} else if (this.computerPick === 'Scissors' && this.yourPick === 'Paper') {
  return this.computer++;
}
  },
  }
 
}
</script>

<style>

.button {
  background: none;
  border: none;
  outline: none;
}

h1 {
  display: flex;
  justify-content: center;
}

.choosen {
  display: flex;
  justify-content: center;
  padding: 20px;
}

.lol {
  background-image: url("./assets/rock.png");
}
.choose1 {
height: 300px;
width: 300px;
cursor: pointer;
transition: 100ms;
}

.choose2 {
height: 300px;
width: 300px;
cursor: pointer;
transition: 100ms;
}

.choose3 {
height: 300px;
width: 300px;
cursor: pointer;
transition: 100ms;
}

.choose1:hover, .choose2:hover, .choose3:hover {
  transform: scale(1.2);
}

.score {
  margin-top: 1rem;
  display: grid;
  justify-content: center;
  grid-template-columns: repeat(2, 1fr);
  justify-items: center;
  align-items: center;
  font-size: 2rem;
}

.score-d{
  margin-left: .1rem;
  font-size: 1.2rem;
  color: #333;
}

.result-winner{
opacity: .5;
height: 200px;
width: 200px;
}

.result {
  height: 200px;
  width: 200px;
  opacity: 1;
  font-size: 1.5rem;
}

</style>
