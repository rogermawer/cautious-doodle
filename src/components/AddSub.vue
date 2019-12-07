<template>

    <div>
        <v-btn @click="addPoints" color="primary">+</v-btn>
        <v-btn @click="subPoints" color="error">-</v-btn>
    </div>
</template>

<script>
    export default {
        name: 'AddSub',
        props: {
          selectedPlayers: Array  
        },
        data () {
            return {
                
            }
        },
        components: {
            
        },
        mounted: function() {
            
        },
        methods: {
            addPoints: function(){
                this.selectedPlayers.forEach(function(player){
                    player.points += 1;
                })
                this.$emit('postPoints', this.selectedPlayers)
            },
            subPoints: function(){
                this.selectedPlayers.forEach(function(player){
                    player.points -= 1;
                })
                this.$emit('postPoints', this.selectedPlayers)
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