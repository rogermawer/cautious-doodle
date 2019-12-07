<template>

    <div>
        <v-card v-on:click="selectPlayer($event)" class="" v-for="player in players" v-bind:key="player.id" v-bind:player_id="player.id">
            <v-card-title prepend-icon="mdi-account">{{player.name}} | {{player.points}}</v-card-title>
            <v-card-text>"{{player.tagline}}"</v-card-text>
            
  
         
        </v-card>
    </div>
</template>

<script>
    export default {
        name: 'PlayerCard',
        props: {
          players: Array  
        },
        data () {
            return {
                selectedPlayers: []
            }
        },
        components: {
        },
        mounted: function() {
           
        },
        methods: {
            selectPlayer: function(event) {
                const playerElement = event.target.parentElement;
                if (!playerElement.classList.contains('selected')) {
                    playerElement.classList.add('selected');
                    var theSelectedPlayer = this.players.filter(player => player.id == playerElement.getAttribute('player_id'))
                    this.selectedPlayers.push(theSelectedPlayer[0])
                }else {
                    playerElement.classList.remove('selected');
                    this.selectedPlayers = this.selectedPlayers.filter(player => player.id != playerElement.getAttribute('player_id'))
                }
                this.$emit('selectedPlayers', this.selectedPlayers) // send to other components
            }
        }
    }
</script>

<style>
    .selected {
        background-color: rgba(0, 0, 0, 0.87)!important;
        color: white!important
    }

</style>