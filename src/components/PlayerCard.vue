<template>

    <div id="player-list">
        <v-card class="player-card d-flex" v-on:click="selectPlayer($event)" v-for="player in players" v-bind:key="player.id" v-bind:player_id="player.id">
            
                <v-icon class="pr-4" large>mdi-account</v-icon>
                <div>
                  <v-card-title class="pa-2" prepend-icon="mdi-account">{{player.name}} | {{player.points}}</v-card-title>
                  <v-card-text class="pa-2">"{{player.tagline}}"</v-card-text>
                </div>
    
            
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
                const playerElement = event.target;
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
    /* all children of parent */
    .player-card * {
        pointer-events: none
    }
    .selected {
        background-color: rgba(173,216,230 ,1)!important;
    }

</style>