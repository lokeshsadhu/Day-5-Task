<!-- eslint-disable vue/valid-v-for -->
<template>
  <h1 style="text-decoration: underline;">Component Props and Emits</h1><br/>
  <FirstComp text="Hi First Component" :games=games @editGame="updateGame"/><br/>
  <SecondComp @buttonClicked="giveWarn"/><br/>
  <ComputeComp/><br/>
  <WatcherComp/><br/>
  <RegisterPage v-show="registered" @register="registerUser"/><br/>
  <LoginPage v-show="loggedin" @login="check"/>
</template>

<script setup>
import { ref } from "vue";
import 'bootstrap'; 
import 'bootstrap/dist/css/bootstrap.min.css';
import FirstComp from "@/components/FirstComp.vue"
import SecondComp from "@/components/SecondComp.vue"
import ComputeComp from "@/components/ComputeComp.vue"
import WatcherComp from "@/components/WatcherComp.vue"
import RegisterPage from "@/components/RegisterPage.vue"
import LoginPage from "@/components/LoginPage.vue"

const games = ref([
{ title: 'The Legend of Zelda: Breath of the Wild', year: 2017 },
  { title: 'Super Mario Odyssey', year: 2017 },
  { title: 'Fortnite', year: 2017 },
  { title: 'Minecraft', year: 2011 },
  { title: 'Overwatch', year: 2016 },
  { title: 'Red Dead Redemption 2', year: 2018 },
  { title: 'Call of Duty: Warzone', year: 2020 }
]);

const giveWarn=(username,password)=>{
  if (username=="" || password=="") {
    alert("This field should not be empty.")
  }
  else{
      error.value=""
      alert("Form submitted.")
  }
  
}
const updateGame=(gameId)=>{
  games.value=games.value.map((game)=>{
    if(game.title===gameId){
      return {...game, title:"Title is updated"}
    }
    return game
  })
}

const users=[]
const registered=ref(true)
const loggedin=ref(false)

const registerUser=(email,phone)=>{
  const newUser={
    email:email,
    phone:phone
  }
  users.push(newUser)
  registered.value=false
  loggedin.value=true
}
console.log(users)

const check=(loginemail,loginphone)=>{
  users.map((user)=>{
    if(user.email===loginemail && user.phone===loginphone){
      alert(loginemail+" "+"Logged in")
    }
  })
  registered.value=true
  loggedin.value=false
}
</script>