<template>
<div class="container">
    <span>{{message}}</span>
    <span> {{ count }}</span>
<ul class="list-group">
  <li class="list-group-item" v-for="listItem in listItems"> {{ listItem }}</li> 
</ul>
<input v-model="NewItem" placeholder="New Item">
<button v-on:click="AddItem">Add One</button>
{{ info }}
</div>
</template>
<script>
export default {
    data: function(){
        return{
            listItems: [],
            message : "Tasks",
            count: 0,
            NewItem: '',
            info: null
        }
    },
    mounted() {
            console.log('Component mounted.'),
            axios
                .get('https://run.mocky.io/v3/5ceb96ee-dc79-447e-886f-3c2bba84c957')
                .then(response => (this.info = response.data))
        },
    methods:{
        AddCount(){
            this.count += 1
        },
        AddItem(){
            this.listItems.push(this.NewItem);
            this.NewItem = '';
            this.AddCount()
        }
    }
}
</script>