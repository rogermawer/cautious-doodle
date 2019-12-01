<template>
  <div id="main">
      <h1>The game goes here</h1>
      <p>We can test the games functionality here</p>
      <p>Ideally once a successful login is recorded this page will become visible. But for now, its live for dev.</p>
      <p>Selected Players: {{selectedPlayers}}</p>
      <PlayerCard @selectedPlayers="showSelectedPlayers"></PlayerCard>
  </div>
</template>

<script>
import PlayerCard from '@/components/PlayerCard.vue';
    
export default {
  name: 'Playground',
  components: {
    PlayerCard
  },
    data () {
        return {
            selectedPlayers: []
        }
    },
    methods: {
        showSelectedPlayers: function(variable) {
            //assign variable (selectedPlayers array from PlayerCard component)
            this.selectedPlayers = variable; 
        }
    }
}
</script>

<style>
    
</style>

