<script>
import axios from 'axios';

 
 export default {
    data(){
        return {
            facts: []
        }
    },
    async mounted(){
        this.newFact()

    },

    methods: {
       async newFact() {
            axios.defaults.headers.common = {
            "X-API-key" : "crkH1iAOmrnAauO5fC1QHg==6OWtaIGIPWZGUdKi",
        };
        const response = await axios.get('https://api.api-ninjas.com/v1/facts?')
        this.facts = response.data 
        
        }
    }

 }






</script>
<template>
    <div class="container">
        <div class="container-wrapper" v-for="fact in facts">
            <div class="dots">
                <div class="dot1"></div>
                <div class="dot2"></div>
                <div class="dot3"></div>
            </div>
            <div class="container-inner">

                <h1>{{fact.fact}}</h1>
            </div>
            <button class="next" @click="newFact"><span class="material-symbols-outlined" style="font-size:11px; font-weight: 800;	color: rgb(20 184 166);">
                arrow_forward_ios
                </span>Next</button>
        </div>
    </div>



</template>
<style scoped lang="scss">


    @media screen and (min-width:600px) {
 .container {
    display : flex;
    justify-content: center;
    align-items:center;
    width:100%;
    height: 100%;
    
    .container-wrapper{
        height: 30%;
        width:50%;
        position:relative;
        background-color: white;
        border: 1px solid #ddd;
        border-radius:10px;
        box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
          
        .container-inner {
            padding:4.5rem;
            display:flex;
            align-items: center;
            h1{
                font-size : 1.4rem;
                text-align:center;
             }
        }

        .next {
            bottom:0;
            right:0;
            margin: 0 1rem 1rem 0;
            position : absolute;
            font-size: 1rem;
            padding:.5rem;
            display:flex;
            border-radius: 10px;
            border:0;
            font-family: 'Nunito', sans-serif;
            align-items: center;

            &:hover {
                background-color: #ddd;
            }
        }
        .dots{
            display:flex;
            position: absolute;
            gap:10px;
            top:0; 
            left:0;
            margin:15px;

            .dot1{
             background-color:rgb(179, 30, 30);
             height:20px;
             width:20px;
             border-radius:50%;
            }
            .dot2{
                background-color:rgb(238, 199, 70);
                height:20px;
                width:20px;
                border-radius:50%;
            }
            .dot3{
                 background-color:rgb(70, 238, 84);
                height:20px;
                width:20px;
                border-radius:50%;

            }
        }
        
      

    }

   }
 }   


 @media screen and (max-width:599px){
    .container {
        display : flex;
        justify-content: center;
        align-items:center;
        width:100%;

        height: 100%;
        
        .container-wrapper{
            height: 30%;
            width:100%;
            position:relative;
            background-color: white;
            border: 1px solid #ddd;
            border-radius:10px;
            box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
              
            .container-inner {
                padding:4.5rem;
                display:flex;
                align-items: center;
                h1{
                    font-size : 1.4rem;
                    text-align:center;
                 }
            }
    
            .next {
                bottom:0;
                right:0;
                margin: 0 1rem 1rem 0;
                position : absolute;
                font-size: 1rem;
                padding:.5rem;
                display:flex;
                border-radius: 10px;
                border:0;
                font-family: 'Nunito', sans-serif;
                align-items: center;
    
                &:hover {
                    background-color: #ddd;
                }
            }
            .dots{
                display:flex;
                position: absolute;
                gap:10px;
                top:0; 
                left:0;
                margin:15px;
    
                .dot1{
                 background-color:rgb(179, 30, 30);
                 height:20px;
                 width:20px;
                 border-radius:50%;
                }
                .dot2{
                    background-color:rgb(238, 199, 70);
                    height:20px;
                    width:20px;
                    border-radius:50%;
                }
                .dot3{
                     background-color:rgb(70, 238, 84);
                    height:20px;
                    width:20px;
                    border-radius:50%;
    
                }
            }
            
          
    
        }
    
       }
    
    
 }

</style>