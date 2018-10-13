<template>
  <div class="col-md-12">
    {{items}}
  </div>
</template>

<script>
  export default {
    data() {
      return {
        type: this.$route.params.type,
        items: [],
      }
    },
    methods: {
      fetchItems() {
        this.items = [];
        this.type = this.$route.params.type;
        let initial_ids = [1, 4, 7];
        for (let i in initial_ids) {
          let id = initial_ids[i];
          console.log('id', id);
          fetch(
            `https://lotrapi.co/api/v1/${this.type}/${id}`, {
              method: 'GET'
            })
            .then(response => response.json())
            .then(json => this.items.push(json))
        }
      }
    },
    created() {
      this.fetchItems()
    },
    watch: {
      '$route': 'fetchItems'
    }
  }
</script>
