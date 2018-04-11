<template>
   
       <div class="col-sm-12 col-xs-12 col-md-6 col-md-offset-3">

           <div class="toppings">
                <h2 class="text-center">Build your burger</h2>

                <div class="toppingStyle">
                    <button  class="btn btn-primary button" @click.prevent="addMeat">+</button>
                    <p>meet</p>
                    <button class="btn btn-primary button" @click.prevent="removeMeat">-</button>
                </div>
                <div class="toppingStyle">
                    <button class="btn btn-primary button" @click.prevent="addCheese">+</button>
                    <p>cheese</p>
                    <button class="btn btn-primary button" @click.prevent="removeCheese">-</button>
                </div>
                <div class="toppingStyle">
                <button class="btn btn-primary button" @click.prevent="addSalad">+</button><p>salad</p><button class="btn btn-primary button" @click.prevent="removeSalad">-</button>
                </div> 
    

            </div>
            
        </div>
</template>

<script>
export default {

       props: ['seen'],
       


        methods: {
            addMeat () {
                this.$emit('meatAdded', this.meat);
                this.meat = '';
            },
            removeMeat() {
                this.$emit('meatRemoved', this.meat);
                this.meat = '';
            },
            addSalad() {
                this.$emit('saladAdded', this.salad);
                this.salad = '';
            },
              removeSalad() {
                this.$emit('saladRemoved', this.salad);
                this.salad = '';
            },
            addCheese() {
                this.$emit('cheeseAdded', this.cheese);
                this.cheese= '';
            },
             removeCheese() {
                this.$emit('cheeseRemoved', this.cheese);
                this.cheese = '';
            },
    
        },
 

}
</script>

<style>
        .toppings {
            border: 1px solid black;
            display: flex;
            flex-direction: column;
            margin-top: 11px;
            background-color: rgb(255, 94, 0);
            border-radius: 3%;
        }
        .toppingStyle {
        display: flex;
        justify-content: space-between;
        align-content:center;
        margin-top: 6px;
        }
        .toppingStyle:last-child {
            margin-bottom: 20px;
        }
        .button {
            width: 50px;
            margin: auto 10px;
            background-color: black;
            border: black;
        }
        p {
            font-size: 20px;
            text-transform: uppercase;
        }

        .submit__button {
        width: 100%;
        margin-bottom: 10px !important; 
        }



</style>

