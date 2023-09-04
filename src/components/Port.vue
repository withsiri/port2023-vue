<script setup>
import { portText } from "../constants";
</script>

<template>
    <section id="port">
        <div class="port_inner">
            <h2 class="port_title">PORTFOLIO <em>포폴 작업물</em></h2>
            <div class="port_wrap">
                <article class="port_item" v-for="(port, key) in portText" :key="key">
                    <span class="num">{{ port.num }}.</span>
                    <a :href="port.code" target="_blank" class="img"><img :src="port.img" :alt="port.name"></a>
                    <h3 class="title">{{  port.title }}</h3>
                    <p class="desc">{{ port.desc }}</p>
                    <a :href="port.view" target="_blank" class="site">사이트 보기</a>
                </article>
            </div>
        </div>
    </section>
</template>

<style lang="scss">
#port {
    width: 100%;
    margin-top: 30vh;
    padding-top: 56px;
    //overflow: hidden;
}

.port_inner {
    padding: 16px;

    .port_title {
        width: 100%;
        height: 5vw;
        font-size: 4vw;
        font-weight: 900;
        line-height: 1.6;
        font-family: var(--mainKor-font);
        text-transform: uppercase;
        color: var(--black100);
        border-bottom: 0.4vw solid var(--black100);
        margin-bottom: 16px;
        text-indent: -0.26vw;

        @media (max-width: 800px){
            width: 100%;
            margin-bottom: 16px;
            font-size: 30px;
            height: auto;
            top: 68px;
            z-index: 1000;
            background-color: var(--mainBg-color);
        }

        em {
            font-size: 1.25rem;
            font-weight: 400;
            line-height: 2;
        }
    }
    .port_wrap {
        display: flex;
        flex-wrap: wrap;
        width: 7000px;

        .port_item {
            width: 500px;
            height: 75vh;
            background-color: var(--subBg100);
            padding: 2.5rem;
            margin-right: 20px;
            
            @media (max-width: 800px) {
                width: 400px;
                padding: 40px 30px;
                height: auto;
            }

            &:nth-child(1) {
                background-color: var(--subBg100);
            }
            &:nth-child(2) {
                background-color: var(--subBg200);
            }
            &:nth-child(3) {
                background-color: var(--subBg300);
            }
            &:nth-child(4) {
                background-color: var(--subBg400);
            }
            &:nth-child(5) {
                background-color: var(--subBg500);
            }
            &:nth-child(6) {
                background-color: var(--subBg100);
            }
            &:nth-child(7) {
                background-color: var(--subBg200);
            }
            &:nth-child(8) {
                background-color: var(--subBg300);
            }
            &:nth-child(9) {
                background-color: var(--subBg400);
            }
            &:nth-child(10) {
                background-color: var(--subBg500);
            }

            .num {
                font-size: 2rem;
                font-family: var(--mainNum-font);
            }
            .img {
                display: block;
                margin-top: -20px;
                transition: margin-top 0.3s;

                &:hover {
                    margin-top: 0;
                }

                img {
                    border-radius: 10px;
                    filter: saturate(0%);
                    transition: all 0.3s;
                    
                    &:hover {
                        filter: saturate(100%); 
                    }
                }
            }
            .title {
                font-size: 1.5rem;
                text-align: center;
                font-weight: 700;
                color: var(--black100);
                border-bottom: 2px solid var(--black100);
                padding: 0.8rem 0;
                margin-bottom: 1rem;
            }
            .desc {
                font-size: 1rem;
            };
            .site {
                border: 1px solid var(--black100);
                display: block;
                text-align: center;
                padding: 0.625rem 1.5rem;
                margin-top: 1.5rem;

                &:hover {
                    background-color: var(--black);
                    color: #fff;
                }
            }
        }
    }
}
</style>