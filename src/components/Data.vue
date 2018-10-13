<template>
  <div class="col-md-12">
    Type: {{type}}
  </div>
</template>

<script>
  export default {
    data() {
      return {
        type: this.$route.params.type
      }
    },
    methods: {
      change() {
        this.type = this.$route.params.type
      }
    },
    watch: {
      '$route': 'change'
    }
  }
</script>
