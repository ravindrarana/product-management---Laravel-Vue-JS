<template>
  <div>
    <h3 class="text-center">Edit Product</h3>
    <div class="row justify-content-center">
      <div class="col-md-8">
        <form @submit.prevent="updateProduct">
          <div class="form-group">
            <label>Title</label>
            <input type="text" class="form-control" v-model="product.title" />
          </div>
          <div class="form-group">
            <label>Price</label>
            <input type="text" class="form-control" v-model="product.price" />
          </div>
          <div class="form-group">
            <label>Description</label>
            <input type="text" class="form-control" v-model="product.description" />
          </div>
          <button type="submit" class="btn btn-primary">Update</button>
        </form>
      </div>
    </div>
  </div>
</template>
 
<script>
export default {
  data() {
    return {
      product: {},
    };
  },
  created() {
    this.axios
      .get(`http://localhost:8000/api/products/${this.$route.params.id}`)
      .then((res) => {
        this.product = res.data;
      });
  },
  methods: {
    updateProduct() {
      this.axios
        .patch(
          `http://localhost:8000/api/products/${this.$route.params.id}`,
          this.product
        )
        .then((res) => {
          this.$router.push({ name: "home" });
        });
    },
  },
};
</script>