<template>
<div>
    <h2>Books in Cart</h2>
    <div v-bind:key="book.bookid" v-for="book in cart">
        <CartItem v-bind:book="book" v-on:decrease:cartitem="Decrease" v-on:Increase:cartitem="Increase" v-on:Delete:cartitem="Delete"/>
    </div>
</div>
</template>

<script>
import CartItem from './CartItem.vue';
export default {
    name: "Cart",
    props: ["cart"],
    components: {
        CartItem
    },
    methods:{
        Decrease(bookId){
            this.$emit("decrease:cart",bookId);
        },
        Increase(bookId){
            this.$emit("Increase:cart",bookId);
        },
        Delete(bookId){
            this.$emit("Delete:cart",bookId);
        }
    }

}
</script>

<style scoped>
.book-item {
    background: #e6f2ff;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
}
</style>
