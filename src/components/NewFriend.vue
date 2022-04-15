<template>
<form @submit.prevent="submitData">
<h2>New Friend</h2>

<div>
<label> Name</label>
<input type="text" v-model="ename">
<div>
<label> Email</label>
<input type="text" v-model="eemail">
</div>
<div>
<label> Phone</label>
<input type="text" v-model="ephone">
</div>
<button >Submit</button>
</div>
</form>
</template>
<script>
export default{
    emits:[
        'submit'
    ],
    data(){
        return{
            ename:'',
            ephone:'',
            eemail:''
        }

    },
    methods:{
        submitData(){
            this.$emit('submit',
            this.ename,
            this.ephone,
            this.eemail
            )
        }
    }
}
</script>

