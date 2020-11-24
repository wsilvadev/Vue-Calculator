<template>
    <div class="hello">
        <button id="but" @click="test">{{ value }}</button>
    </div>
</template>

<script>
export default {
    data() {
        return {};
    },
    props: {
        value: String
    },
    methods: {
        test: function() {
            this.$emit('clicking');
        }
    }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#but {
    text-align: center;
    font-size: 40px;
    font-family: 'Courier New', Courier, monospace;
    color: azure;
    background-color: blueviolet;
    width: 20rem;
    height: 5rem;
    border-radius: 2vh;
    box-shadow: 3px 5px 5px lightslategrey;
}
</style>
