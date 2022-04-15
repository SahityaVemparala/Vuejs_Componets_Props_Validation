<template>
    <li>
    <h2 >{{name}}{{isFavourite?'(Favourite)':''}}</h2>
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
            type:Boolean,
            required:false,
            default:false,
            // validator:function(value){
            //     return value===true||value===false
            // }
        }
    },
    data(){
        return{
            detailsAreVisible:false,
            friendIsFavourite:this.isFavourite
        }
    },
    methods:{
        toggleDisplayData(){
            this.detailsAreVisible=!this.detailsAreVisible;
        },
        toggleFavourite(){
            this.friendIsFavourite=!this.friendIsFavourite;
        }
    }

}
</script>