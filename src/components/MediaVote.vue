<script>
    export default{
        name: 'MediaVote',
        props: ["vote"],
        methods: {
            getStars(){               
                const halfVote= this.vote/ 2;
                let numberStars = Math.ceil(halfVote.toFixed(1));
                return numberStars;
            }
        },
    }
</script>

<template>
    <div class="vote">
        <i v-for="c in this.getStars()" class="fa-solid fa-star gold"></i>
        <i v-if="this.getStars() < 5" v-for="n in 5 - this.getStars()" class="fa-solid fa-star goldgrey"></i>
    </div>
</template>

<style scoped lang="scss">
    .gold{
        color: gold;
    }
    .goldgrey{
        color: rgb(146, 128, 81);
    }

</style>