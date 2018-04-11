<template>
    <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-4 col-md-offset-4 burger-container">
    <div class="bread-top"> </div>
        <transition-group 
        enter-active-class="animated lightSpeedIn"
        leave-active-class="animated lightSpeedOut">
            <app-meat v-for="meat in meats" :key="meat"> {{ meat }}</app-meat>
        </transition-group>
       <transition-group 
        enter-active-class="animated lightSpeedIn"
        leave-active-class="animated lightSpeedOut">
            <app-cheese v-for="cheese in cheeses" :key="cheese"> {{ cheese }}</app-cheese>
       </transition-group>
       <transition-group 
        enter-active-class="animated lightSpeedIn"
        leave-active-class="animated lightSpeedOut">
            <app-salad v-for="salad in salads" :key="salad"> {{ salad }}</app-salad>
       </transition-group>
    <div class="bread-bottom"> </div>
</div>

   
</template>

<script>
import Meat from '../components/Meat';
import Salad from '../components/Salad';
import Cheese from '../components/Cheese';
export default {
    props: ['meats', 'salads', 'cheeses'],
    components: {
        appMeat: Meat,
        appSalad: Salad,
        appCheese: Cheese,
    }
 
}
</script>

<style>
.burger-container {
    margin-top: 10px;
    height: 300px;
    overflow: scroll;
}

.bread-top {
    background-color: rgb(238, 147, 10);
    width: 100%;
    height: 70px;
    border-radius: 30% 30% 3% 3%;
    margin-bottom: 10px;
}
.bread-bottom {
    background-color: rgb(238, 147, 10);
    width: 100%;
    height: 70px;
    border-radius: 3% 3% 30% 30%;
    margin-top: 10px;
}

.slide-enter {
opacity: 0;
}

.slide-enter-active {
animation: slide-in 1s ease-out forwards;
transition: opacity .5s;
}

.slide-leave {

}

.slide-leave-active {
animation: slide-out 1s ease-out forwards;
transition: opacity 1s;
opacity: 0;
}

@keyframes slide-in {
    from {
        transform: translateX(20px);
    }
    to {
        transform: translateX(0);
    }
}
@keyframes slide-out {
    from {
        transform: translateX(0);
    }
    to {
        transform: translateX(20px);
    }
}
</style>