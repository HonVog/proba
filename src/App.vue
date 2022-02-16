<template class ='this' >  
<div v-if="!user.ofCorse">
    <div>
    <label>Имя пользователя</label>
    <input 
    :value="user.name"
    @input="setUserName"
    placeholder="Введите имя пользователя">
    </div>

    <div>
    <label>Фамилия пользователя</label>
    <input
     :value="user.surname" 
    @input="setUserSurName"
    placeholder="Фамилию имя пользователя">

    </div>

    <div >
    <label>Пол пользователя</label>
    <input
    :value="user.gender"
    @input="setGender"
    placeholder="Введите ваш пол">
    
        <div>
            <button @click="OfCours">Подтвердить</button>
        </div>
    </div>
    <div >
        <label>Возраст пользователя</label>
        <input
        :value="age" 
        @input="setAge"
        placeholder="Введите свой возраст">

        <div>
            <button @click="OfCours">Подтвердить</button>
        </div>
    </div>

</div>
<div v-else>
    <div v-if="user.like >= 10">
        Вы очень популярны {{user.name}}
    </div>

    <div v-else-if="diz >= 10" >
        Вас никто не любит {{user.name}}
    </div>

    <div v-else>
        <h2>{{ user.gender +' ' + user.name +' '+ user.surname + ' ' + user.age + 'лет'}}</h2>
        <button @click="addLike">Лайки</button>
        <button @click="addDiz">Дизлайки</button>

        <div> Лайки {{user.like }}</div>
        <div> Дизлайки {{ user.diz }}</div>
    </div>
</div>

</template>

<script>
    export default{
        data(){
            return{
                user: {
                    name: "user_name",
                    surname: "user_surname",
                    gender: "NaN",
                    age: 0,
                    like: 0,
                    diz: 0,
                    ofCorse: false,
                },
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
    margin:10px 10px;
    padding:5px;
}
</style>
