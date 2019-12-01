<template>

    <v-app>
        <v-card v-on:click="selectPlayer($event)" class="" v-for="player in players" v-bind:key="player.name" v-bind:player="player.name">
            <v-card-title>{{player.name}}</v-card-title>
            <v-card-text>{{player.tagline}}</v-card-text>
            <v-card-text>{{player.points}}</v-card-text>
        </v-card>
    </v-app>
</template>

<script>
    export default {
        name: 'PlayerCard',
        data () {
            return {
                players: [{name: 'guy1',tagline: `im a guy`,points: 0},{name: 'girl2',tagline: `girrrrl what?`,points: 0},{name: 'thing3',tagline: `who am i`,points: 0}],
                selectedPlayers: []
            }
        },
        components: {
        },
        mounted: function() {
            this.getPlayersFromDB();
        },
        methods: {
            getPlayersFromDB: function() {
                //call DB
                
                //then set db results as the player variable as array of objects
                //this.$set(this.players,'name', 'roger');
            },
            selectPlayer: function(event) {
                const playerElement = event.target.parentElement;
                if (!playerElement.classList.contains('selected')) {
                    playerElement.classList.add('selected');
                    this.selectedPlayers.push(playerElement.getAttribute('player'))
                }else {
                    playerElement.classList.remove('selected');
                    this.selectedPlayers = this.selectedPlayers.filter(player => player != playerElement.getAttribute('player'))
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