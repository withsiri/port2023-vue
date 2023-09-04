<script setup>
import { siteText } from "../constants";
</script>

<template>
    <section id="site">
        <div class="site_inner">
            <h2 class="site_title">site coding <em>나의 작업물</em></h2>
            <div class="site_wrap">
                <article class="site_item" v-for="(site, key) in siteText" :key="key">
                    <span class="num">{{ key+1 }}.</span>
                    <div class="text">
                        <div>{{ site.text[0] }}</div>
                        <div>{{ site.text[1] }}</div>
                        <div>{{ site.text[2] }}</div>
                    </div>
                    <h3 class="title">{{ site.title }}</h3>
                    <div class="btn">
                        <a :href="site.code">code</a>
                        <a :href="site.view">site</a>
                    </div>
                    <div class="info">
                        <span>{{ site.info[0] }}</span>
                        <span>{{ site.info[1] }}</span>
                        <span>{{ site.info[2] }}</span>
                    </div>
                </article>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@import "@/assets/scss/mixin";
.site_inner {
    padding: 16px;

    .site_title {
        position: sticky;
        top: 70px;
        left: 0;
        width: 70%;
        height: 5vw;
        font-size: 4vw;
        font-weight: 900;
        line-height: 1.6;
        font-family: var(--mainKor-font);
        text-transform: uppercase;
        color: var(--black100);
        border-bottom: 0.4vw solid var(--black100);
        margin-bottom: 100px;

        @media (max-width: 800px){
            width: 100%;
            height: auto;
            margin-bottom: 10vw;
            font-size: 30px;
            background-color: var(--mainBg-color);
            top: 68px;
            z-index: 100; 
        }

        em {
            font-size: 1.25rem;
            font-weight: 400;
            line-height: 2;
        }
    }
    .site_wrap {
        .site_item {
            height: 70vh;
            @include flex-center;
            flex-direction: column;
            position: sticky;
            left: 0;

            &:nth-child(1) {
                background-color: var(--subBg100);
                top: 180px; 

                @media (max-width: 800px){
                    top: 140px;
                }
            }
            &:nth-child(2) {
                background-color: var(--subBg200);
                top: 200px;

                @media (max-width: 800px){
                    top: 160px;
                }
            }
            &:nth-child(3) {
                background-color: var(--subBg300);
                top: 220px;

                @media (max-width: 800px){
                    top: 180px;
                }
            }
            &:nth-child(4) {
                background-color: var(--subBg400);
                top: 240px;

                @media (max-width: 800px){
                    top: 200px;
                }
            }
            .num {
                position: absolute;
                left: 1vw;
                top: 1vw;
                font-size: 5vw;
                line-height: 1;
                font-family: var(--mainNum-font);
                font-weight: 900;

                @media (max-width: 800px){
                    font-size: 80px;
                    left: 20px;
                    top: 20px;
                }
            }
            .text {
                text-align: center;
                margin-bottom: 1rem;

                > div {
                    font-size: 3vw;
                    line-height: 1;
                    font-weight: 900;
                    text-transform: uppercase;
                    text-decoration: underline;
                    font-family: var(--mainEng-font);
                
                    @media (max-width: 800px){
                        font-size: 26px;
                    }
                }
            }
            .title {
                font-family: var(--mainKor-font);
                margin-bottom: 1rem;
            }
            .btn {
                a {
                    text-transform: uppercase;
                    color: var(--black200);
                    font-size: 1rem;
                    transition: all 0.3s;

                    &:hover {
                        color: var(--black);
                        text-decoration: underline;
                    }
                }
            }
            .info {
                position: absolute;
                left: 0;
                bottom: 3%;
                width: 98%;
                margin-left: 1%;
                border-top: 1px solid var(--black);
                border-bottom: 1px solid var(--black);
                display: flex;
                justify-content: space-between;
                
                @media (max-width: 800px){
                    flex-direction: column;
                    width: 90%;
                    margin-left: 5%;
                    padding: 5px 0;
                }

                span {
                    font-family: var(--mainKor-font);
                    font-size: 12px;
                    padding: 3px 0;
                    text-transform: uppercase;
                }
            }
        }
    }
}
</style>
