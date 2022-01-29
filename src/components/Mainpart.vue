<template>
    <div>
        <h1>Goals</h1>
        <br>
        
            <input type="text" v-model="enteredGoalValue">
            <button @click="addGoal">AddGoal</button>
        
        <p v-if="goals.length === 0">No goals have been added yet - please start adding some!</p>
        <ul v-else>
            <li v-for="(goal, index) in goals" :key="goal" @click="removeGoal(index)">{{goal.message}}</li>
        </ul>
    </div>
</template>
<script>
export default {
    name: 'Mainpart',
    data(){
        return{
            goals:[],
            enteredGoalValue: ''
        };
    },
    methods:{
        addGoal(){
            const newGoal = {message:this.enteredGoalValue};
            this.goals.push(newGoal);
            this.enteredGoalValue = '';
            //console.log(this.goals);
        },
        removeGoal(index){
            this.goals.splice(index, 1);
        }
    }
}
</script>

<style scoped>
div{
    box-shadow: 0 2px 8px rgba(0,0,0,0.26);
    margin: 3rem auto;
    border-radius: 10px;
    padding: 1rem;
    text-align: center;
    width: 90%;
    max-width: 40rem;
    font-size: 2rem;
}
h1{
    color:rgba(22, 148, 77, 0.842);
}
button{
    width: 15%;
    text-align: center;
    height: 2.5rem;
    background-color: salmon;
}
input{
    width: 80%;
    
    height: 2.5rem;
}
li{
    height: 3rem;
    border-radius: 25px;
    background-color: rgb(77, 184, 77);
    list-style: none;
    margin-right: 7%;
    margin-top: 1rem;
}
</style>