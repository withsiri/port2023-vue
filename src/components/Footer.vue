<script setup>
import { footerText } from "../constants";
</script>

<template>
    <footer id="footer" role="contentinfo">
        <div class="footer_inner">
            <h2 class="footer_text">
                <div>withsiri91</div>
                <div>@siri</div>
            </h2>
            <!-- //footer_text -->
            <div class="footer_info">
                <div class="left">
                    <div class="title"><a href="#">sign up</a></div>
                    <p class="desc">회원가입을 하시면 댓글과 게시판 기능을 이용할 수 있습니다.</p>
                </div>
                <div class="right">
                    <h3>social</h3>
                    <ul>
                        <li v-for="(footer, key) in footerText" :key="key">
                            <a :href="footer.link" target="_blank" title="새창열림">{{ footer.title }}</a>
                            <em>{{ footer.desc }}</em>
                        </li>
                    </ul>
                </div>

            </div>
            <!-- //footer_info -->
            <div class="footer_bottom">
                &copy;2023 withsiri91<br />
                이 사이트는 뷰를 이용하여 제작하였습니다.
            </div>
            <!-- //footer_bottom -->
        </div>
    </footer>
</template>

<style lang="scss">
#footer {
    font-family: var(--mainKor-font);
}
.footer_inner {
    padding: 16px;

    .footer_text {
        font-size: 12px;
        border-top: 1px solid var(--black);
        border-bottom: 1px solid var(--black);
        display: flex;
        justify-content: space-between;
    }
    .footer_info {
        display: flex;
        justify-content: space-between;
        margin: 100px 0px;

        @media (max-width: 800px){
            flex-direction: column;
        }

        .left {
            width: 40%;

            @media (max-width: 800px){
                width: 100%;
            }

            .title {
                border-top: 2px solid var(--black);
                border-bottom: 1px solid var(--black);
                padding: 20px 0;
                text-transform: uppercase;
                font-weight: 700;
                background: url(@/assets/img/arrow.svg) no-repeat right 20px;
                transition: all 0.3s;
                font-size: 16px;

                &:hover {
                    background-color: var(--black400);
                    padding-left: 10px;
                    border-color: transparent;
                }
            }

            .desc {
                font-size: 12px;
                padding-top: 20px;

                @media (max-width: 800px){
                    margin-bottom: 40px;
                }
            }
        }
        .right {
            width: 50%;

            @media (max-width: 800px){
                width: 100%;
            }

            h3 {
                border-top: 2px solid var(--black);
                font-size: 16px;
                margin-bottom: 20px;
                padding-top: 20px;
                font-weight: 700;
                text-transform: uppercase;
            }
            ul {
                border-top: 2px solid var(--black);
                
                li {
                    border-bottom: 1px solid var(--black); 
                
                    a {
                        padding: 14px 0;
                        font-size: 14px;
                        display: inline-block;
                        text-transform: uppercase;
                    }
                    em {
                        font-size: 12px;
                        padding-left: 10px;
                        opacity: 0;
                        transition: all 0.3s; 
                    }
                    &:hover {
                        em {
                            opacity: 1;
                        }
                    }
                }
            }
        }
    }
    .footer_bottom {
        text-align: center;
        text-transform: uppercase;
        font-size: 12px;
        margin-bottom: 20px;
    }
}
</style>