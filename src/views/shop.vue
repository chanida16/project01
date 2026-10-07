<template>
  <div class="container my-5">

    <!-- หัวข้อ -->
    <h2 class="text-center mb-4">
      แสดงข้อมูลสินค้า
    </h2>

    <!-- ปุ่มอัปเดต -->
    <div class="text-center mb-3">
      <button class="btn btn-primary" @click="fetchProducts">
        🔄 อัปเดต
      </button>
    </div>

    <!-- ตารางสินค้า -->
    <table class="table table-bordered table-striped text-center">

      <!-- หัวตาราง -->
      <thead class="table-dark">
        <tr>
          <th>รหัสสินค้า</th>
          <th>รูปภาพ</th>
          <th>ชื่อสินค้า</th>
          <th>จำนวน</th>
          <th>ราคา</th>
        </tr>
      </thead>

      <!-- ข้อมูลสินค้า -->
      <tbody>

        <tr
          v-for="(product, index) in products"
          :key="product.id"
        >

          <!-- รหัสสินค้า -->
          <td>
            {{ index + 1 }}
          </td>

          <!-- รูปภาพ -->
          <td>
            <img
              :src="product.images[0]"
              :alt="product.title"
              width="50"
              height="50"
              style="object-fit: contain;"
            >
          </td>

          <!-- ชื่อสินค้า -->
          <td class="text-start product-name">
            {{ product.title }}
          </td>

          <!-- จำนวน -->
          <td>
            {{ product.stock }}
          </td>

          <!-- ราคา -->
          <td class="text-danger">
            ${{ product.price }}
          </td>

        </tr>

      </tbody>

    </table>

  </div>
</template>


<script>
import { ref, onMounted } from "vue";

export default {

  setup() {

    // เก็บข้อมูลสินค้า
    const products = ref([]);

    // ดึงข้อมูลสินค้าจาก API
    const fetchProducts = async () => {

      try {

        const response = await fetch(
          "https://dummyjson.com/products"
        );

        const data = await response.json();

        products.value = data.products;

      } catch (error) {

        console.error(
          "Error fetching products:",
          error
        );

      }

    };

    // เรียก API ตอนเปิดหน้า
    onMounted(fetchProducts);

    return {
      products,
      fetchProducts
    };

  },

};
</script>


<style scoped>

/* ชื่อสินค้า */
.product-name {
  color: #548c7d;
}

/* รูปสินค้า */
img {
  object-fit: contain;
}

/* ตาราง */
table {
  vertical-align: middle;
}

/* หัวตาราง */
thead th {
  text-align: center;
}

/* ราคา */
.text-danger {
  font-weight: bold;
}

</style>