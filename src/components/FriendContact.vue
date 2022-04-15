<template>
    <li>
    <h2 v-if="isFavourite">{{name}}{{isFavourite==='1'?'(Favourite)':''}}</h2>
    <button @click="toggleDisplayData">{{detailsAreVisible?'Hide':'Show'}} Details</button>
    <ul v-if="detailsAreVisible">
    <li><strong>Phone:</strong>{{phoneNumber}}</li>
    <li><strong>Email:</strong>{{emailAddress}}</li>
    </ul>
    </li>
</template>
<script>
export default{
    props:{
        name:{
            type:String,
            required:true
        },
        phoneNumber:{
            type:String,
            required:true
        },
        emailAddress:{
            type:String,
            required:true
        },
        isFavourite:{
            type:String,
            required:false,
            default:'0',
            validator:function(value){
                return value===1||value===0
            }
        }
    },
    data(){
        return{
            detailsAreVisible:false,
            friend:{
            id:1,
            name:'Sahitya',
            email:'sahitya.v@gmail.com',
            phone:'012345'
            }
        }
    },
    methods:{
        toggleDisplayData(){
            this.detailsAreVisible=!this.detailsAreVisible;
        }
    }

}
</script>