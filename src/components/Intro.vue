<script setup>
import { introText } from "../constants";
</script>

<template>
    <section id="intro">
        <div class="intro_inner">
            <h2 class="intro_title">{{ introText.title }}</h2>
            <div class="intro_lines" aria-hidden="true">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
            <div class="intro_text">
                <div class="text">
                    <div>{{  introText.desc[0] }}</div>
                    <div>{{  introText.desc[1] }}</div>
                    <div>{{  introText.desc[2] }}</div>
                </div>
                <div class="img">
                    <img src="@/assets/img/about.jpg" alt="about image">
                </div>
                
            </div>
            <div class="intro_lines bottom" aria-hidden="true">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@import "@/assets/scss/mixin";

#intro {
    height: 100vh;
}
.intro_inner {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: flex-start;
    justify-content: flex-end;
    flex-direction: column;
    padding: 16px;

    @media (max-width: 800px){
        justify-content: center;
    }

    .intro_title {
        font-size: 10vw;
        text-transform: uppercase;
        line-height: 1;
        font-weight: 800;
        white-space: nowrap;
        text-indent: -0.5vw;
        letter-spacing: -0.3vw;

        @media (max-width: 320px) {
            display: none;
        }
    }
    .intro_text {
        @include flex-center;
        position: relative;
        width: 100%;
        height: 40vh;
        background-color: var(--black);
        color: var(--white);
        flex-direction: column;
        cursor: all-scroll;
        transition: all 0.3s;

        .text {
            font-size: 3vw;
            line-height: 1;
            font-weight: 900;
            text-transform: uppercase;
            text-decoration: underline;
            text-align: center;
            position: relative;
            z-index: 100;

            @media (max-width: 800px){
                font-size: 24px;
            }
        }
        &:hover .text {
            opacity: 0;
        }
        .img {
            @include position-center;
            width: 30vh;
            height: 30vh;
            border-radius: 50%;
            overflow: hidden;
            filter: grayscale(100%);
            transition: all 0.3s;

            @media (max-width:320px){
                width: 20vh;
                height: 20vh;
            }
        }
        &:hover .img {
            filter: grayscale(0%);
        }
    }
    .intro_lines {
        width: 100%;

        .line {
            display: block;
            width: 100%;
            background-color: var(--black);
            height: 1px;
            margin-bottom: 0.5vw;

            &:nth-child(1){
                height: 1px; 
            }
            &:nth-child(2){
                height: 2px; 
            }
            &:nth-child(3){
                height: 5px; 
            }
            &:nth-child(4){
                height: 9px; 
            }
            &:nth-child(5){
                height: 13px; 
            }
            &:nth-child(6){
                height: 17px; 
            }
            &:nth-child(7){
                height: 25px; 
            }
        }
        &.bottom {
            .line {
                margin-top: 0.5vw;
                margin-bottom: 0;
                display: none;

                @media (max-width: 800px){
                    display: block;
                }
            }
            &:nth-child(1) {
                height: 25px;
            }
            &:nth-child(2) {
                height: 17px;
            }
            &:nth-child(3) {
                height: 13px;
            }
            &:nth-child(4) {
                height: 9px;
            }
            &:nth-child(5) {
                height: 5px;
            }
            &:nth-child(6) {
                height: 2px;
            }
            &:nth-child(7) {
                height: 1px;
            }
        }
    }
}
</style>