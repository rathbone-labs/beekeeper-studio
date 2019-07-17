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
        tables: [
          { name: "users", columns: [{name: "first_name", dataType:"STRING"}]},
          {name: "items", columns: [{name: "wizzbang", dataType:"INT(18)"}]}
        ]
      }
    }
  }

</script>
