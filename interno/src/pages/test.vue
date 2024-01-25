<template>
    <div>
        <div ref="swiper" class="swiper-container">
            <div class="swiper-wrapper">
                <div v-for="(image, index) in images" :key="index" class="swiper-slide">
                    <img :src="image.src" :alt="image.alt" @click="openZoomedImage(image.src)" />
                </div>
            </div>
        </div>
        <div class="swiper-pagination"></div>
        <!-- <button class="swiper-button-next" @click="nextSlide">Next</button>
        <button class="swiper-button-prev" @click="prevSlide">Prev</button> -->

    </div>
</template>

<script>
import Swiper from 'swiper'
import 'swiper/scss'
import 'swiper/swiper-bundle.css';

export default {
    name: 'TestComp',

    data() {
        return {
            images: [
                { src: require("../assets/project_photo9.png"), alt: "photo 1" },
                { src: require("../assets/content_photo8.png"), alt: "photo 2" },
                { src: require("../assets/content_photo7.png"), alt: "photo 3" }
            ],
            swiperInstance: null
        };
    },
    mounted() {
        this.swiperInstance = new Swiper(this.$refs.swiper, {
            loop: true,
            pagination: {
                el: ".swiper-pagination",
                type: "bullets",
                clickable: true
            },
            navigation: {
                nextEl: ".swiper-button-next",
                prevEl: ".swiper-button-prev"
            }
        });
    },
    methods: {
        nextSlide() {
            this.swiperInstance.slideNext();
        },
        prevSlide() {
            this.swiperInstance.slidePrev();
        },
        openZoomedImage(imageSrc) {
            // Replace with logic to open a modal or trigger zoom functionality for the clicked image
            console.log("Zoom in on image: " + imageSrc);
        }
    }
};
</script>

<style lang="scss" scoped>
.swiper-container {
    width: 75%;
    height: 200px;
    margin: 20px auto;
    position: relative;
}

.swiper-slide img {
    width: 75%;
    height: 75%;
    object-fit: cover;
    cursor: pointer;
}

.swiper-pagination {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    bottom: 10px;
    width: 100%;
}

.swiper-pagination-bullet {
    width: 8px;
    height: 8px;
    background: red;
    color: blue;
    opacity: 0.5;
    margin: 0 5px;
    border-radius: 50%;
    cursor: pointer;
}

.swiper-pagination-bullet-active {
    background: #fff;
    opacity: 1;
}

// .swiper-pagination {
//     position: absolute;
//     bottom: 10px;
//     text-align: center;
//     width: 100%;
// }

// .swiper-pagination-bullet {
//     width: 8px;
//     height: 8px;
//     display: inline-block;
//     border-radius: 50%;
//     background: #000;
//     margin: 0 5px;
//     cursor: pointer;

// }

// .swiper-pagination-bullet-active {
//     background: #fff;
// }
</style>