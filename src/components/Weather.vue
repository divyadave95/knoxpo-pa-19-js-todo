<template>
<div class="container">
    <div class="row">
        <div class="col-md-12">
        <div v-for="item in items">
            {{ item }}
        <p v-for="temp in temps">{{ temp }}</p>
        
        </div>
        
        
</div>
</div>
</div>
</template>
<script>
import axios from 'axios'
export default {
    data() {
        return {
            
                items: ['sunday','monday', 'tuesday', 'wednesday','thuesday','friday'],
                temps: []
            }

        },
    mounted() {
        axios.get('http://api.openweathermap.org/data/2.5/forecast/daily?q=Mumbai&units=metric&cnt=7&appid=12bc580296e1fce828f8e4e8ca694e14')
        .then(res => {
         const list = res.data.list
         for (let item in list) {
             const user = list[item]
             this.temps.push(user.temp.max.toFixed())
         }
         console.log(temps)
         
         
        })
        .catch(err => console.log(err))
    }

}
</script>
<style>
div {
    display: inline-block;
    padding-left: 1em;
    padding-right: 1em;
    
    
}