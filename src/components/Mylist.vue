<template>
    <div class = "list">
        <h1>{{ title }}</h1>
        <div>
            <div>
                <input type = "text" v-model = "input">
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
        };
    },

    methods: {
        doAction: function(){
            //input text add array
            var arr = this.input.push();

            while(arr[5] != ''){
                var last = arr.pop();
                //if arr[5] not empty,repeat move each item to front in arr
                for(var n in arr){
                    arr[n] = arr[n + 1];
                }
            }
            //Last item in arr of array,insert to last 
            arr = last.push()


            //Call result-event on $emit
            this.$emit('result-event',arr);
        }
    }

}
</script>