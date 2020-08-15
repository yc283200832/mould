<template>
  <div class="dashboard-container">
    <span>{{roles}}</span>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
export default {
  name: 'Dashboard',
  data() {
    return{
      num: 0
    }
  },
  computed: {
    ...mapGetters([
      'roles'
    ])
  },
  mounted() {
    
  }
}
</script>
