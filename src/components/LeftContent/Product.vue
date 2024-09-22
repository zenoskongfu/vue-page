<script setup lang="ts">
  import { ref } from 'vue';

  const props = defineProps<{
    data: {
      checked: boolean,
      img: string,
      title: string,
      color: string
    }
  }>();

  const colorOptions = [
    { label: 'black', value: 'black' },
    { label: 'red', value: 'red' },
    { label: 'white', value: 'white' },
  ]

  const colorItems = ['black', 'red', 'white']
  const checked = ref(false);
</script>

<template>
  <div class="product-container">
    <span class="product-checkbox">
      <el-checkbox v-model="checked"
                   size="large" />

    </span>
    <!-- <input type="checkbox"
           :checked="data.checked" /> -->
    <Image :src="data.img" />
    <div class="product-description">
      <div class="product-title">{{ data.title }}</div>
      <el-dropdown trigger="click">
        <span class="el-dropdown-link">
          Color: {{ data.color }}
          <el-icon class="el-icon--right">
            <arrow-right />
          </el-icon>
        </span>
        <template #dropdown>
          <el-dropdown-menu>
            <el-dropdown-item v-for="color in colorItems">{{ color }}</el-dropdown-item>
          </el-dropdown-menu>
        </template>
      </el-dropdown>
      <!-- <div class="product-color">Color: {{ data.color }}</div> -->
    </div>
  </div>
</template>

<style scoped lang="scss">
  .product-container {
    display: flex;
    --size: 100px;

    .product-checkbox {
      display: flex;
      align-items: center;

      :deep(.el-checkbox) {
        .el-checkbox__input .el-checkbox__inner {
          border: 1px solid #DCDFE5;
          border-radius: 50%;
        }

        .el-checkbox__input.is-checked .el-checkbox__inner {
          background-color: tomato;
        }

      }


    }

    image {
      display: inline-block;
      width: var(--size);
      height: var(--size);
      background-color: antiquewhite;
      border-radius: 4px;
      flex-shrink: 0;
      margin-left: 1em;
    }

    .product-description {
      padding-left: 1em;
      margin-top: 0.2em;

      .product-title {
        font-weight: 700;
        width: 210px;


        overflow: hidden;
        display: -webkit-box;
        text-overflow: ellipsis;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical
      }

      .el-dropdown {
        cursor: pointer;
        font-size: 12px;
        margin-top: 0.5em;
        color: gray;

        .el-dropdown-link {
          display: flex;
          align-items: center;
        }
      }




    }
  }
</style>