<template>
  <div>
    <table cellspacing="0" summary="Example of Complex Table" class="chart">
      <caption>
        Example of Complex Table
      </caption>
      <thead>
        <tr>
          <th id="fam" class="toplevel">Family</th>
          <th id="rmc" class="toplevel" colspan="2">Romance Lang</th>
          <th id="cel" class="toplevel" colspan="2">Celtic</th>
        </tr>
        <tr>
          <th headers="hue">Color</th>
          <th id="es" headers="rmc">Spanish</th>
          <th id="fr" headers="rmc">French</th>
          <th id="ga" headers="cel">Irish</th>
          <th id="cy" headers="cel">Welsh</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th id="green" headers="hue">Green</th>
          <td lang="es" headers="rmc es green">verde</td>
          <td lang="fr" headers="rmc fr green">vert</td>
          <td lang="ga" headers="cel ga green">glas</td>
          <td lang="cy" headers="cel cy green">gwyrdd</td>
        </tr>
      </tbody>
    </table>
    <!-- <div class="table--caption text-center">This is the table Caption</div> -->
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped></style>
