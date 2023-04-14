<script>
export default {
    name: "AppHeader",
    data() {
        return {
            links: [
                {
                    text:"CHARACTERS",
                    url: "#",
                    active: false
                },
                {
                    text:"COMICS",
                    url: "#",
                    active: true
                },
                {
                    text:"MOVIES",
                    url: "#",
                    active: false
                },
                {
                    text:"TV",
                    url: "#",
                    active: false
                },
                {
                    text:"GAMES",
                    url: "#",
                    active: false
                },
                {
                    text:"COLLECTIBLES",
                    url: "#",
                    active: false
                },
                {
                    text:"VIDEOS",
                    url: "#",
                    active: false
                },
                {
                    text:"FANS",
                    url: "#",
                    active: false
                },
                {
                    text:"NEWS",
                    url: "#",
                    active: false
                },
                {
                    text:"SHOP",
                    url: "#",
                    active: false
                }
            ]
        }
    }
}
</script>

<template>
    <header>
        <section class="left">
            <img src="../assets/img/dc-logo.png" alt="">
        </section>
        <section class="right">
            <ul class="navigation">
                <li v-for="(link, index) in links" :key="index" :class="link.active ? 'active': ''">
                    <a :href="link.url">{{ link.text }}</a>
                </li>
            </ul>
        </section>
    </header>
</template>

<style scoped lang="scss">
    header {
        width: 70%;
        margin: 0 auto;
        padding: 1rem 0;
        display: flex;
        align-items: center;
        justify-content: space-between;
        

        img {
            width: 70%;
        }
        .navigation {
            list-style: none;
            display: flex;
            li {
                font-size: 0.7rem;
                margin: 0 0.3rem;
                padding: 0 0.3rem;
                a {
                    color: inherit;
                    text-decoration: none;
                }
                &.active,
                &:hover{
                    color: #0082F9;
                }
            }
            li:hover {
                border-bottom: 2px solid #0082F9;
            }
        }
    }
</style>