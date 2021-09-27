<template>
  <div>
    <Navbar />
    <Header />
    <!-- First jumbotron -->
    <div class="container-fluid py-5">
      <p class="col-md-12 fs-4">
        Банальные, но неопровержимые выводы, а также акционеры крупнейших
        компаний, которые представляют собой яркий пример
        континентально-европейского типа политической культуры, будут в равной
        степени предоставлены сами себе. Для современного мира постоянный
        количественный рост и сфера нашей активности напрямую зависит от
        кластеризации усилий.
      </p>
    </div>
    <InSide />
    <!-- Second jumbotron -->
    <div class="container-fluid py-5">
      <p class="col-md-12 fs-4">
        Банальные, но неопровержимые выводы, а также акционеры крупнейших
        компаний, которые представляют собой яркий пример
        континентально-европейского типа политической культуры, будут в равной
        степени предоставлены сами себе. Для современного мира постоянный
        количественный рост и сфера нашей активности напрямую зависит от
        кластеризации усилий.
      </p>
    </div>
    <Card/>
    <Features/>
    <Form/>
    <Reviews/>
    <Footer/>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import Header from "@/components/Header.vue";
import InSide from "@/components/InSide.vue";
import Card from "@/components/Card.vue";
import Features from "@/components/Features.vue";
import Form from "@/components/Form.vue"
import Reviews from "@/components/Reviews.vue"
import Footer from "@/components/Footer.vue"

export default {
  name: "App",
  components: {
    Navbar,
    Header,
    InSide,
    Card,
    Features,
    Form,
    Reviews,
    Footer
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
