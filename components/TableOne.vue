<template>
  <div>
    <table
      cellspacing="0"
      summary="This is an Example of Dynamic Table"
      class="table"
    >
      <caption>
        Example of Dynamic Table
      </caption>
      <tr>
        <td>one</td>
        <td>one</td>
        <td>one</td>
      </tr>
      <tr>
        <td>two</td>
        <td>two</td>
        <td>two</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  mounted() {
    window.jQuery('icon icon-link').text('test')
  },
}
</script>

<style lang="scss" scoped></style>
