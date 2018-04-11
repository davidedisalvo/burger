<template>       
<div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-4 col-md-offset-4 submit">
        <button class="btn btn-primary submit__button" @click="$emit('buttonClicked')"> Submit</button>
 </div>
      
   
</template>

<script>
export default {


}
</script>

<style>
.submit__button {
    margin-top: 3px;
    background-color: black;
    border: 1px solid black;
    
}

.btn:hover {
    background-color: white;
    color: black;
}


</style>