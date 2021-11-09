<template>
  <div class="item" :class="item.house">
      <p class="director" v-if="item.director">Diretor</p>
      <img :src="item.image" :alt="item.name">
      <h2>{{item.name}}</h2>
      <p> <span>Casa:</span> {{item.house }} </p>
      <p> <span> Patrono: </span> {{item.patronus || "indefinido"}}</p>
      <p> <span> Ator: </span> {{item.actor}}</p>
  </div>
</template>

<script>
export default {
    name: "item",
    props: {
        item: {}
    }
}
</script>

<style lang="less" scoped>
    .item {
        &.Gryffindor {
            background: @red;
        }
        &.Slytherin {
            background: @green;
        }
        &.Hufflepuff {
            background: @yellow;
        }
        &.Ravenclaw {
            background: @blue;
        }
        &.Nenhuma {
            background: @brown;
        }
        width: 240px;
        height: 370px;
        margin: 10px;
        border-radius: 8px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;
        color: white;
        position: relative;

        .director {
            position: absolute;
            right: 5px;
            background: @yellow;
            padding: 5px;
            border-radius: 5px;
            color: black;
            font-weight: 600;
        }


        span {
            font-weight: 600;
           
        }

        h2 {
            margin: 0;
            font-size: 20px;
        }

        p {
            margin: 10px;
            
        }

        img {
            border-radius: 8px 8px 0 0;
            width: 240px;
            height: 200px;
            object-fit: cover;
            object-position: center -10px;

        }
    }
</style>