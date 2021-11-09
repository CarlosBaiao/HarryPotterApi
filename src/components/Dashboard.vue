<template>
  <div class="dashboard">
      <CategoryMenu/>
      <ItemsList/>
  </div>
</template>

<script>
import CategoryMenu from './CategoryMenu.vue'
import ItemsList from './ItemsList.vue'

export default {
    name: "Dashboard",
    components: {
        CategoryMenu,
        ItemsList
        
    }
}
</script>

<style scoped lang="less">
    .dashboard {
        background: rgba(0,0,0,0.7);
        width: 90%;
        height: 90vh;
        border: 4px solid @yellow;
        border-radius: 8px;
        display: flex;

        @media @smartphones {
            width: 350px;
            height: 100vh;
            overflow: auto;
            display: block;
        }
    }
</style>