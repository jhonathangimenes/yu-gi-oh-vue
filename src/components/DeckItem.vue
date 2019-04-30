<template>
    <div>
        <CardsList v-for="cards in deck.cards" 
            :cards="cards" 
            :key="cards.id">
            <slot :MyCards="cards"></slot>
        </CardsList>
    </div>
</template>
<script>
import CardsList from './CardsList.vue'

export default {
    components: {
        CardsList
    },
    props: {
        deck: Object
    }
}
</script>

