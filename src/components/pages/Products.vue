<template>
    <div>
        123
    </div>
</template>

<script>
export default {
  name: 'Products',
  data () {
    return {
      products:[]
    }
  },
  methods: {
    getProducts() {
      const api = `${process.env.APIPATH}/api/${process.env.CUSTOMPATH}/products`
      const vm = this
      this.$http.get(api).then((response) => {
        if(response.data.success){
          vm.products = response.data.products;
        }
      })
    }
  },
  created(){
      this.getProducts();
  }
}
</script>