<template>
  <div class="TabbedView">
    <Sidebar :tables="tables"></Sidebar>
  </div>
</template>


<script>
  import Sidebar from './Sidebar.vue'

  export default {
    components: { Sidebar },
    props: ['connection'],
    data() {
      return {
        tables: [{ name: "users", columns: [{name: "first_name", data_type:"STRING"}]}, {name: "items", columns: [{name: "wizzbang", data_type:"INT(18)"}]}]
      }
    }
  }

</script>
