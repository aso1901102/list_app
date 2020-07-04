<template>
    <div class = "list">
        <h1>{{ title }}</h1>
        <div>
            <div>
                <input type = "text" v-model = "input" placeholder="Input here">
            </div>
                <button v-on:click = "doAction">
                    クリック
                </button>
        </div>  
    </div>
</template>

<script>
export default {
    name: 'Mylist',
    props:{
        title:String,
    },

    data:function(){
        return {
            input: 'Input Here',
            arr: [],
        };
    },
     
    methods: {
        doAction: function(){
            //input text add array
            this.arr = this.input;

            //Call result-event on $emit
            this.$emit('result-event',this.arr);
        }
    }

}
</script>