<template @scroll.passive="onScroll">
  <header class="header" :class="{ active: scrollDown }">
    <nav class="header-navigation">
      <input type="text" class="search" placeholder="Поиск по всем категориям">
      <ul class="main-navigation">
        <swiper
          :slides-per-view="3"
          :space-between="50"
          :free-mode="true"
          grab-cursor
        >
          <swiper-slide>
            <li>
              <a href="#" class="navigation__button">Подборки</a>
            </li>
          </swiper-slide>
          <swiper-slide>
            <li>
              <a href="#" class="navigation__button">Все каталоги</a>
            </li>
          </swiper-slide>
          <swiper-slide>
            <li>
              <a href="#" class="navigation__button">Где поесть</a>
            </li>
          </swiper-slide>
          <swiper-slide>
            <li>
              <a href="#" class="navigation__button">Еда</a>
            </li>

          </swiper-slide>
          <swiper-slide>
            <li>
              <a href="#" class="navigation__button">Развлечение</a>
            </li>
          </swiper-slide>
          <swiper-slide>
            <li>
              <a href="#" class="navigation__button">И что-то еще</a>
            </li>
          </swiper-slide>
        </swiper>
      </ul>
    </nav>
  </header>
  <div class="block">
    <swiper
      :slides-per-view="3"
      :space-between="10"
      :free-mode="true"
      grab-cursor
    >
      <swiper-slide v-for="(elem, index) in elements" :key="index">
        <ListItem :elem="elem" :index="index == currentIndex" />
      </swiper-slide>
    </swiper>
  </div>
  <div class="block">
    <swiper
      :slides-per-view="3"
      :space-between="20"
      :free-mode="true"
      grab-cursor
    >
      <swiper-slide v-for="(elem, index) in elements2" :key="index">
        <ListItem :elem="elem" />
      </swiper-slide>
    </swiper>
  </div>
  <div class="block">
    <swiper
      :slides-per-view="3"
      :space-between="20"
      :free-mode="true"
      grab-cursor
    >
      <swiper-slide v-for="(elem, index) in elements3" :key="index">
        <ListItem :elem="elem" />
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import ListItem from "./components/ListItem.vue";
import "swiper/swiper-bundle.min.css";

