<template>
    <h1 class="text-blue-500 text-3xl">{{ name }}</h1>
    <h1 class="text-blue-600">{{ age }}</h1>
    <h1 class="text-blue-700">{{ Position() }}</h1>
    <h1 class="text-blue-800">{{ CalAge() }}</h1>
</template>

<script>
export default {
    data() {
        return {
            name: "Yan Phayu",
            age : 19,
            gender : "Male"
        }
    },
    methods:{
        Position(){
            return "Web Developer";
        },
        CalAge(){
            if(this.age > 0 && this.age > 19 && this.age < 25){
                return "Junior";
            }
            else{
                return "Senior";
            }
        }
    }
}
</script>

<style>

</style>