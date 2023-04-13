<script>
export default {
    name: "ContentSection",
    data() {
        return {
            ctas: [
                {
                    name: 'DIGITAL COMICS',
                    images:'buy-comics-digital-comics.png',
                    url:'#'
                },
                {
                    name: 'DC MERCHANDISE',
                    images:'buy-comics-merchandise.png',
                    url:'#'
                },
                {
                    name: 'SUBSCRIPTION',
                    images:'buy-comics-subscriptions.png',
                    url:'#'
                },
                {
                    name: 'COMIC SHOP LOCATOR',
                    images:'buy-comics-shop-locator.png',
                    url:'#'
                },
                {
                    name: 'DC POWER VISA',
                    images:'buy-dc-power-visa.svg',
                    url:'#'
                },
            ]
        }
    },
    methods: {
        getImagePath(img) {
            return new URL(`../assets/img/${img.images}`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <main>
        <section class="top">
            <div class="content">
                <h2> --> Content goes here &lt;-- </h2>
            </div>
        </section>
        <section class="bottom">
            <div class="cta">
                <ul>
                    <li v-for="image in ctas">
                     <a :href="image.url">
                        <img :src="getImagePath(image)" alt="">
                        <p>{{ image.name }}</p>
                     </a>
                    </li>
                </ul>
            </div>
        </section>
    </main>
</template>

<style scoped lang="scss">
.top{
    background-color: #1C1C1C;
    .content {
     display: flex;
     align-items: center;
     width: 70%;
     height: 100px;
     margin: 0 auto;
     color: white;
    }
}
.bottom {
    background-color: #0082F9;
    padding: 2rem;
    position: relative;
    z-index: 998;
    .cta {
        width: 70%;
        margin: 0 auto;
        ul {
            display: flex;
            align-items: center;
            justify-content: center;
            li {
                list-style: none;
                padding: 0 1rem;
                a {
                    text-decoration: none;
                    color: inherit;
                    display: flex;
                    align-items: center;
                    font-size: 0.8rem;
                    img {
                        width: 50px;
                    }
                    p {
                        padding: 0 10px;
                        color: white;
                    }
                }
            }
        }
    }
}
</style>