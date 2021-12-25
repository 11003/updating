<template>
    <div class="loader-big">
        <Loading />
        <div class="center-msg">
            <p>正在进行更新 {{ time }}%</p>
            <p>请保持计算机打开状态。</p>
        </div>
        <div class="footer-msg">
            你的电脑将重启几次。
        </div>
    </div>
</template>

<script>
import Loading from "@/components/Loading"
export default {
    components: {
        Loading
    },
    data() {
        return {
            time: 0, // 更新的数字
            timer: null, // 清除定时器
            timeNumber: 1000, // 定时器时间
            pauseTimeNumber: 8888, // 停顿时间
            pauseTimeNumberArr: [5, 15, 20, 30, 40, 50] // 想要有所停顿的时间
        }
    },
    methods: {
        startTime() {
            this.timer = setInterval(() => {
                this.time++;
                this.pauseTime();
            }, this.timeNumber)
        },
        pauseTime() {
            this.endTime();
            if (this.pauseTimeNumberArr.length && this.pauseTimeNumberArr.includes(this.time)) {
                clearInterval(this.timer)
                setTimeout(() => {
                    this.timer = setInterval(() => {
                        this.time++;
                        this.pauseTime();
                    }, this.timeNumber)
                }, this.pauseTimeNumber)
            }
        },
        endTime() {
            // 在98%的时候停止定时器，虽然不会到这儿
            if(this.time >= 98) clearInterval(this.timer);
        }
    },
    mounted() {
        this.startTime();
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

.footer-msg {
    position: absolute;
    bottom: 8%;
    text-align: center;
    color: #fff;
    font-size: 18px;
}
</style>
