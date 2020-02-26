<template>
    <div id="list-form">
        <form @submit.prevent="handleSubmit">
            <label>Item</label>
            <input type="text" v-model="list.item"/>
            <button>Add ToDo</button>
        </form>
    </div>
</template>

<script>
export default {
    name:'list-form',
    data(){
        return{
            list : {
            status:false,
            item:'',
            }
        }
    },
    methods:{
        handleSubmit(){
            this.$emit('add:item', this.list)
        },
    }
    
}
</script>
    
<style scoped>
    form{
        margin-bottom: 2rem;
    }
</style>