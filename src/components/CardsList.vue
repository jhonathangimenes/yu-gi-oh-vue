<template>
    <div>
        <slot>
            {{ cards }} a
        </slot>
    </div>
</template>
<script>
export default {
    props: {
        cards: Array
    }
}
</script>

