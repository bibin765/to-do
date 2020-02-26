<template>
  <div id="to-do-list">
    <table>
      <thead>
        <!-- <tr>
          <th>Status</th>
          <th>Item</th>
        </tr>  -->
      </thead>  

      <tbody>
        
        <tr v-for="listitem in list" :key="listitem.id">
          <td>{{listitem.status}}</td>
          <td>{{listitem.item}}</td>

        </tr>  
      </tbody> 
    </table>  
  </div>
</template>

<script>
  export default {
    name: 'to-do-list',
    props: {
      list:Array,
    }
  }
</script>

<style scoped>


</style>