<template>
    <div>
        <slot>
            {{ cards }}
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

