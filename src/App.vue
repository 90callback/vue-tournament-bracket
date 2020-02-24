<template>
    <bracket :rounds="rounds">
        <template #player="{ player }">
            {{ player.name }} <span class="points">{{ player.points }}</span>
        </template>
    </bracket>
</template>

<script>
    import Bracket from "./Bracket";

    const rounds = [
        //Quarter
        {
            games: [
                {
                    player1: { id: "1", name: "Team1", winner: true, points: 2 },
                    player2: { id: "2", name: "Team2", winner: false, points: 0 }
                },
                {
                    player1: { id: "3", name: "Competitor 3", winner: false, points: 1 },
                    player2: { id: "4", name: "Competitor 4", winner: true, points: 2 }
                },
                {
                    player1: { id: "5", name: "Competitor 5", winner: true, points: 1  },
                    player2: { id: "6", name: "Competitor 6", winner: false, points: 1 }
                },
                {
                    player1: { id: "7", name: "Competitor 7", winner: false, points: 1 },
                    player2: { id: "8", name: "Competitor 8", winner: true, points: 1 }
                }
            ]
        },
        //Semi
        {
            games: [
                {
                    player1: { id: "1", name: "Competitor 1", winner: false, points: 1 },
                    player2: { id: "4", name: "Competitor 4", winner: true, points: 1 }
                },
                {
                    player1: { id: "5", name: "Competitor 5", winner: false },
                    player2: { id: "8", name: "Competitor 8", winner: true }
                }
            ]
        },
        //Final
        {
            games: [
                {
                    player1: { id: "4", name: "Competitor 4", winner: false },
                    player2: { id: "8", name: "Competitor 8", winner: true }
                }
            ]
        }
    ];

    export default {
        name: "app",
        components: {
            Bracket
        },
        data() {
            return {
                rounds: rounds
            };
        }
    };
</script>

<style scoped>
.points {
  display: inline-block;
  float: right;
  font-weight: bold;
}
</style>