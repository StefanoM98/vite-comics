<script>
import ProductCard from "./ProductCard.vue";
export default {
  name: "ContentSection",
  components: {
    ProductCard,
  },
  data() {
    return {
      superHero: [
        {
          thumb: "https://www.coverbrowser.com/image/action-comics/1-1.jpg",
          price: "$19.99",
          series: "Action Comics",
          type: "comic book",
        },
        {
          thumb:
            "https://www.panini.it/media/catalog/product/cache/a5b5dd3adfe0d321084804c738f29601/M/1/M1BLLA015ISBN_0.jpg",
          price: "$3.99",
          series: "American Vampire 1976",
          type: "comic book",
        },
        {
          thumb:
            "https://media.wired.com/photos/593384dad80dd005b42b2817/master/w_2560%2Cc_limit/Aquaman-16.jpg",
          price: "$16.99",
          series: "Aquaman",
          type: "graphic novel",
        },
        {
          thumb: "https://d29xot63vimef3.cloudfront.net/image/batgirl/1-1.jpg",
          price: "$2.99",
          series: "Batgirl",
          type: "comic book",
        },
        {
          thumb:
            "https://static.posters.cz/image/750/locandine-film-in-plexiglass-batman-prowl-comic-cover-i69653.jpg",
          price: "$3.99",
          series: "Batman",
          type: "comic book",
        },
        {
          thumb:
            "https://static.wikia.nocookie.net/marvel_dc/images/5/50/Batman_Beyond_v.1_1.jpg",
          price: "$2.99",
          series: "Batman Beyond",
          type: "comic book",
        },
        {
          thumb:
            "https://static.wikia.nocookie.net/marvel_dc/images/0/0d/Batman_Superman_Vol_1_1.jpg",
          price: "$3.99",
          series: "Batman/Superman",
          type: "comic book",
        },
        {
          thumb:
            "https://static.wikia.nocookie.net/marvel_dc/images/c/cf/Batman_Superman_Annual_Vol_2_1.jpg",
          price: "$4.99",
          series: "Batman/Superman Annual",
          type: "comic book",
        },
        {
          thumb:
            "https://static.wikia.nocookie.net/marvel_dc/images/5/54/Batman_The_Joker_War_Zone_Vol_1_1.jpg",
          price: "$5.99",
          series: "Batman: The Joker War Zone",
          type: "comic book",
        },
        {
          thumb:
            "https://static.wikia.nocookie.net/marvel_dc/images/6/64/Batman_Three_Jokers_Collected.jpg",
          price: "$6.99",
          series: "Batman: Three Jokers",
          type: "comic book",
        },
        {
          thumb:
            "https://static.wikia.nocookie.net/marvel_dc/images/f/f8/Batman_White_Knight_Presents_Harley_Quinn_Vol_1_1.jpg",
          price: "$4.99",
          series: "Batman: White Knight Presents: Harley Quinn",
          type: "comic book",
        },
        {
          thumb:
            "https://static.wikia.nocookie.net/marvel_dc/images/c/c8/Catwoman_Vol_2_1.jpg",
          price: "$16.99",
          series: "Catwoman",
          type: "graphic novel",
        },
      ],
      ctas: [
        {
          name: "DIGITAL COMICS",
          images: "buy-comics-digital-comics.png",
          url: "#",
        },
        {
          name: "DC MERCHANDISE",
          images: "buy-comics-merchandise.png",
          url: "#",
        },
        {
          name: "SUBSCRIPTION",
          images: "buy-comics-subscriptions.png",
          url: "#",
        },
        {
          name: "COMIC SHOP LOCATOR",
          images: "buy-comics-shop-locator.png",
          url: "#",
        },
        {
          name: "DC POWER VISA",
          images: "buy-dc-power-visa.svg",
          url: "#",
        },
      ],
    };
  },
  methods: {
    getImagePath(img) {
      return new URL(`../assets/img/${img.images}`, import.meta.url).href;
    },
  },
};
</script>

<template>
  <main>
    <section class="top">
      <div class="content"></div>
    </section>

    <section class="mid">
      <div class="container">
        <div class="text">
          <a href="#">current series</a>
        </div>
        <div class="row">
          <ProductCard
            v-for="(comics, index) in superHero"
            :key="index"
            :img="comics.thumb"
            :series="comics.series"
          />
          <a href="#" class="more">load more</a>
        </div>
      </div>
    </section>

    <section class="bottom">
      <div class="cta">
        <ul>
          <li v-for="(image, index) in ctas" :key="index">
            <a :href="image.url">
              <img :src="getImagePath(image)" alt="" />
              <p>{{ image.name }}</p>
            </a>
          </li>
        </ul>
      </div>
    </section>
  </main>
</template>

<style scoped lang="scss">
.top {
  height: 400px;
  background-image: url(../assets/img/jumbotron.jpg);
}

.mid {
  background-color: black;

  .container {
    width: 70%;
    margin: auto;
    .text {
      color: white;
      a {
        padding: 10px;
        position: relative;
        top: -20px;
        margin: 30px 0;
        color: inherit;
        text-decoration: none;
        text-transform: uppercase;
        font-weight: 700;
        background-color: #0082f9;
      }
    }
    .row {
      display: flex;
      justify-content: center;
      align-items: stretch;
      flex-wrap: wrap;
    }
    .more {
      position: relative;
      bottom: 30px;
      padding: 20px;
      color: white;
      text-transform: uppercase;
      text-decoration: none;
      background-color: #0082f9;
    }
  }
}
.bottom {
  background-color: #0082f9;
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
