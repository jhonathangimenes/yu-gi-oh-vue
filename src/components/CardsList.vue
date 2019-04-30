<template>
    <div>
        <slot>
            <ul class="list-group">
                <li class="list-group-item" @click.prevent="chosenCard(cards.name)">{{ cards.name }}</li>
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