export default {
  name: "App",
  data() {
    return {
      currentIndex: 0,
      scrollDown: true,
      pos: 0,
      elements: [
        {
          title: "1",
          text: "Небольшой пример текста, основанного на названии карточки и составляющего основную часть содержимого карточки.",
          img: "slider_01.jpg",
        },
        {
          title: "2",
          text: "Небольшой пример текста",
          img: "slider_02.jpg",
        },
        {
          title: "3",
          text: "Реклама информативная. В основном данный вид рекламы создает первичный спрос, позволяет потребителям запомнить бренд, а также указывает на преимущества конкретного продукта.",
          img: "slider_03.jpg",
        },
        {
          title: "4",
          text: "Реклама разъяснительная. Данный вид предназначен для подробного рассказа о преимуществах конкретного товара. Часто для этого используется мнение специалистов и экспертов",
          img: "slider_04.jpg",
        },
        {
          title: "5",
          text: "Реклама напоминающая. Ее главная задача заключается не в моментальной продаже продукта, а в убеждении потребителя в том, что он не ошибся, купив данный товар. В таком случае покупатель продолжит пользоваться рекламируемой продукцией.",
          img: "slider_05.jpg",
        },
      ],
      elements2: [
        {
          title: "1",
          text: "Небольшой пример текста, основанного на названии карточки и составляющего основную часть содержимого карточки.",
          img: "1.jpg",
        },
        {
          title: "2",
          text: "Небольшой пример текста",
          img: "2.jpg",
        },
        {
          title: "3",
          text: "Реклама информативная. В основном данный вид рекламы создает первичный спрос, позволяет потребителям запомнить бренд, а также указывает на преимущества конкретного продукта.",
          img: "3.jpg",
        },
        {
          title: "4",
          text: "Реклама разъяснительная. Данный вид предназначен для подробного рассказа о преимуществах конкретного товара. Часто для этого используется мнение специалистов и экспертов",
          img: "4.jpg",
        },
        {
          title: "5",
          text: "Реклама напоминающая. Ее главная задача заключается не в моментальной продаже продукта, а в убеждении потребителя в том, что он не ошибся, купив данный товар. В таком случае покупатель продолжит пользоваться рекламируемой продукцией.",
          img: "5.jpg",
        },
        {
          title: "6",
          text: "Реклама напоминающая. Ее главная задача заключается не в моментальной продаже продукта, а в убеждении потребителя в том, что он не ошибся, купив данный товар. В таком случае покупатель продолжит пользоваться рекламируемой продукцией.",
          img: "6.jpg",
        },
        {
          title: "7",
          text: "Реклама напоминающая. Ее главная задача заключается не в моментальной продаже продукта, а в убеждении потребителя в том, что он не ошибся, купив данный товар. В таком случае покупатель продолжит пользоваться рекламируемой продукцией.",
          img: "7.jpg",
        },
        {
          title: "8",
          text: "Реклама напоминающая. Ее главная задача заключается не в моментальной продаже продукта, а в убеждении потребителя в том, что он не ошибся, купив данный товар. В таком случае покупатель продолжит пользоваться рекламируемой продукцией.",
          img: "8.jpg",
        },
        {
          title: "9",
          text: "Реклама напоминающая. Ее главная задача заключается не в моментальной продаже продукта, а в убеждении потребителя в том, что он не ошибся, купив данный товар. В таком случае покупатель продолжит пользоваться рекламируемой продукцией.",
          img: "9.jpg",
        },
      ],
      elements3: [
        {
          title: "1",
          text: "Небольшой пример текста, основанного на названии карточки и составляющего основную часть содержимого карточки.",
          img: "cat_1.jpg",
        },
        {
          title: "2",
          text: "Небольшой пример текста",
          img: "cat_2.jpg",
        },
        {
          title: "3",
          text: "Реклама информативная. В основном данный вид рекламы создает первичный спрос, позволяет потребителям запомнить бренд, а также указывает на преимущества конкретного продукта.",
          img: "cat_3.jpg",
        },
        {
          title: "4",
          text: "Реклама разъяснительная. Данный вид предназначен для подробного рассказа о преимуществах конкретного товара. Часто для этого используется мнение специалистов и экспертов",
          img: "cat_4.jpg",
        },
        {
          title: "5",
          text: "Реклама напоминающая. Ее главная задача заключается не в моментальной продаже продукта, а в убеждении потребителя в том, что он не ошибся, купив данный товар. В таком случае покупатель продолжит пользоваться рекламируемой продукцией.",
          img: "cat_5.jpg",
        },
        {
          title: "6",
          text: "Реклама напоминающая. Ее главная задача заключается не в моментальной продаже продукта, а в убеждении потребителя в том, что он не ошибся, купив данный товар. В таком случае покупатель продолжит пользоваться рекламируемой продукцией.",
          img: "cat_6.png",
        },
      ],
    };
  },
  created() {
    window.addEventListener("scroll", this.onScroll);
  },
  destroyed() {
    window.removeEventListener("scroll", this.onScroll);
  },
  methods: {
    scrollY() {
      console.log("dada");
      this.scrollDown = false;
    },
    onScroll(event) {
      if (window.scrollY > this.pos) {
        this.scrollDown = true;
        this.pos = window.scrollY;
      } else if (window.scrollY < this.pos) {
        this.scrollDown = false;
        this.pos = window.scrollY;
      }
    },
  },
  components: {
    ListItem,
    Swiper,
    SwiperSlide,
  },
};
</script>

<style lang="scss" scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.header {
  position: sticky;
  top: 0;
  z-index: 20;
}
.header-navigation {
  margin: 0 auto 0px;
  background-color: white;
}
.search{
  width:90%;
  height:30px;
  padding:2px 16px 0 16px;
  margin-top:5px;
  margin-left:10px;
  font-size:16px;
  border: 1px solid rgba(51, 51, 51, 0.2);
  border-radius: 50px;
}
.block{
  margin-top:10px;
  margin-bottom:5px;
}
.main-navigation {
  /* display: flex;
  flex-direction: row;
  justify-content: flex-start;
  flex-wrap: wrap; */
  max-width: 100%;
  min-height: 40px;
  padding:0;
  margin:0 0 20px 0;
  li {
    text-align: center;
    font-size: 17px;
    list-style-type: none;
  }
  li a {
    display: block;
    text-decoration: none;
    padding: 16px 30px 20px 34px;
    color: black;
  }
}
.active {
  position: static;
} 
@media(max-width:480px){
  .search{
    width:430px;
  }
}
</style>
