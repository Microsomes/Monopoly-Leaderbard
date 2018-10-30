<template>

<div style="min-height:1200px;overflow:hidden" class="">


  <div>
<div style="width:100%;" class="jumbotron-fluid bg-success">
  <h1 style="color:white;text-align:center" class="display-4 pt-4">Monopoly Champ</h1>
  <h2  style="color:white;text-align:center" > <span class="badge badge-secondary">coming soon</span></h2>
  <p style="color:white;text-align:center" class="lead p-5">Welcome to the non-official record of the Monopoly champions all around the world</p>
 
   <p style="color:white;text-align:center" class="p-5">We will be keeping a  record of  your wins and lossees. Want to be apart of this amazing project? Carry on reading below then register your interest.</p>
   <div style="text-align:Center" class="pb-3">
 
   </div>

</div>
  </div>

  

  <div class="row p-5">
    
      <div class="col-md l-8">
          <h1 style="color:white" id="speakers" class="display-4 text-center text-muted">What...</h1>

      <h4 style="color:white;text-align:center" class="display-4  mb-3">About?</h4>
     
      <img style="border-radius:20px;" width="100%" src="./img/promo_1.png"/>
      <p class="mt-4" style="color:white;">
       At HQ we love playing Monopoly Deal. So much so that me and my Friends always argue after who was the better player. So I decided to start this website as a way of keeping track of the wins and losses. Everyone is welcome, anyone can submit their win/loss scores and ill update them on the global database (screenshot required for proof). 
       </p>
    </div>

    <div class="col-md">
           <h1 style="color:white" id="speakers" class="display-4 text-center text-muted">Why...</h1>

      <h4 style="color:white;text-align:center" class="display-4  mb-3">Glad you asked?</h4>
     
  
        <ul class="list-group">
  <li class="list-group-item"><strong>Competitive</strong> leaderboard</li>
  <li class="list-group-item"><strong>Buzz</strong> Hosted Tournaments</li>
  <li class="list-group-item"><strong>Ego</strong> Bragging Rights</li>
  <li class="list-group-item"><strong>Shiny</strong> App (Android/IOS)</li>
  <li class="list-group-item"><strong>Love</strong> Connect and play with the best</li>
</ul>
     <p class="mt-4" style="color:white;">
         Monopoly deal is a really precisious  and competitive game. We wanted to keep track of the worlds best Monopoly player similar to how the worlds best chess player is known. Below we list some of the benefits we can offer.
        </p>
    </div>

    
  </div>

    <h1 id="speakers" class="display-4 text-center my-5 text-muted">Who?</h1>
  <div class="row">
    <div v-for="n in who" class="col-md mt-3  col-sm-2 ml-5">
      <div class="card" style="width: 18rem;">
  <img class="card-img-top" :src="n.image" alt="profile image">
  <div class="card-body">
    <h5 class="card-title">{{n.title}}</h5>
    <p class="card-text">{{n.description}}</p>
   </div>
</div>
    </div>
 
  </div>

  
 <div>
     <h1 id="speakers" class="display-4 text-center my-5 text-muted">Want this to happen?</h1>

  <div class="row mt-5 mb-5 p-5">
    
    <div style="color:white;" class="col">
      
      
      <h4>Register your interest</h4>
      Interested in the project? <br>Register your interest to recieve more details via email.
    </div>
    
    <div class="col-md">
      
      <form @submit.prevent="submitInterest">
       <div class="form-group">
    <label style="color:white" for="exampleInputEmail1">Email address</label>
    <input v-model="emailinput" type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Enter email">
    <small id="emailHelp" class="form-text text-muted">We'll never share your email with anyone else.</small>
    <input  type="submit" value="Register your interest" class="btn btn-success"/>
       <div v-if="feedback" class="alert alert-danger mt-2" role="alert">
  {{feedback}}
</div>
    
    </div>

      </form>
    </div>
  </div>
  </div>


</div>


</template>


<script>

var db = require("./db.js").db;
 


 
export default{
  data:function(){
    return {
      emailinput:'',
      feedback:false,
      who:[
        {
          title:'Me',
          description:'I love playing Minecraft Call of Duty and GTA V. Oh and i love blowing shit up.',
          image:'https://firebasestorage.googleapis.com/v0/b/leaderboard-382c5.appspot.com/o/pvp.jpg?alt=media&token=164cc41d-f664-455f-971a-2b1de86a0d19'
        },
         {
          title:'Brisk',
          description:"I'm Fortnite addicted but i also like to lighten up with some Monopoly.",
          image:'https://firebasestorage.googleapis.com/v0/b/leaderboard-382c5.appspot.com/o/brisk.jpg?alt=media&token=594f5b28-2f66-449c-a04d-188e6cceb147'
        },
         {
          title:'Lil Tiz',
          description:'I suck at everything. Fuck it',
          image:'https://firebasestorage.googleapis.com/v0/b/leaderboard-382c5.appspot.com/o/irtiza.jpg?alt=media&token=e55e3713-3826-4a64-a3e4-12f29f6d3eac'
        },
         {
          title:'O Like a i3oss',
          description:'What day is it today? Oh its Friday lets bring out the alexa and play some Monopoly',
          image:'https://firebasestorage.googleapis.com/v0/b/leaderboard-382c5.appspot.com/o/sajjid.jpg?alt=media&token=d25853fa-a636-4fce-a5f1-21bd26cd900c'
        },
         {
          title:'Miss Alexa',
          description:'I take commands and execute them well. Their is never a good game of Monopoly without me. I supply the Music (:',
          image:'https://consequenceofsound.files.wordpress.com/2018/03/amazon-alexa-laughing-creepy.jpg?quality=80'
        }
      ],
        info:[
        {
          image:'https://firebasestorage.googleapis.com/v0/b/leaderboard-382c5.appspot.com/o/promo_1.png?alt=media&token=684207a9-ca67-4563-bd82-dd3846cc65e8',
          description:'Monopoly is better with competitive people. Find competitive people from all around the world to play with.',
          heading:'Find people to play with'
        },
        {
        image:'https://firebasestorage.googleapis.com/v0/b/leaderboard-382c5.appspot.com/o/promo_2.png?alt=media&token=5c47f383-c421-46d8-a5e5-9f5f31782339',
          description:"Send us a picture of you winning a game of Monopoly Deal and we'll add your name to the global records.",
          heading:'See how you stack up'
        },
        {
      image:'https://firebasestorage.googleapis.com/v0/b/leaderboard-382c5.appspot.com/o/promo_3.png?alt=media&token=4c27cf0e-0cfa-4e2e-a8bd-5254e7e9f193',
          description:'We will be hosting tournaments with lots of prizes to come every couple of Months.',
          heading:'Tournaments'
        }
      ]
    }
  },
  methods:{
    submitInterest(){
      var home=this;
      //check if emailinput was submitted
      if(this.emailinput.length<=1){
        this.feedback="no email was typed";
        return;
      }
      this.feedback="Porcessing....";
      var ref =  db.collection("monppoly").add({
      email:home.emailinput
    }).then(status=>{
      home.feedback="You have been addded to the list. Thanks for your interest (:";
      home.emailinput="";
    })
      //make an api call to add email to a database

    }
  }
}

</script>