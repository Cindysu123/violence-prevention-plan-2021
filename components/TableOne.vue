<template>
  <div>
    <table cellspacing="0" summary="Example of Dynamic Table" class="chart">
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
