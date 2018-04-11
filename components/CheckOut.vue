<template >
       <div v-if="isMySieblingClicked">
            <div class="checkout col-sm-8 col-sm-offset-2 col-xs-12 col-md-4 col-md-offset-4">
                <div @click="close"> <i class="far fa-times-circle"></i> </div>
                <h3 class="text-center">Your order</h3>
                <p>You ordered a burger with:</p>
                <ul>
                    <li> <span>Meat: </span><span>{{ meats.length }}</span> </li>
                    <li> <span>Salad: </span><span>{{ salads.length }}</span> </li>
                    <li> <span>Cheese: </span><span>{{ cheeses.length }} </span></li>
                </ul>
                <button class="btn btn-primary submitted" @click="order">Order now!</button>
            </div>
      </div>
</template>

<script>
export default {
    data: function() {
        return {
            seen: true
        }
    },
    methods: {
        close() {
            this.$emit('close')
        },
        order() {
            const x = Math.floor(Math.random()*10 ) + 5;
            alert('Your order has been submitted and it will be ready in ' + x + ' minutes.') ;
        }
    },

 


 props: ['meats', 'salads', 'cheeses', 'isMySieblingClicked'],

 }


 



</script>

<style>
.checkout {
    
    display: flex;
    flex-direction: column;
    position: absolute;
    left: 1%;
    top: 50%;
    transform: translateY(-50%);
    height: 250px;
    background-color: white;
    color: black;
    border: 1px solid black;
    z-index: 1000;
}
.checkout h3 {
    padding-bottom: 7px;
    margin-top: 0;
}
.checkout ul {
    list-style: none;
}
.checkout li {
    margin-bottom: 8px;
    display: flex;
    justify-content: space-between;
}
.fa-times-circle {
    margin-left: 98%;
    margin-top: 2%;
    cursor: pointer;
    transition: all .8s;
}

.fa-times-circle:hover {
    transform: scale(1.3);
    color: black;
}

.active {
    display: none;
}
.submitted {
    background-color: black;
    border: 1px solid black;
}

</style>