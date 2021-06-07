<template>
  <v-footer padless class="noprint">
    <v-card
      flat
      tile
      class="text-center"
      style="width: 100%; background: #082b6b"
    >
      <v-card-text
        class="text-center mt-2"
        style="color: #fff; font-size: 10px"
      >
        Disclaimer here Disclaimer here Disclaimer here Latet quod, dat odium
        Aetolius abruptaque longaeque litusque, levior pater omne, potuit. Est
        dona solusque Diam lactantia corpore nulla nec et parens habemus, pictis
        stravit, nactus commissa puniceum. Ferrum animo utrumque iungit, quem
        atque se folio debilitaturum et vestigia, videt bicorni ferro, extremo.
        Pittheam hoc manus dictis desertaque quam, crescentemque mansit
        sustinet.
      </v-card-text>
      <v-card-text class="mb-2" style="margin-top: -10px">
        <div style="font-size: 12px; color: #fff">
          &copy;&nbsp;{{ new Date().getFullYear() }}
          <strong>
            <a
              href="http://icjia.state.il.us"
              class="footer-link"
              target="_blank"
              rel="noreferrer"
              >Illinois Criminal Justice Information Authority</a
            > </strong
          >&nbsp;|&nbsp;
          <strong>
            <a
              href="https://archive.icjia.cloud"
              target="_blank"
              class="footer-link"
              rel="noreferrer"
              >ICJIA Document Archive</a
            ></strong
          >&nbsp;|&nbsp;
          <strong>
            <a
              href="https://icjia.illinois.gov/status"
              target="_blank"
              class="footer-link"
              rel="noreferrer"
              >ICJIA Site status</a
            ></strong
          >
          &nbsp;|&nbsp;
          <strong>
            <a
              href="https://github.com/ICJIA/violence-prevention-plan-2021"
              target="_blank"
              class="footer-link"
              rel="noreferrer"
              >Github</a
            >
          </strong>
        </div>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  data: () => ({
    icons: ['fab fa-facebook', 'fab fa-twitter'],
    loading: true,
    nav: [],
    items: null,
    isLoading: false,
  }),
}
</script>

<style>
.footer-link {
  color: #fff !important;
  text-decoration: none;
}

.footer-link:hover {
  color: #aaa !important;
  text-decoration: underline;
}
</style>
