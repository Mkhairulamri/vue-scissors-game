<template>
<div class="game">
    <h1>Scissors Paper Rock</h1>
    <h4 class="text-primary">{{Message}}</h4>
    <div class="score">
        <ul>
            <li>{{UserScore}}</li>
            <li>=</li>
            <li>{{ComputerScore}}</li>
        </ul>
    </div>
    <div class="result">
        <p>{{UserPick}}</p>
        <p>=</p>
        <p>{{ComputerPick}}</p>
    </div>
    <div class="pick">
        <!-- <button class="btn-primary" v-for="pick in option" :key="pick" :click="pick">{{pick}}</button> -->
        <button class="btn-primary" @click="rock">Rock</button>
        <button class="btn-primary" @click="paper">Paper</button>
        <button class="btn-primary" @click="scissors">Scissors</button>
    </div>
    <p>{{message}}</p>
</div>
</template>

<script>
export default {
  name: "GameSection",
  data(){
    return{
           ComputerScore:0,
           UserScore: 0,
           UserPick: "",
           ComputerPick:"",
           option:["rock","paper","scissors"],
           message:""
    }
  },
  methods:{
    rock(){
        const RandPick = Math.floor(Math.random() * this.option.length)
        this.UserPick = "Rock"
        this.ComputerPick = this.option[RandPick]
        if(this.option[RandPick] === "rock"){
            this.UserScore++
            return this.message = "Anda Menang"
        }else{
            this.ComputerScore++
            console.log(RandPick)
            return this.message = "Anda Kalah"
        }
    },
    paper(){
        this.UserPick = "Paper"
        const RandPick = Math.floor(Math.random()*this.option.length)
        this.ComputerPick = this.option[RandPick]
        if(this.option[RandPick] == "paper"){
            this.UserScore++
            return  this.message = "Anda Menang"
        }else{
            this.ComputerScore++
            console.log(RandPick)
            return this.message = "Anda Kalah"
        }
    },
    scissors(){
        this.UserPick = "Scissors"
        const RandPick = Math.floor(Math.random()*this.option.length)
        this.ComputerPick = this.option[RandPick]
        if(this.option[RandPick] == "scissors"){
            this.UserScore++
            return  this.message = "Anda Menang"
        }else{
            this.ComputerScore++
            console.log(RandPick)
            return this.message = "Anda Kalah"
        }
    }
  }
};
</script>

<style>
.game{
    display: grid;
    justify-content: center;
    height: 500px;
    margin-top: 50px;
}
.game h1{
    font-family: 'Roboto', sans-serif;

}
ul{
    list-style: none;
    margin-top: -100px;
    display: flex;
    font-size: 5em;
    justify-content: center;
}
.pick{
    padding-left:20px;
    margin-left: 10px;
    cursor: pointer;
}
.pick button{
    margin-left:20px;
    width:100px
}
.option{
    cursor:pointer;
}
</style>