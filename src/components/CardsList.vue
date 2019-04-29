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
                <ul class="list-group">
                    <li class="list-group-item" v-for="cards in decks[0].cards" :key="cards.id">{{ cards.name }}</li>
                </ul>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            decks:[
                {id: 1, name: 'deck01', cards:[
                    {id: 1, name: 'Sacred Serpents Wake', img: '5318639.png'},
                    {id: 2, name: 'Sacred Serpents Wake', img: '5318639.png'},
                    {id: 3, name: 'Sacred Serpents Wake', img: '5318639.png'},
                    {id: 4, name: 'Sacred Serpents Wake', img: '5318639.png'},
                    {id: 5, name: 'Sacred Serpents Wake', img: '5318639.png'}
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

