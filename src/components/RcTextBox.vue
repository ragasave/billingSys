<template>
    <span spellcheck="false" ref="text" v-on:blur="updateValue" :class="className" :style="styleAttr" v-on:paste="pasteOnlyText" v-on:input="updateValue" contenteditable=""></span>
</template>

<script>
export default {
    created(){
        this.$emit('update', this.value);
    },
    mounted(){
        this.$refs.text.textContent = this.value||""; 
    },
    props:{
        value : String,
        className : String,
        styleAttr: String
    },
    watch:{
        value(v) {
            this.$refs.text.textContent = v;        
        } 
    },
    data() {
        return {
            classes : ""
        }
    },
    methods:{
        updateValue($event){
            this.$emit('update', $event.target.textContent);
        },
        pasteOnlyText(e){
            e.preventDefault();
            var text = (e.originalEvent || e).clipboardData.getData('text/plain');
            document.execCommand("insertHTML", false, text);
            this.updateValue(e);
        },
    }
}
</script>