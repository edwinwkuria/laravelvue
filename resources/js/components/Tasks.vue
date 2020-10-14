<template>
<div class="container">
    <span>{{message}}</span>
    <span> {{ count }}</span>
<ul class="list-group">
  <li class="list-group-item" v-for="listItem in listItems"> {{ listItem }}</li> 
</ul>
<input v-model="NewItem" placeholder="New Item">
<button v-on:click="AddItem">Add One</button>
<button v-on:click="sortItems">Sort Array</button>
{{ info }}
</div>
</template>
<script>
export default {
    data: function(){
        return{
            listItems: [],
            arrayEmpty: [],
            message : "Tasks",
            count: 0,
            NewItem: '',
            info: null
        }
    },
    mounted() {
            console.log('Component mounted.'),
            axios
                .get('https://run.mocky.io/v3/4aafaa27-4ce5-4f47-84c0-ec546c71037b')
                .then(response => (this.listItems = this.arrayEmpty.concat(JSON.parse(response.data)).name))
        },
    methods:{
        AddCount(){
            this.count += 1
        },
        AddItem(){
            this.listItems.push(this.NewItem);
            this.NewItem = '';
            this.AddCount()
        },
        sortItems(){
            this.listItems.sort()
        }
    }
}
</script>