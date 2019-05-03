<template>
    <div class="row">
        <div class="col-md-4">
            <div class="row">
                <div class="col-6" v-for="deck in decks" :key="deck.id">
                    <h3>{{ deck.name }}</h3>
                    <div @click.prevent="checkDeck(deck)">
                        <template v-if="card != undefined">
                            <img v-if="findDeck(deck)" :src="require('../assets/cards/'+card)" class="img-thumbnail border-0 p-0" alt="Imagem responsiva">
                            <img v-else src=".././assets/background-card.png" class="img-thumbnail border-0 p-0" alt="Imagem responsiva">
                        </template>
                        <img v-else src=".././assets/background-card.png" class="img-thumbnail border-0 p-0" alt="Imagem responsiva">
                    </div>
                </div>
            </div>
        </div>
        <div class="col-md-8">
            <template v-if="chosenDeck != undefined">
                <h3 class="text-right">{{ chosenDeck.name }}</h3>
                <DeckItem :deck="chosenDeck"/>
            </template>
            <template v-else>
                <div class="text-center">
                    <h1>Escolha um Deck!</h1>
                    <img src=".././assets/yu-gi.png" width="330" height="450" alt="Imagem responsiva">
                </div>
            </template>
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
            chosenDeck: undefined,
            decks:[
                {id: 1, name: 'Player #1', cards:[
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
                {id: 2, name: 'Player #2', cards:[
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
                ]},
                {id: 3, name: 'Player #3', cards:[
                    {id: 1, name: 'Gem-Knight Fusion', img: '1264319.png'},
                    {id: 2, name: 'Kozmo Soartroopers', img: '1274455.png'},
                    {id: 3, name: 'Vylon Treta', img: '1281505.png'},
                    {id: 4, name: 'Prime Material Falcon', img: '1287123.png'},
                    {id: 6, name: 'T.G. Strike', img: '1315120.png'},
                    {id: 7, name: 'Mysterious Guard', img: '1347977.png'},
                    {id: 8, name: 'Valhalla, Hall of the Fallen', img: '1353770.png'},
                    {id: 9, name: 'Ronintoadin', img: '1357146.png'},
                    {id: 10, name: 'Photon Crusher', img: '1362589.png'},
                    {id: 11, name: 'Vampire Koala', img: '1371589.png'},
                    {id: 12, name: 'Shared Ride', img: '1372887.png'},
                    {id: 13, name: 'Hazy Flame Sphynx', img: '1409474.png'},
                    {id: 14, name: 'Super Roboyarou', img: '1412158.png'},
                    {id: 15, name: 'Number 48: Shadow Lich', img: '1426714.png'}
                ]},
                {id: 4, name: 'Player #4', cards:[
                    {id: 1, name: 'Silver Bow and Arrow', img: '1557499.png'},
                    {id: 2, name: 'ABC-Dragon Buster', img: '1561110.png'},
                    {id: 3, name: 'White Ninja', img: '1571945.png'},
                    {id: 4, name: 'Dinomist Stegosaur', img: '1580833.png'},
                    {id: 6, name: 'Dimension Fortress Weapon', img: '1596508.png'},
                    {id: 7, name: 'Dark Requiem Xyz Dragon', img: '1621413.png'},
                    {id: 8, name: 'Grand Horn of Heaven', img: '1637760.png'},
                    {id: 9, name: 'Divine Dragon Knight Felgrand', img: '1639384.png'},
                    {id: 10, name: 'Fusionist', img: '1641882.png'},
                    {id: 11, name: 'Spell Purification', img: '1669772.png'},
                    {id: 12, name: 'Ultimaya Tzolkin', img: '1686814.png'},
                    {id: 13, name: 'The Big March of Animals', img: '1689516.png'},
                    {id: 14, name: 'PSY-Framegear Epsilon', img: '1697104.png'},
                    {id: 15, name: 'Malefic Cyber end Dragon', img: '1710476.png'}
                ]}  
            ]
        }
    },
    created() {
        EventBus.$on('chosenCard', (card) => {
            this.card = card
        })
    },
    methods: {
        checkDeck(deck) {
            this.card = deck.cards[0].img
            this.chosenDeck = deck
        },
        findDeck(deck) {
            return deck.cards.find(obj => obj.img == this.card)
        }
    }
}
</script>
<style>
    .img-thumbnail {
        box-shadow: 5px 5px 5px black!important;
        cursor: pointer;
    }
    h3 {
        color: #f1f2f6!important; 
    }
    h1 {
        color: #f1f2f6!important; 
    }
    .col-6 {
        margin-bottom: 10px!important;
    }
    .img-thumbnail:hover {
        transform: scale(1.02);
    }
</style>


