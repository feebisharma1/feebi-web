<template>
<section class="bg-light page-section" id="portfolio">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 text-center">
          <h2 class="section-heading text-uppercase">Portfolio</h2>
        </div>
      </div>

  <div id="app">
    <div class="card-row">
    <div v-for="(card, index) in cards" 
        :key="index"
        :ref="`card_${index}`"
        @mouseover="hoverCard(index)"
        @mouseout="hoverCard(-1)"
        class="card">
      
      <img class="card-image" 
        :class="{'selected': isSelected(index)}"
        :src="card.image">
      
      <div class="card-footer">
        <h3 class="card-title">{{card.title}}</h3>
      </div>
    </div>
  
  </div>
  </div>
  </div>

</section>
</template>

<script>
export default {
    
name: 'app',
  data() {
    return {
      selectedCard: -1,
      cards: [
        {
         title: 'New York', 
         
         image: require('/Users/feebisharma1/Desktop/webby/myweb/src/assets/img/pipi.jpg')
        },
        {
          title: 'Washigton DC', 
         
          image: require('/Users/feebisharma1/Desktop/webby/myweb/src/assets/img/kiki.jpg')
        },
        {
          title: 'San Francisco', 
           
          image: require('/Users/feebisharma1/Desktop/webby/myweb/src/assets/img/mimi.jpg')
        },
         {
          title: 'Las Vegas', 
          
          image: require('/Users/feebisharma1/Desktop/webby/myweb/src/assets/img/cic.jpg')
        }
      ]
    }
  },
  methods: {
    hoverCard(selectedIndex) {
      this.selectedCard = selectedIndex
    },
    isSelected(cardIndex) {
      return this.selectedCard === cardIndex
    }
  }
}
</script>
<style scoped>
body {
    background-color: #E1E7E7;
  }
  
  .card-row {
    display: flex;
    justify-content: center;
    align-items: center;  
    min-width: 780px;
    width: 100%;
    height: 500px;
  }
  
  .card {
    position: relative;
    background-color: #FFFFFF;
    height: 370px;
    width: 240px;
    margin: 10px;
    overflow: hidden;
    box-shadow: 0px 2px 4px 0px rgba(0,0,0,0.5);
  }
  
  .card-image {
    /* center horizontally overflown image */
    position: absolute;
    left: -9999px;
    right: -9999px;
    margin: auto;
  
    height: 300px;
    min-width: 100%;
  
    transition: height 0.3s, opacity 0.3s;
  }
  .card-image.selected {
    height: 410px;
    opacity: 0.3;
  }
  
  .card-footer {
    position: absolute;
    bottom: 0;
    height: 50px;
    padding: 10px 15px;
    font-family: Helvetica;
  }
  .card-text {
    font-size: 14px;
    color: rgba(0, 0, 0, 0.7);
  }
  .card-title {
    font-family: Serif;
  }
  
  .card-author.selected {
    color: #6a6456;
  }
  .card {
    /* the other rules */
    transition: height 0.3s, box-shadow 0.3s;
  }
  .card:hover {
    height: 410px;
    box-shadow: 20px 20px 40px 0px rgba(0,0,0,0.5);
  }
</style>