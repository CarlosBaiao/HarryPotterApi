<template>
  <div class="category-menu">
    <ul>
      <li
        v-for="category in categoriesList"
        :key="category.id"
        :id="category.id"
        @click="onCategoryClick(category.id)"
        :class="{'active' : isActive(category.id)}"
      >
        <Harry />
        <p>{{ category.label }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
import Harry from "../assets/images/harry.svg";

export default {
  name: "CategoryMenu",
  components: {
    Harry,
  },
  data() {
    return {
      categoriesList: [
        { label: "Grifinória", id: "grifinoria" },
        { label: "Sonserina", id: "sonserina" },
        { label: "Lufa-lufa", id: "lufalufa" },
        { label: "Corvinal", id: "corvinal" },
        { label: "Integrantes", id: "integrantes" },
      ],
      selectedCategory: "",
    };
  },
  mounted() {
    this.onCategoryClick('grifinoria')
  },
  methods: {
    onCategoryClick(id) {
      this.selectedCategory = id;
      this.$store.dispatch('changeCategory', id)
    },
    isActive(id) {
        return this.selectedCategory === id;
    }
  },
};
</script>

<style scoped lang="less">
.category-menu {
 
  height: 100%;
  background: rgba(0, 0, 0, 0.8);

  display: flex;
  align-items: center;

  ul {
    width: 100%;
    list-style: none;
    padding: 0;

    li {
      width: 130px;
      height: 100px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      margin:  0;

      &.active {
          background: black;
          border-radius: 8px;
      }

      p {
        margin: 7px 0 0 0;
        font-weight: 600;
        font-size: 14px;
      }
    }

    #grifinoria {
      p {
        color: @red;
      }
      svg {
        path {
          fill: @red;
        }
      }
    }
    #sonserina {
      p {
        color: @green;
      }
      svg {
        path {
          fill: @green;
        }
      }
    }
    #lufalufa {
      p {
        color: @yellow;
      }
      svg {
        path {
          fill: @yellow;
        }
      }
    }
    #corvinal {
      p {
        color: @blue;
      }
      svg {
        path {
          fill: @blue;
        }
      }
    }
    #integrantes {
      p {
        color: @brown;
      }
      svg {
        path {
          fill: @brown;
        }
      }
    }
  }

  @media @smartphones {
    width: 100%;
    height: fit-content;

    ul {
      display: flex;
      overflow: scroll;
      margin: 20px;

      li {
        min-width: 90px;
        margin: 0 10px;
    }
    }

  } 
    
  
}
</style>
