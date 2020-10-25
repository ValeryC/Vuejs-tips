<template>
    <div class="container">
        <div class="vbind">
            <h1>v-bind</h1>   
        <p>syntaxe complète</p>
        <p>{{`<a v-bind:href="url"> ... </a>`}}</p>
        <p>abréviation </p>
        <p>{{`<a :href="url"> ... </a>`}}</p>
        <p>abréviation avec argument dynamique (2.6.0+)</p> 
        <p>{{`<a :[key]="url"> ... </a>`}}</p>
        </div>
         <div class="vbind">  
             <h1>v-on</h1> 
        <p>syntaxe complète</p>
        <p>{{`<a v-on:click="doSomething"> ... </a>`}}</p>
        <p>abréviation </p>
        <p>{{`@click="doSomething`}}</p>
        <p>abréviation avec argument dynamique (2.6.0+)</p> 
        <p>{{`@[event]="doSomething`}}</p>
        </div>

        <div v-bind:style="{ color: activeColor, fontSize: fontSize + 'px' }">Element</div>
    </div>
</template>

<script>
export default {
data(){
    return{
            activeColor: 'red',
            fontSize: 40
    }
},
}
</script>


<style>
.container{
    position: relative;
    display: flex;
   
}
.vbind{
    position: relative;
    display: flex;
    flex-direction: column;
    margin-left: 50px;
    margin-right: 50px;
}

</style>
