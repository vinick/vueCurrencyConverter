<template>
    <div class="conversor p-2">
        <h2>{{moedaA}} To {{moedaB}}</h2>
        <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA">
        <input type="button" value="Converter" v-on:click="converter">
        <h2>{{moedaB_value}}</h2>
    </div>    
</template>

<script>
export default {
    name: "Conversor",
    props: ["moedaA", "moedaB"],
    data()  {
        return {
            moedaA_value : "",
            moedaB_value : 0
        }
    },
    methods: {
        converter() {
            let url = "https://api.exchangeratesapi.io/latest?symbols="+ 
                this.moedaA + "," + this.moedaB +"&base=" + this.moedaA;
            fetch(url).then(res => {return res.json()})
                      .then(json => {
                          console.log(url);
                          let currency = json["rates"][this.moedaB];
                          console.log(currency);
                          this.moedaB_value = (currency * parseFloat(this.moedaA_value)).toFixed(2);
            })
        }
    }
}
</script>

<style>
.conversor {
    max-width: 400px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}

</style>