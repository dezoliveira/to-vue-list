<template>
  <div class="container">
    <h1 class="text-center m-4">To Vue List</h1>

    <div class="d-flex m-4">
      <input type="text" placeholder="Enter Task" class="form-control rounded-0">
      <button class="btn btn-success rounded-0">Pesquisar</button>
    </div>

    <!-- Table Bootstrap -->
    <table class="table">
    <thead>
      <tr>
        <th scope="col">Task</th>
        <th scope="col">Status</th>
        <th scope="col" class="text-center">#</th>
        <th scope="col" class="text-center">#</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Steal banana from the store</td>
        <td>To do</td>
        <td>
          <div class="text-center">
            <span>
              <i class="fa fa-pen"></i>
            </span>
          </div>
        </td>
        <td>
          <div class="text-center">
            <span>
              <i class="fa fa-trash"></i>
            </span>
          </div>
        </td>
      </tr>
    </tbody>
  </table>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
