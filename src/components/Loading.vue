<template>
  <div class="loading"></div>
</template>

<script>
export default {
  name: "Loading",
};
</script>

<style lang="less" scoped>
.loading {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  border: 5px solid @yellow; 
  border-bottom-color: @red;
  border-right-color: @blue;
  border-left-color: @green;
  animation: spin 1s linear infinite;
  margin: auto;

  @media @smartphones {
      margin-top: 250px
  }
}

@keyframes spin {
    to {
        transform: rotate(360deg);
    }
}
</style>
