<template>
  <div id="main">
      <p>This is the users selected game.</p>
      <p>when a player selects a game from "your games" it shows up here</p>
      <p>Selected Players: {{selectedPlayers}}</p>
      <PlayerCard :players="players" @selectedPlayers="showSelectedPlayers"></PlayerCard>
      <AddSub :selectedPlayers="selectedPlayers" @postPoints="updatePlayers"></AddSub>
    </div>
</template>

<script>
import PlayerCard from '@/components/PlayerCard.vue';
import AddSub from '@/components/AddSub.vue';
    
export default {
  name: 'CurrentGame',
  components: {
    PlayerCard,
    AddSub
  },
    data () {
        return {
            //players from DB
            players: [{id: 1, name: 'guy1',tagline: `im a guy`,points: 0},{id: 2, name: 'girl2',tagline: `girrrrl what?`,points: 0},{id: 3, name: 'thing3',tagline: `who am i`,points: 0},{id: 4, name: 'guy1',tagline: `im a guy with the same name, but different`,points: 0}],
            //when you click on someone they show up here
            selectedPlayers: []
        }
    },
    methods: {
        getPlayersFromDB: function() {
            //call DB
                
            //then set db results as the player variable as array of objects
            //this.$set(this.players,'name', 'roger');
        },
        showSelectedPlayers: function(array) {
            this.selectedPlayers = array; 
        },
        updatePlayers: function(selectedPlayersArray){
            var vm = this;
            selectedPlayersArray.forEach(function(e1){
                vm.players.forEach(function(e2){
                    if (e1.id == e2.id) {
                        vm.$set(vm.players[vm.players.indexOf(e2)],'points', e1.points);
                    }
                })
            })
        }
    }
}
</script>

<style>
    
</style>

