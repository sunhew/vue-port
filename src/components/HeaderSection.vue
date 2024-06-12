<script setup>
import { headerNav } from '@/constants'
</script>

<template>
    <header id="header" role="banner">
        <div class="header__inner">
            <h1 class="header__logo">
                <a href="#">portfolio <em>vue.js</em></a>
            </h1>
            <div class="header__nav" :class="{ show: isNavVisible }" role="navigation" aria-label="메인 메뉴">
                <ul>
                    <li v-for="(nav, key) in headerNav" :key="key">
                        <a :href="nav.url" @click="scrollLink($event)">{{ nav.title }}</a>
                    </li>
                </ul>
            </div>
            <div class="header__nav__mobile" id="headerToggle" aria-controls="primary-menu" aria-expanded="false" role="button" tabindex="0" @click="toggleMobileMuen">
                <span></span>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    data() {
        return {
            isNavVisible: false
        }
    },
    methods: {
        toggleMobileMuen() {
            this.isNavVisible = !this.isNavVisible
        },
        scrollLink(event) {
            event.preventDefault()

            const targetId = event.target.getAttribute('href')
            const tagetElement = document.querySelector(targetId)

            if (tagetElement) {
                tagetElement.scrollIntoView({ behavior: 'smooth' })
            }
        }
    }
}
</script>

<style lang="scss">
@import '../assets/scss/maxin';

#header {
    @include position-fixed;
    z-index: 10000;

    .header__inner {
        @include flex-between;
        background-color: rgba(112, 168, 166, 0.1);
        backdrop-filter: blur(15px);
        padding: 1rem;

        .header__logo {
            font-size: 1.9rem;
            text-align: center;
            text-transform: uppercase;
            line-height: 1;

            em {
                font-size: 14px;
                display: block;
                color: var(--white);
            }
        }

        .header__nav {
            @media (max-width: 800px) {
                display: none;

                &.show {
                    display: block;

                    ul {
                        display: block;
                        position: absolute;
                        right: 0;
                        top: 68px;
                        background-color: rgba(92, 146, 155, 0.445);
                        backdrop-filter: blur(15px);
                        z-index: 10000;
                        min-width: 100px;
                        padding: 20px 0;

                        li {
                            display: block;
                            text-align: right;

                            a {
                                display: inline-block;
                                padding: 10px;
                                color: var(--white);
                            }
                        }
                    }
                }
                &.show + .header__nav__mobile span::before {
                    width: 20px;
                }
                &.show + .header__nav__mobile span::after {
                    width: 20px;
                }
            }
            li {
                display: inline;

                a {
                    font-size: 1rem;
                    padding: 14px;
                    position: relative;
                    text-transform: uppercase;
                    font-weight: 400;

                    &::before {
                        content: '';
                        height: 1px;
                        width: calc(100% - 28px);
                        background-color: var(--black);
                        position: absolute;
                        color: var(--black200);
                        left: 14px;
                        bottom: 10px;
                        transform: scaleX(0);
                        transition: all 0.3s;
                    }

                    &:hover::before {
                        transform: scaleX(1);
                    }
                }
            }
        }

        .header__nav__mobile {
            display: none;
            width: 40px;
            height: 40px;
            cursor: pointer;

            @media (max-width: 800px) {
                display: block;
            }

            span {
                display: block;
                width: 40px;
                height: 2px;
                background-color: var(--white);
                margin-top: 19px;
                position: relative;

                &::before {
                    content: '';
                    width: 40px;
                    height: 2px;
                    position: absolute;
                    background-color: var(--white);
                    top: 6px;
                    right: 0;
                    transition: width 0.3s;
                }

                &::after {
                    content: '';
                    width: 40px;
                    height: 2px;
                    position: absolute;
                    background-color: var(--white);
                    bottom: 6px;
                    left: 0;
                    transition: width 0.3s;
                }
            }
        }
    }
}
</style>
