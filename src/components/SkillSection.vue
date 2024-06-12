<script setup>
import { skillText } from '@/constants'
</script>

<template>
    <section id="skill">
        <div class="skill_inner">
            <div class="skill_title">
                <h2>coding <em>도전기</em></h2>
            </div>
            <div class="skill_desc">
                <div v-for="(text, key) in skillText" :key="key">
                    <span>{{ key + 1 }}.</span>
                    <h3>{{ text.title }}</h3>
                    <p>{{ text.desc }}</p>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
#skill {
    min-height: 100vh;
}
.skill_inner {
    padding: 16px;
    display: flex;
    justify-content: space-between;

    @media (max-width: 800px) {
        flex-direction: column;
    }

    .skill_title {
        position: sticky;
        top: 100px;
        left: 0;
        width: 48%;
        height: 5vw;

        @media (max-width: 800px) {
            width: 100%;
            height: 35px;
            background-color: #616e8473;
            backdrop-filter: blur(5px);
        }

        h2 {
            font-size: 4vw;
            font-weight: 900;
            line-height: 0.7;
            text-transform: uppercase;
            color: var(--black);
            border-bottom: 3px solid #000;
            font-family: var(--mainKor-font);

            em {
                font-size: 1.25rem;
                font-weight: 400;
                line-height: 1.3;
            }
        }
    }
    .skill_desc {
        width: 50%;

        @media (max-width: 800px) {
            width: 100%;
        }

        span {
            font-size: 5vw;
            line-height: 1.3;
            font-weight: 900;
            font-family: var(--mainNum-font);
        }

        h3 {
            font-size: 1.5rem;
            text-decoration: underline;
            text-underline-position: under;
            margin-bottom: 1vw;
        }

        p {
            margin-bottom: 30vw;
            font-size: 1.1rem;
            color: var(--black300);
            line-height: 1.7;
        }
    }
}
</style>
