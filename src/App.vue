<template> 
<div class="bazis">
    <form v-if="!user.ofCorse" @submit.prevent>
        <div>
        <input 
        :value="user.name"
        
        class="imput"
        placeholder="Введите имя пользователя">
        </div>

        <div>
        <input
        :value="user.surname" 
        @input="setUserSurName"
        class="imput"
        placeholder="Фамилию имя пользователя">
        </div>

        <div >
        <input
        :value="user.gender"
        @input="setGender"
        class="imput"
        placeholder="Введите ваш пол">
        </div>
    
        <div >
            <input
            :value="age" 
            @input="setAge"
            class="imput"
            placeholder="Введите свой возраст">

           
                
            
        </div>
        <button class="btr" @click="OfCours">Подтвердить</button>
    </form> 

    <div v-else>
        <h2>{{ user.gender +' ' + user.name +' '+ user.surname + ' ' + user.age + 'лет'}}</h2>
    </div>
</div>
</template>

<script>
    export default{
        data(){
            return{
                
                user: {
                    id: 0,
                    name: "Введите имя пользователя",
                    surname: "Фамилию имя пользователя",
                    gender: "Введите ваш пол",
                    age: "Введите свой возраст",
                    ofCorse: false,
                },
                user_name: String,
                user_surname: String,
                user_gender: String,
                user_age: Number,
            }           

        },
        methods:{
            addLike(){   this.user.like +=1;  },
            addDiz(){    this.user.diz+=1; },
            setUserName(event){
                this.user.name = event.target.value
            },
            setUserSurName(event){
                this.user.surname = event.target.value
            },
            setGender(event){
                this.user.gender = event.target.value
            },
            setAge(event){
                this.user.age = event.target.value
            },
            OfCours(){
                this.user.ofCorse = true
            },
        }   
    }

</script>

<style>
* {
    margin: 0;
    padding:0;
}

.bazis{
    padding: 3%;
}

form{
    color: tomato;
    display: flex;
    border: 3px solid tomato;
    flex-direction:column;
}

.users{
    padding: 15px;
    border: 2px solid tomato;
    margin-top: 10px;
}

.imput{
    width: 98%;
    border: 2px solid tomato;
    padding: 10px 10px;
    margin-top: 20px;
}

.btr{
    margin-top: 10px;
    align-self:flex-end;
     border: 2px solid tomato;
    padding: 20px 20px;
    color: tomato;
    background: none;
}
     

</style>
