<template>
    <div>
        <h1>Welcom to {{title2}}</h1>
        <input type="text" v-model="input1">
        <button @click="getData">Click me</button>
         <button @click="setData">set me</button>

         <select class="form-control" v-model="region" @change="changeRegion">
             <option v-for="(d, i) in options" :key="i" :value="d.v">{{d.t}}</option>
         </select>

         <table class="table table-bordered">
             <tr v-for="(d,i) in options" :key="i">
                 <td>{{d.v}}</td>
                 <td>{{d.t}}</td>
             </tr>
         </table>
    </div>
</template>

<script>
export default {
    name:'Home',
    data(){
        return{
            title:"Hello Hambo",
            title2:"Seoul",
            input1:"abcd",
            options:[
                {v:"s", t:"seoul"},
                {v:"d", t:"busan"},
                {v:"f", t:"ded"}
            ],
            region:"d"
        }
    },
    watch:{
        input1(){
            console.log(this.input1);
        }
    },
    methods:{
        getData(){
            alert(this.input1)
        },
        setData(){
            this.input1 = "1234";
        },
        changeRegion(){
            alert(this.region)
        }
    },
    beforeCreate(){
            console.log('beforeCreate');
        },
        created(){
            console.log('created');
        },
        beforeMount(){
            console.log('beforeMount');
        },
        mounted(){
            console.log('mounted');
        },
        beforeUpdate(){
            console.log('beforeUpdate');
        },
        updated(){
            console.log('updated');
        },
        beforeDestroy(){
            console.log('beforeDestroy');
        },
        destroyed(){
            console.log('destroyed');
        }
}
</script>