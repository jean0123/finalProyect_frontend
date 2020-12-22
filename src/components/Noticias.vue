<template>
  <div class="row mt-md-5 mt-sm-5 mt-xs-5" style="background: #f3f3ee">
    <div
      class="col-lg-6 col-xs-12 border"
      v-for="(item, index) of noticias"
      :key="index"
    >
      <div class="d-flex justify-content-center align-itemscenter">
        <div class="w-60 p-3">
          <img
            class="w-100"
            :src="item.urlToImage"
            alt="Imagen de la noticia"
            style="
              height: 100%;
              object-fit: cover;
              object-position: center center;
            "
          />
        </div>
        <div class="w-40 p-2" style="text-align: justify">
          <h4>{{ item.title }}</h4>
          <p>{{ item.description }}</p>
        </div>
      </div>
      <div class="d-flex container-fluid justify-content-end pb-2 mt-n2">
        <a
          :href="item.url"
          type="button"
          class="btn btn-outlineinfo"
          target="_blank"
          >Más información >></a
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Noticias",
  data() {
    return {
      noticias: null,
    };
  },
  mounted() {
    this.axios
      .get(
        "http://newsapi.org/v2/top-headlines?country=co&category=technology&apiKey=13af64b658f94c4fab209de109ba5480"
      )
      .then((response) => {
        this.noticias = response.data.articles.slice(0, 4);
      });
  },
};
</script>

<style>
</style>