<script setup>
import { useRoute, useRouter, RouterView } from "vue-router"
import cars from "../data/cars.json"
import ContactView from "./ContactView.vue"
const route = useRoute()
const router = useRouter()
//const carId = parseInt(route.params.id)

//console.log("useRoute:"+route);
//console.log("useRouter:"+router);

const carId = parseInt(route.params.id)
const car = cars.find(c=>c.id === carId);
console.log(car)
const cartest = ()=>{
    return cars.find(c=>c.id === parseInt(route.params.id))
}

//const car = cars.find(c=>c.id === parseInt(route.params.id))
//const car = cars.find(c=>c.id === carId)
console.log(route.params)

const showContact =()=>{
    console.log("In showContact")
    if(carId === 4) return;
    return router.push(`/cars/${carId}/contact`)
}


</script>

<template>
<div v-if="car">
<h1>Car View</h1>
<p>{{car.name}}</p>
<p>{{car.year}}</p>
<p>{{car.price}}</p>
<button @Click="showContact">Click for contact</button>
<RouterView/>
<ContactView/>


<!--
<ContactView/>
{{car}} -->
</div>
<div v-else>
<h1>Car not found</h1>
</div>
</template>