<template>
    <div>
        <div class="row">
            <div class="col-md-4">
                <div class="row">
                    <div class="col-6">
                        <div class="float-right">
                            <img src=".././assets/background-card.png" class="img-thumbnail border-0 p-0" alt="Imagem responsiva">
                        </div>
                    </div>
                    <div class="col-6">
                        <div class="float-right">
                            <img src=".././assets/background-card.png" class="img-thumbnail border-0 p-0" alt="Imagem responsiva">
                        </div>
                    </div>
                    <div class="col-6">
                        <div class="float-right">
                            <img src=".././assets/background-card.png" class="img-thumbnail border-0 p-0" alt="Imagem responsiva">
                        </div>
                    </div>
                    <div class="col-6">
                        <div class="float-right">
                            <img src=".././assets/background-card.png" class="img-thumbnail border-0 p-0" alt="Imagem responsiva">
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-md-8">
                <DeckItem :deck="decks[0]">
                    <ul class="list-group" slot-scope="myCards">
                        <li class="list-group-item" v-for="cards in myCards" :key="cards.id">{{ cards.name }}</li>
                    </ul>
                </DeckItem>
            </div>
            <DeckItem :deck="decks[0]"/>
        </div>
    </div>
</template>
<script>
import DeckItem from './DeckItem.vue'

export default {
    components: {
        DeckItem,
    },
    data() {
        return {
            decks:[
                {id: 1, name: 'Deck 01', cards:[
                    {id: 1, name: 'Mystical Space Typhoon', img: '5318639.png'},
                    {id: 2, name: 'Pot of Dichotomy', img: '98672567.png'},
                    {id: 3, name: 'Mystacal Knight of Jackal', img: '98745000.png'},
                    {id: 4, name: 'Sacred Serpents Wake', img: '98850929.png'},
                    {id: 6, name: 'Key Mouse', img: '135598.png'},
                    {id: 7, name: 'Mischielf of the Gnomes', img: '164710.png'},
                    {id: 8, name: 'Vylon Hept', img: '168917.png'},
                    {id: 9, name: 'A lengedary Ocena', img: '295517.png'},
                    {id: 10, name: 'Amplifier', img: '303660.png'},
                    {id: 11, name: 'Bahamut Shark', img: '440556.png'},
                    {id: 12, name: 'Frightfur Tiger', img: '464362.png'},
                    {id: 13, name: 'Driving Snow', img: '473469.png'},
                    {id: 14, name: 'Water Spirit', img: '487395.png'},
                    {id: 15, name: 'Superheavy Samurai Warlord Susanowo', img: '494922.png'}
                ]} 
            ]
        }
    }
}
</script>

<style>
    .list-group-item {
        background-color: #57606f!important;
        color: #ffff;
        border-color: #ced6e0;
    }
</style>

