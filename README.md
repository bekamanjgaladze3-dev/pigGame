'use strict';
const score0 = document.querySelector("#score--0");
const score1 = document.querySelector("#score--1");
const current0 = document.querySelector("#current--0");
const current1 = document.querySelector("#current--1");
const dice = document.querySelector(".dice");
const rollDice = document.querySelector(".btn--roll");
const holdBtn = document.querySelector(".btn--hold");
const diceNumbers = ["dice-1.png","dice-2.png","dice-3.png","dice-4.png","dice-5.png","dice-6.png"];
let random;
let score = 0;
const player0 = document.querySelector(".player--0");
const player1 = document.querySelector(".player--1");

rollDice.addEventListener("click", updateUI,false);


function updateUI(){


pigGame();
  

}


function pigGame(){

    if(player0.classList.contains("player--active")){

        player01();
    }else{

        player02()
    }
}


function player01(){
 
random = Math.floor(Math.random() * diceNumbers.length);

dice.src = diceNumbers[random];

score = random + 1;
if(score === 1){

    score = 0;
    current0.innerHTML = score;
     player0.classList.remove("player--active");
     player1.classList.add("player--active");
}
 
 current0.innerHTML =   Number(current0.innerHTML) + score;

}

function player02(){
 
random = Math.floor(Math.random() * diceNumbers.length);

dice.src = diceNumbers[random];

score = random + 1;
if(score === 1){

    score = 0;
    current1.innerHTML = score;
     player1.classList.remove("player--active");
     player0.classList.add("player--active");
}
 
 current1.innerHTML =   Number(current1.innerHTML) + score;

}

holdBtn.addEventListener("click", function(){

      if(player0.classList.contains("player--active")){
     
   score0.innerHTML = Number(score0.innerHTML) + Number(current0.innerHTML);
      score = 0;
    

    current0.innerHTML = score;

    player0.classList.remove("player--active");
     player1.classList.add("player--active");
           
      }else{


          score1.innerHTML = Number(score1.innerHTML) + Number(current1.innerHTML);

          score = 0;
          current1.innerHTML = score;
           player1.classList.remove("player--active");
     player0.classList.add("player--active");
      }


})
