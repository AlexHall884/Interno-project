<template>
    <div>
        <header class="header center">
            <div class="header__left">
                <router-link to="/home" class="header__logo">
                    <svg class="header__logo-img" xmlns="http://www.w3.org/2000/svg" width="34" height="34"
                        viewBox="0 0 34 34" fill="none">
                        <path
                            d="M0 34.0003H13.4588V24.499C13.4588 22.4853 15.0898 20.8543 17.1035 20.8543C19.1172 20.8543 20.7482 22.4853 20.7482 24.499V34.0003H33.9975V0C15.2211 0 0 15.2211 0 34.0003Z"
                            fill="#CDA274" />
                    </svg>
                    <span class="header__logo-text">Interno</span>
                </router-link>
            </div>
            <div class="header__right">
                <div class="menubar">
                    <router-link class="menubar__item" to="/home">Home</router-link>
                    <router-link class="menubar__item" to="/project">Project</router-link>
                    <router-link class="menubar__item" to="/blog">Blog</router-link>
                </div>
            </div>
        </header>
    </div>
</template>

<script>
export default {
    name: 'HeaderBlockComp',

    data() {
        return {

        }
    },

    mounted() {

    },

    methods: {

    }
}
</script>

<style lang="scss" scoped>
@import "/src/stylesheets/_vars.scss";
@import "/src/stylesheets/style.scss";

//headear
.header {
    display: flex;
    align-items: center;
    min-height: 75px;
    margin-top: 53px;
    justify-content: space-between;
    margin-bottom: 57px;

    .header__left {
        .header__logo {
            color: $tittleColor;
            font-family: DM Serif Display;
            font-size: 40px;
            font-style: normal;
            font-weight: 400;
            line-height: 125%;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: all 0.3s;

            &:hover {
                scale: 1.1;
                color: $colorSiteSelect;

            }

            &:hover path {
                fill: $tittleColor;
            }


        }
    }

    .header__right {
        .menubar {
            display: flex;
            justify-content: flex-end;
            align-items: center;
            gap: 31px;

            .menubar__item {
                color: $tittleColor;
                text-align: center;
                font-family: Jost;
                font-size: 20px;
                font-style: normal;
                font-weight: 400;
                line-height: 125%;
                /* 25px */

                &:hover {
                    scale: 1.1;
                    color: $colorSiteSelect;
                }
            }
        }
    }

}

//tablet styles
@media (max-width: 1024px) {}
</style>
