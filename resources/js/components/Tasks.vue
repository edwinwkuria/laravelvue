<template>
<div class="container">
    <span>{{message}}</span>
<ul class="list-group">
  <li class="list-group-item"> </li>
</ul>
</div>
</template>
<script>
export default {
    data: function(){
        return{
            listItems: ["Got to the shop", "Go to the Market", "Clean the house"],
            message : "Vue JS"
        }
    },
    mounted() {
            console.log('Component mounted.')
        }
}
</script>