<template>
<div class="container">
  <transition name='bounce' appear>
    <div class="col-md-2 col-sm-2 col-sm-offset-3 col-md-offset-3 col-xs-4" id="title">
      <h1>Build</h1>
    </div>
  </transition>
    <transition name='bounce-after' appear>
    <div class="col-md-2 col-sm-2 col-xs-4" id="title-your">
      <h1>your</h1>
    </div>
  </transition>
  <transition name='bounce-after-2' appear>
    <div class="col-md-2 col-sm-2 col-xs-4" id="title-your">
      <h1>burger</h1>
    </div>
  </transition>
<div class="container">
  <div class="row">
     <app-burger :meats="meats" :cheeses="cheeses" :salads="salads" ></app-burger>
  
      <app-checkout :meats="meats" 
        :salads="salads" 
        :cheeses="cheeses" 
        v-bind:isMySieblingClicked='isSiebling1Clicked'
        @close="isSiebling1Clicked = false">
      </app-checkout>


    <app-add-toppings 
      @meatAdded="addMeat" 
      @meatRemoved="removeMeat" 
      @saladAdded="addSalad"
      @saladRemoved="removeSalad"
      @cheeseAdded = "addCheese"
      @cheeseRemoved = "removeCheese"
      >
      </app-add-toppings>
      <app-submit v-on:buttonClicked="isSiebling1Clicked = !isSiebling1Clicked"></app-submit>
  </div>
</div>
   
</div>

</template>

<script>
import AddToppings from './components/AddToppings';
import Burger from './components/Burger';
import Submit from './components/Submit';
import Checkout from './components/CheckOut';

export default {
  data: function() {
    return {
      meats: [''],
      salads: [''],
      cheeses: [''],
      isSiebling1Clicked: false,
      hide: false
      
    }
  },
  methods: {
    addMeat (meat) {
      this.meats.push('meat');
    },
    removeMeat (meat) {
      this.meats.pop('meat');
    },
     addSalad (salad) {
      this.salads.push('salad');
    },
    removeSalad (salad) {
      this.salads.pop('salad');
    },
    addCheese(cheese) {
      this.cheeses.push('cheese');
    },
    removeCheese (cheese) {
      this.cheeses.pop('cheese');
    }, 


  },

 components: {
   appAddToppings: AddToppings,
   appBurger: Burger,
   appCheckout: Checkout,
  appSubmit: Submit

 }
}
</script>

<style>
body {
  font-family: 'Anton', sans-serif;
}

#title-your h1{
  padding-left: 20px;
}

h1 {
  font-size: 50px;
  text-transform: uppercase;
font-family: 'Black Ops One', cursive;
color: black;

}

.bounce-after-2-enter-active {
-webkit-animation-name: bounceInDown;
  animation-name: bounceInDown;
  -webkit-animation-duration: 1s;
  animation-duration: 1s;
  -webkit-animation-fill-mode: both;
  animation-fill-mode: both;
  animation-delay: .8s;
}
.bounce-after-enter-active {
-webkit-animation-name: bounceInDown;
  animation-name: bounceInDown;
  -webkit-animation-duration: 1s;
  animation-duration: 1s;
  -webkit-animation-fill-mode: both;
  animation-fill-mode: both;
  animation-delay: .4s;
}

.bounce-enter-active {
-webkit-animation-name: bounceInDown;
  animation-name: bounceInDown;
  -webkit-animation-duration: 1s;
  animation-duration: 1s;
  -webkit-animation-fill-mode: both;
  animation-fill-mode: both;
  }





  @-webkit-keyframes bounceInDown {
  0%, 60%, 75%, 90%, 100% {
  -webkit-transition-timing-function: cubic-bezier(0.215, 0.610, 0.355, 1.000);
  transition-timing-function: cubic-bezier(0.215, 0.610, 0.355, 1.000);
  }
  
  0% {
  opacity: 0;
  -webkit-transform: translate3d(0, -3000px, 0);
  transform: translate3d(0, -3000px, 0);
  }
  
  60% {
  opacity: 1;
  -webkit-transform: translate3d(0, 25px, 0);
  transform: translate3d(0, 25px, 0);
  }
  
  75% {
  -webkit-transform: translate3d(0, -10px, 0);
  transform: translate3d(0, -10px, 0);
  }
  
  90% {
  -webkit-transform: translate3d(0, 5px, 0);
  transform: translate3d(0, 5px, 0);
  }
  
  100% {
  -webkit-transform: none;
  transform: none;
  }
  }
  
  @keyframes bounceInDown {
  0%, 60%, 75%, 90%, 100% {
  -webkit-transition-timing-function: cubic-bezier(0.215, 0.610, 0.355, 1.000);
  transition-timing-function: cubic-bezier(0.215, 0.610, 0.355, 1.000);
  }
  
  0% {
  opacity: 0;
  -webkit-transform: translate3d(0, -3000px, 0);
  transform: translate3d(0, -3000px, 0);
  }
  
  60% {
  opacity: 1;
  -webkit-transform: translate3d(0, 25px, 0);
  transform: translate3d(0, 25px, 0);
  }
  
  75% {
  -webkit-transform: translate3d(0, -10px, 0);
  transform: translate3d(0, -10px, 0);
  }
  
  90% {
  -webkit-transform: translate3d(0, 5px, 0);
  transform: translate3d(0, 5px, 0);
  }
  
  100% {
  -webkit-transform: none;
  transform: none;
  }
  } 
@media only screen and (max-width: 1100px) {
  #title {
    position: relative;
    left: 0;
    padding: 0;
  }
  h1 {
    font-size: 31px;
  }
  #title-burger {
    position: relative;
    left: 0 ;
    padding: 0;
  }
  #title-your {
    position: relative;
    left: 0;
    padding: 0;
  }
}
</style>
