<template>
    <div v-if="card.withoutCardStyles" class="htmlCard" :class="cardClassList">
        <div v-html="card.content" class="htmlCard__content">
        </div>
    </div>

    <Card v-else class="htmlCard" :class="cardClassList">
        <div class="px-3 py-3">
            <div v-html="card.content" class="htmlCard__content">
            </div>
        </div>
    </Card>
</template>

<script>
    export default {
        props: [
            'card',
        ],
        computed: {
            cardClassList() {
                let classes = '';
                if (this.card.center) {
                    classes += ' flex flex-col justify-center text-center';
                }

                return classes;
            },
        },
    }
</script>

<style>
    .htmlCard__content > p:not(:last-child) {
        margin-bottom: 1em;
    }
</style>
