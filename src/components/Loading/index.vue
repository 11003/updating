<template>
    <div class="loader">
        <div class="bg"></div>
        <div class="circle"></div>
        <div class="circle"></div>
        <div class="circle"></div>
        <div class="circle"></div>
        <div class="circle"></div>
    </div>
</template>

<script>
export default {
name: "index"
}
</script>

<style scoped>

.loader {
    width: 50px;
    height: 50px;
    margin-bottom: 3px;
}

.loader .circle {
    position: absolute;
    width: 38px;
    height: 38px;
    opacity: 0;
    transform: rotate(225deg);
    animation-iteration-count: infinite;
    animation-name: orbit;
    animation-duration: 5.5s;
}

.loader .circle:after {
    content: '';
    position: absolute;
    width: 6px;
    height: 6px;
    border-radius: 5px;
    background: #fff;
    box-shadow: 0 0 9px rgba(255, 255, 255, .3);
}

.loader .circle:nth-child(2) {
    animation-delay: 240ms;
}

.loader .circle:nth-child(3) {
    animation-delay: 480ms;
}

.loader .circle:nth-child(4) {
    animation-delay: 720ms;
}

.loader .circle:nth-child(5) {
    animation-delay: 960ms;
}

.loader .bg {
    position: absolute;
    width: 70px;
    height: 70px;
    margin-left: -16px;
    margin-top: -16px;
    border-radius: 13px;
    background-color: rgba(0, 109, 174, 0.69);
}

@keyframes orbit {
    0% {
        transform: rotate(225deg);
        opacity: 1;
        animation-timing-function: ease-out;
    }
    7% {
        transform: rotate(345deg);
        animation-timing-function: linear;
    }
    30% {
        transform: rotate(455deg);
        animation-timing-function: ease-in-out;
    }
    39% {
        transform: rotate(690deg);
        animation-timing-function: linear;
    }
    70% {
        transform: rotate(815deg);
        opacity: 1;
        animation-timing-function: ease-out;
    }
    75% {
        transform: rotate(945deg);
        animation-timing-function: ease-out;
    }
    76% {
        transform: rotate(945deg);
        opacity: 0;
    }
    100% {
        transform: rotate(945deg);
        opacity: 0;
    }
}
</style>
