<template>
  <div class="gameArea">
    <h3 class="tittle">Find picture</h3>
    <h1 class="desc">Select one of the open cards and click the "?".If you find the right answer, you are won</h1>
{{answer}}
    <div class="container">

      <transition-group class="container">
        <card
          appear
          class="animate__animated animate__zoomInDown animate__repeat-3"
          @click.native="selectedCard = card.id"
          :class="{ shadow: selectedCard == card.id }"
          v-for="card in cards"
          :card="card"
          :key="card.id"
        ></card>

      </transition-group>
    </div>

    <div class="container">
      <transition-group>
        <component
          class="animate__animated animate__slideInUp"
          mode="in-out"
          :is="activeCard"
          @click.native="showCard(answer)"
          :card="answer"
          :key="answer.id"
        ></component>
      </transition-group>
    </div>
  </div>
</template>
<script>
import card from "./card";
import defaultCard from "../components/defaultCard";
export default {
  components: {
    card,
    defaultCard,
  },
  data() {
    return {
      selectedCard: null,
      activeCard: "defaultCard",
      cardName:null,
      answer: {},
      cards: [
        { id: "1", component: "card", image: "card-1.jpg",name:"Ahmed" },
        { id: "2", component: "card", image: "card-2.jpg",name:"Aydan" },
        { id: "3", component: "card", image: "card-3.jpg",name:"Simran" },
        { id: "4", component: "card", image: "card-4.jpg",name:"Amir" },
        { id: "5", component: "card", image: "card-5.jpg",name:"Asgar" },
        { id: "6", component: "card", image: "card-6.jpg" ,name:"Azad"},
        { id: "7", component: "card", image: "card-7.jpg",name:"Elchin" },
        { id: "8", component: "card", image: "card-8.jpg",name:"Farman" },
        { id: "9", component: "card", image: "card-9.jpg",name:"Ruhin" },
      ],
    };
  },
  created() {
    let answer = Math.ceil(Math.random() * this.cards.length);
    this.answer = this.cards[answer - 1];

    console.log(this.answer);
  },
  methods: {
    showCard(answer) {
      if (this.selectedCard == null) {
        alert("Select one pic");
      } else {
        this.activeCard = answer.component;
        this.cardName=answer.name;
        setTimeout(() => {
          if (answer.id == this.selectedCard) {
            this.$emit("data", "win");
          } else {
            this.$emit("data", "lost");
          }
        }, 2000);
      }
    },
  },
};
</script>

<style scoped>
.tittle {
  text-align: center;
  color: blueviolet;
}
.desc {
  text-align: center;
  font-size: 15px;
  color: rgb(12, 79, 82);
}
.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  text-align: center;

}
.shadow {
  box-shadow: 0px 5px 48px rgb(253, 6, 6) !important;
}
</style>