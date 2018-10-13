<template>
  <div class="col-md-4 my-4">
    <div class="item-card" @click="switchItem">
      <div class="card bg-dark">
        <h4 class="card-title pt-2">{{item.name}}</h4>
        <div class="card-body">
          <div v-for="(value, key, index) in item">
            <div v-if="index < 6 && index > 0">
              <strong class="text-capitalize">{{key}}</strong>: {{value}}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['passedItem', 'type'],
    data() {
      return {
        item: {}
      }
    },
    methods: {
      switchItem() {
        let random_id = Math.floor(Math.random() * 10 ) + 1;
        fetch(`https://lotrapi.co/api/v1/${this.type}/${random_id}`, {
          method: 'GET'
        })
          .then(response => response.json())
          .then(json => this.item = json)
      }
    },
    created() {
      this.item = this.passedItem;
    }
  }
</script>
