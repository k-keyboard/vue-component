<template>
    <li>
        <img src="https://cdn-icons-png.flaticon.com/512/2922/2922510.png" alt=""><br>
        <slot name="card-header"></slot>
        <slot name="card-button"></slot>
        <slot name="card-detail"></slot>
    </li>
</template>

<script>
export default {

}
</script>

<style scoped>
    li{
        margin: 1rem 0;
        font-size: 1.25rem;
        font-weight: bold;
        background: #257fe0;
        padding: .5rem;
        color: yellow;
        border-radius: 25px;
    }
    img{
        height: 100px;
        margin-top: 20px;
    }
</style>