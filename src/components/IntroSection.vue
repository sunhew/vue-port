<template>
    <div id="intro">
        <div class="intro__inner">
            <div class="intro__title">port developer</div>
            <div class="intro__lines" aria-hidden="true">
                <div class="line"></div>
                <div class="line"></div>
                <div class="line"></div>
                <div class="line"></div>
                <div class="line"></div>
                <div class="line"></div>
                <div class="line"></div>
            </div>
            <div class="intro__text">
                <div class="text">
                    <div>I'm so tired</div>
                    <div>It's hard</div>
                    <div>I won't give up</div>
                </div>
                <div class="img">
                    <img
                        src="https://images.unsplash.com/photo-1609505848912-b7c3b8b4beda?w=400&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NzR8fCVFQyVCNCU4OCVFQyU4MyU4MXxlbnwwfHwwfHx8MA%3D%3D"
                        alt=""
                    />
                </div>
                <div class="intro__lines bottom" aria-hidden="true">
                    <div class="line"></div>
                    <div class="line"></div>
                    <div class="line"></div>
                    <div class="line"></div>
                    <div class="line"></div>
                    <div class="line"></div>
                    <div class="line"></div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
#intro {
    height: 100vh;

    .intro__inner {
        margin-top: 25px;
        width: 100%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        padding: 16px;

        .intro__title {
            font-size: 10vw;
            line-height: 1;
            font-weight: 800;
            white-space: nowrap;
            text-transform: uppercase;
            letter-spacing: -0.3vw;
            text-indent: -17.6vw;
            color: var(--fontcol1);
        }
    }

    .intro__lines {
        width: 100%;
        .line {
            display: block;
            width: 100%;
            height: 1px;
            background-color: var(--linecol1);
            margin-bottom: 0.5vw;

            &:nth-child(1) {
                height: 1px;
            }
            &:nth-child(2) {
                height: 2px;
            }
            &:nth-child(3) {
                height: 5px;
            }
            &:nth-child(4) {
                height: 9px;
            }
            &:nth-child(5) {
                height: 13px;
            }
            &:nth-child(6) {
                height: 19px;
            }
            &:nth-child(7) {
                height: 22px;
            }
        }

        &:bottom {
            display: none;
        }
    }

    .intro__text {
        width: 100%;
        height: 40vh;
        background-color: var(--divcol1);
        color: var(--white);
        align-items: center;
        justify-content: center;
        flex-direction: column;
        position: relative;

        .text {
            font-size: 4vw;
            line-height: 1;
            font-weight: 900;
            top: 60px;
            text-transform: uppercase;
            text-decoration: underline;
            text-align: center;
            position: relative;
            z-index: 100;
            transition: all 0.3s;
            cursor: cell;

            div {
                padding-bottom: 23px;
            }
        }

        .img {
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            width: 30vh;
            height: 30vh;
            border-radius: 50%;
            overflow: hidden;
            transition: all 0.3s;
        }

        .intro__lines {
            display: none;
        }
    }
}
</style>
