<script setup>
    function log(e){
        console.log('me clikeaste')
    }

    const props = defineProps({
        name: {
            default: "MissingNo",
            type: String
        },
        id: {
            default: 0,
            type: Number,
        },
        image: {
            default: 'https://res.cloudinary.com/dxagsphno/image/upload/v1676501971/Pokemon-Types/defaultPokeBall_gqzh1q.png',
            type: String
        },
        types: {
            default: ['none'],
            type: Array
        }
    })
    const urlTypes = {
        'bug' : 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048227/Pokemon-Types/bug_xnoceu.png',
        'dark': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048228/Pokemon-Types/dark_g8pr1m.png',
        'dragon': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048228/Pokemon-Types/dragon_dkn0nq.png',
        'electric': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048227/Pokemon-Types/electric_izhtnf.png',
        'fairy': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048228/Pokemon-Types/fairy_s0umzi.png',
        'fighting': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048228/Pokemon-Types/fighting_crpadb.png',
        'fire': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048228/Pokemon-Types/fire_unxz8o.png',
        'flying': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048228/Pokemon-Types/flying_gl4xv5.png',
        'ghost': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048228/Pokemon-Types/ghost_acmbqh.png',
        'grass': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048228/Pokemon-Types/grass_of6ivc.png',
        'ground': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048227/Pokemon-Types/ground_tbmlgh.png',
        'ice': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048227/Pokemon-Types/ice_jr3qsp.png',
        'normal': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048227/Pokemon-Types/normal_o15fbf.png',
        'poison': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048227/Pokemon-Types/poison_ecusun.png',
        'psychic': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048227/Pokemon-Types/psychic_cwlpc5.png',
        'rock': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048227/Pokemon-Types/rock_byynbp.png',
        'steel': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048227/Pokemon-Types/steel_is6kay.png',
        'water': 'https://res.cloudinary.com/dxagsphno/image/upload/v1671048227/Pokemon-Types/water_vw247n.png',    
        'none': 'https://res.cloudinary.com/dxagsphno/image/upload/v1676517748/Pokemon-Types/mistery_type.png'
    };
    const {name, id, image, types} = props;
</script>
<template>
    <div class="Card" @click="log">
        <img :src="image" class="Card-image" :alt="name" :title="name">
        <div class="Card-data">
            <div>
                <span class="Card-dex">N??{{ id }}</span>
                <h3 class="Card-name">{{ name }}</h3>
            </div>
            <div class="Card-types">
                <template v-for="url in types">
                    <img :src="urlTypes[url]" :alt="url" class="Card-type" :title="url.toUpperCase()">
                </template>
            </div>
        </div>
    </div>
</template>
<style scoped lang="scss"> 
    .Card{
        background-color: var(--grey-color);
        color: var(--grey-card-font);
        padding: .9375rem .625rem;
        display: flex;
        justify-content: flex-start;
        align-items: center;
        box-shadow: 1px 1px 15px 1px #8585852d;
        cursor: pointer;
        transition: box-shadow 0.6s cubic-bezier(0.075, 0.82, 0.165, 1);
        &-data{
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            flex-direction: column;
            height: 100%;
        }
        &-image{
            max-width: 150px;
            height: 100%;
            filter: grayscale(100%);
            transition: filter 0.8s cubic-bezier(0.075, 0.82, 0.165, 1);
            object-fit: contain;
        }
        &-dex{
            font-weight: lighter;
            font-size: 1em;
        }
        &-name{
            margin-top: .3125rem;
            font-weight: bold;
            font-size: 1.6em;
            text-transform: uppercase;
        }
        &-types{
            display: flex;
            justify-content: center;
            align-items: center;
            gap: calc(var(--gap) - .625rem);
        }
        &-type{
            max-width: 2.8125rem;
        }
        &:hover{
            box-shadow: 3px 3px 15px 1px #85858557;
            .Card-image{
            filter: unset;
            }
        }
    }
</style>