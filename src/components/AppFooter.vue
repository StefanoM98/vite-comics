<script>
export default {
    name: "AppFooter",
    data() {
        return {
            links: {
                "DC COMICS": [
                    {
                        name: "Characters",
                        url: "#"
                    },
                    {
                        name: "Comics",
                        url: "#"
                    },
                    {
                        name: "Movies",
                        url: "#"
                    },
                    {
                        name: "TV",
                        url: "#"
                    },
                    {
                        name: "Games",
                        url: "#"
                    },
                    {
                        name: "Videos",
                        url: "#"
                    },
                    {
                        name: "News",
                        url: "#"
                    }
                ],
                "DC": [
                    {
                        name: "Terms Of Use",
                        url: "#"
                    },
                    {
                        name: "Privacy policy(New)",
                        url: "#"
                    },
                    {
                        name: "Ad Choices",
                        url: "#"
                    },
                    {
                        name: "Advertising",
                        url: "#"
                    },
                    {
                        name: "Jobs",
                        url: "#"
                    },
                    {
                        name: "Subscriptions",
                        url: "#"
                    },
                    {
                        name: "Talet Workshops",
                        url: "#"
                    },
                    {
                        name: "CPSC Certificates",
                        url: "#"
                    },
                    {
                        name: "Ratings",
                        url: "#"
                    },
                    {
                        name: "Shop Help",
                        url: "#"
                    },
                    {
                        name: "Contact Us",
                        url: "#"
                    }  
                ],
                "SITES": [
                    {
                        name: "DC",
                        url: "#"
                    },
                    {
                        name: "MAD Magazine",
                        url: "#"
                    },
                    {
                        name: "DC Kids",
                        url: "#"
                    },
                    {
                        name: "DC Universe",
                        url: "#"
                    },
                    {
                        name: "DC Power Visa",
                        url: "#"
                    },
                ],
                "SHOP": [
                    {
                        name: "Shop DC",
                        url: "#"
                    },  
                    {
                        name: "Shop DC Collectibles",
                        url: "#"
                    }
                ],
            },
            social: [
                {
                    images: 'footer-facebook.png',
                    url:'#'
                },
                {
                    images: 'footer-periscope.png',
                    url:'#'
                },
                {
                    images: 'footer-pinterest.png',
                    url:'#'
                },
                {
                    images: 'footer-twitter.png',
                    url:'#'
                },
                {
                    images: 'footer-youtube.png',
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
    <footer>
        <div class="top">
            <div class="cta">
                <div v-for="(elem, index) in links" class="card">
                    <h2>{{ index }}</h2>
                    <ul>
                        <li v-for="link in elem">
                            <a :href="link.url">
                                {{ link.name }}
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="image">
                <img src="../assets/img/dc-logo-bg.png" alt="">
            </div>
        </div>
        <div class="bottom">
            <div class="container">
                <div class="sign-up">
                    <a href="#">SIGN-UP NOW!</a>
                </div>

                <div class="links">
                    <h3>FOLLOW US</h3>
                    <ul>
                        <li v-for="img in social">
                            <a :href="img.url">
                            <img :src="getImagePath(img)" alt="">
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>
</template>

<style scoped lang="scss">
footer {
    height: 500px;
    background-image: url(../assets/img/footer-bg.jpg);
    background-position: center;
    .top {
        width: 80%;
        height: 100%;
        margin: 0 auto;
        display: flex;
        justify-content: space-between;
        position: relative;
        .cta {
            width: 40%;
            margin: 30px;
            color: white;
            display: flex;
            flex-wrap: wrap;
            .card {
                width: calc(100% / 3);
                height: 55%;
                h2 {
                    padding: 0.4rem 0;
                }
                ul {
                    list-style: none;
                    li {

                        padding: 4px 0;
                    }
                    a {
                        text-decoration: none;
                        color: inherit;
                        font-size: 0.8rem;
                    }
                }
            }
        }
        .image {
            position: absolute;
            top: -50px;
            right: 0;
            img {
                height: 100%;
                width: 100%;
                transform: scale(1.2);
            }
        }
    }
    .bottom {
        position: relative;
        z-index: 999;
        background-color: #303030;
        height: 100px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 80%;
            margin: 0 auto;
            .sign-up {
                a {
                    padding: 10px;
                    color: inherit;
                    text-decoration: none;
                    color: white;
                    border: 2px solid #0082F9;
                }
            }
            .links {
                display: flex;
                align-items: center;
                ul{
                    list-style: none;
                    display: flex;
                    li {
                        padding: 0 4px;
                    }
                }
            }

        }
    }
}
</style>