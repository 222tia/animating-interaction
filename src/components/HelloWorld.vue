<template>

  <h1>Hatsune Miku Fun Facts</h1>

  <div class="container">

    <div
      v-for="(card, index) in cards"
      :key="index"
      class="card"
      @click="flipCard(index)"
    >

      <div :class="['card-inner', { flipped: card.flipped }]">
        <div class="card-face card-front">
          <Card>
            <p>{{ card.description }}</p>
          </Card>
        </div>
        <div class="card-face card-back">
          <p>{{ card.backInfo }}</p>
        </div>
      </div>

    </div>

  </div>

</template>

<script>
export default {
  data() {
    return {
      cards: [
        {
          description: "What does Hatsune Miku Mean?",
          backInfo: "The name of the character comes from merging the Japanese words for first (初, hatsu), sound (音, ne), and future (ミク, miku), thus meaning 'the first sound of the future',[2] which, along with her code name, refers to her position as the first of Crypton's 'Character Vocal Series' (abbreviated 'CV Series').",
          flipped: false
        },
        {
          description: "What is Miku's Representative Vegteable?",
          backInfo: "Leek",
          flipped: false
        },
        {
          description: "Who is Hatsune Miku?",
          backInfo: "Hatsune Miku is a Vocaloid software voicebank developed by Crypton Future Media.",
          flipped: false
        },
        {
          description: "What does Hatsune Miku do?",
          backInfo: "Miku's personification has been marketed as a virtual idol, and has performed at live virtual concerts onstage as an animated holographic projection",
          flipped: false
        },
        {
          description: "How old is Hatsune Miku?",
          backInfo: "Hatsune Miku is most commonly depicted as a 16 year old girl. She does not age.",
          flipped: false
        },
        {
          description: "When was Hatsune Miku released?",
          backInfo: "August 31, 2007",
          flipped: false
        },
        {
          description: "How many versions of Miku's voicebank are there?",
          backInfo: "There are 10 total, with Hatsune Miku SP, a refined and retuned version of her original VOCALOID4 (V4X) voicebank, being the most recent.",
          flipped: false
        },
        {
          description: "What is Miku Miku Beam?",
          backInfo: "Miku Miku Beam is an emote in Fortnite, referencing a scene from the music video for 'M@GICAL☆CURE! LOVE ♥ SHOT!' by Sawtowne featuring Hatsune Miku.",
          flipped: false
        },
      ]
    };
  },
  methods: {
    flipCard(index) {
      this.cards[index].flipped = !this.cards[index].flipped;
    }
  }
};
</script>

<style scoped>
/* main container */
.container {
  grid-template-columns: repeat(4, 1fr);
  justify-items: center; 
  align-items: center;  
  display: grid;
  justify-content: center;
  align-items: center;
  height: 100vh; 
}

/* container for cards */
.card {
  border-radius: 10px;
  width: 300px;
  height: 300px;
  perspective: 1000px;
}

.card-inner {
  position: relative;
  border-radius: 10px;
  width: 100%;
  height: 100%;
  transition: transform 0.6s;
  transform-style: preserve-3d;
}

.card:hover .card-inner,
.card.flipped .card-inner {
  transform: rotateY(180deg);
}

/* front of card */
.card-face {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
}

.card-front {
  padding:10px;
  border-radius: 10px;
  border: 1px solid #7acbdc;
  background-color: #ffffff;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* back of card */
.card-back {
  padding: 10px;
  border-radius: 10px;
  border: 1px solid #7acbdc;
  color: white;
  background-color: #7acbdc;
  transform: rotateY(180deg);
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>