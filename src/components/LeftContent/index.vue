<script setup lang="ts">
  import Product from './Product.vue';
  import TableCell from './TableCell.vue';

  const productData = {
    img: '',
    checked: true,
    title: 'Use Charger Muscle Massager Powerful Deep Tissue some',
    color: 'black',
  };

  const tableData = [
    {
      productData: productData,
      price: 30,
      quantity: 1,
      total: 30,
    },
    {
      productData: productData,
      price: 30,
      quantity: 1,
      total: 30,
    },
    {
      productData: productData,
      price: 30,
      quantity: 1,
      total: 30,
    },
    {
      productData: productData,
      price: 30,
      quantity: 1,
      total: 30,
    },
  ]

  const columnWidth = 0;


</script>

<template>
  <div class="left-content">
    <el-table :data="tableData"
              style="width: 100%">
      <el-table-column prop="productData"
                       label="Item"
                       width="350">
        <template #default="scope">
          <product :data="scope.row.productData"></product>
        </template>
      </el-table-column>
      <el-table-column prop="price"
                       label="Price"
                       :width="columnWidth"
                       align="center">
        <template #default="scope">
          <table-cell>
            <span>${{ Number(scope.row.price).toFixed(2) }}</span>
          </table-cell>
        </template>
      </el-table-column>
      <el-table-column prop="quantity"
                       label="Quantity"
                       align="center"
                       :width="columnWidth">
        <template #default="scope">
          <table-cell>
            <span>{{ scope.row.quantity }}</span>
          </table-cell>
        </template>
      </el-table-column>
      <el-table-column prop="total"
                       label="Total"
                       align="center"
                       :width="columnWidth">
        <template #default="scope">
          <table-cell>
            <span>${{ Number(scope.row.total).toFixed(2) }}</span>
          </table-cell>
        </template>
      </el-table-column>
      <el-table-column align="right"
                       width="100">
        <template #header>
          <el-icon color="gray"
                   :size="20">
            <Operation />
          </el-icon>
        </template>
        <template #default="scope">
          <el-icon color="gray"
                   :size="20">
            <Close />
          </el-icon>
        </template>
      </el-table-column>


    </el-table>
  </div>

</template>

<style scoped lang="scss">
  .left-content {
    :deep(.el-table__cell) {
      vertical-align: top;
      padding: 20px 0;
    }
  }
</style>
