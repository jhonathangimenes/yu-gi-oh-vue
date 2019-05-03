<template>
    <div>
        <slot>
            <ul class="list-group">
                <li class="list-group-item" @click.prevent="chosenCard(cards.img)">{{ cards.name }}</li>
            </ul>
        </slot>
    </div>
</template>
<script>
import { EventBus } from './../event-bus.js';

export default {
    props: {
        cards: Object
    },
    methods: {
        chosenCard(card) {
            EventBus.$emit('chosenCard', card)
        }
    }
}
</script>
<style>
    li {
        border-radius: 2px!important;
        margin-bottom: 5px!important;
        padding: 2px 2px 2px 5px!important;
        background-color: #0c2461!important;
        color: #f1f2f6; 
        cursor: pointer;
        font-size: 17px;
    }
    li:hover {
        box-shadow: 5px 5px 5px #222f3e;
        border-style: solid;
        border-width: 1px;
        border-color: #ff7f50;
    }
</style>
