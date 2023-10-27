<script>
    export default {
        props: ['onTagsChange'],
        data(){
            return {
                currentValue : "",
                tags: []
            }
        },

        methods: {
            heandleKeyDown(e){
                if(e.key === 'Backspace' && this.currentValue === ""){
                    this.tags.pop()
                    this.onTagsChange(this.tags)
                }
            },

            heandleSubmit(e){
                if(this.currentValue != ''){
                    const exist = this.tags.some(item => item === this.currentValue)
                    if(!exist){
                        this.tags.push(this.currentValue)
                        this.currentValue = ""
                        this.onTagsChange(this.tags)
                    }
                }
            },

            deleteTag(tag){
                this.tags = this.tags.filter((item) => item != tag )
                this.onTagsChange(this.tags)
            }

        }
    }
</script>

<template>
    <div class="inputTag">
        <div class="tags">
            <div class="tag" v-for="(tag, index) in tags" :key='index'>
                {{tag}} <button @click="deleteTag(tag)">X</button>
            </div>
        </div>
        <form @submit.prevent="heandleSubmit">
            <input class="input" type="text" v-model="currentValue"  @keydown="heandleKeyDown">
        </form>
    </div>
</template>

<style scoped>
    .inputTag{
        display: inline-flex;
        border: solid 1px #000;
        border-radius: 3px;
        height: 43px;
        background-color: #fff;
    }

    .tags{
        display: flex;
        gap: 3px;
        padding: 5px;
    }

    .tags .tag{
        display: flex;
        padding: 5px;
        border: solid 1px #ccc;
        gap: 5px;
        align-content: center;
        border-radius: 3px;
    }

    .inputTag .input {
        border: none;
        outline: none;
        padding: 0 5px;
        width: 600px;
    }

    .inputTag form{
        display: inline-flex;
    }

    .tag button{
        background-color: transparent;
        border: none;
        border-radius: 3px;
    }

    .tag button:hover{
        background-color: #ccc;
    }
</style>