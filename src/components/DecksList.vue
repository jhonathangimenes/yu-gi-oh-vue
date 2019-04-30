<template>
    <div>
        <div class="row">
            <div class="col-md-4">
                <div class="row">
                    <div class="col-6" v-for="deck in decks" :key="deck.id">
                        <div @click.prevent="chosenDeck = deck">
                            <DeckItem :deck="deck">
                                <template slot-scope="myCards">
                                    <template v-for="cards in myCards">
                                        <img :src="require('../assets/cards/'+cards.img)"
                                        :key="cards.id"
                                        v-if="cards.name == card"
                                        class="img-thumbnail border-0 p-0"
                                        alt="Imagem responsiva">            
                                    </template>
                                    
                                </template>
                            </DeckItem>
                            <img v-show="card == undefined" src=".././assets/background-card.png" class="img-thumbnail border-0 p-0" alt="Imagem responsiva">
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-md-8" v-if="chosenDeck != {}">
                <DeckItem :deck="chosenDeck"/>
            </div>
        </div>
    </div>
</template>
<script>
import DeckItem from './DeckItem.vue'
import { EventBus } from './../event-bus.js';

export default {
    components: {
        DeckItem,
    },
    data() {
        return {
            card: undefined,
            chosenDeck: {},
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
                ]},
                {id: 2, name: 'Deck 02', cards:[
                    {id: 1, name: 'Goblin Elite Attack Force', img: '85306040.png'},
                    {id: 2, name: 'Ray & Temperature', img: '85309439.png'},
                    {id: 3, name: 'Dododo Driver', img: '85310252.png'},
                    {id: 4, name: 'Dark Lucius LV4', img: '85313220.png'},
                    {id: 6, name: 'Spike Seadra', img: '85326399.png'},
                    {id: 7, name: 'Paladin of Photon Dragon', img: '85346853.png'},
                    {id: 8, name: 'Attention!', img: '85352446.png'},
                    {id: 9, name: 'Freezing Beast', img: '85359414.png'},
                    {id: 10, name: 'Super Quantum Green Layer', img: '85374678.png'},
                    {id: 11, name: 'Harvest Angel of Wisdom', img: '85399281.png'},
                    {id: 12, name: 'Evil Thorn', img: '85431040.png'},
                    {id: 13, name: 'Zerozerock', img: '85446833.png'},
                    {id: 14, name: 'Sentinel of the Seas', img: '85448931.png'},
                    {id: 15, name: 'Ghostrick Ghoul', img: '85463083.png'}
                ]}  
            ]
        }
    },
    created() {
        EventBus.$on('chosenCard', (card) => {
            this.card = card
        })
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

