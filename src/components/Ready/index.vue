<template>
    <div class="loader-big">
        <Loading />
        <div class="center-msg">
            <p>正在准备 Windows</p>
            <p>请勿关闭计算机</p>
        </div>
    </div>
</template>

<script>
import Loading from "@/components/Loading"
export default {
    components: {
        Loading
    }
}
</script>

<style scoped>
.loader-big {
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

.center-msg {
    text-align: center;
    color: #fff;
    font-size: 18px;
}
</style>
