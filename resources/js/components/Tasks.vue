<template>
<ul class="list-group">
  <li class="list-group-item" v-text="message"></li>
</ul>
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