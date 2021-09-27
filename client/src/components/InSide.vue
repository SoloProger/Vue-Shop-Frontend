<template>
  <div id="myCarousel" class="carousel slide" data-bs-ride="carousel">
    <h1 id="inSide">Внутренняя отделка</h1>
    <div class="carousel-indicators">
      <button
        type="button"
        data-bs-target="#myCarousel"
        data-bs-slide-to="0"
        class="active"
        aria-label="Slide 1"
        aria-current="true"
      ></button>
      <button
        type="button"
        data-bs-target="#myCarousel"
        data-bs-slide-to="1"
        aria-label="Slide 2"
        class=""
      ></button>
      <button
        type="button"
        data-bs-target="#myCarousel"
        data-bs-slide-to="2"
        aria-label="Slide 3"
        class=""
      ></button>
    </div>
    <div class="carousel-inner">
      <div class="carousel-item carousel-item-next carousel-item-start">
        <img src="../assets/FirstCarouselAsset.jpg" alt="Carousel_Asset" />

        <div class="container">
          <div class="carousel-caption text-start">
            <h1>Косметический ремонт</h1>
            <p></p>
            <p>
              <a class="btn btn-lg btn-warning" href="#form">Оставьте заявку!</a>
            </p>
          </div>
        </div>
      </div>
      <div class="carousel-item">
        <img src="../assets/SecondCarouselAsset.jpg" alt="Carousel_Asset" />

        <div class="container">
          <div class="carousel-caption middle">
            <h1>Капитальный ремонт</h1>
            <p></p>
            <p>
              <a class="btn btn-lg btn-warning" href="#form">Оставьте заявку!</a>
            </p>
          </div>
        </div>
      </div>
      <div class="carousel-item active carousel-item-start">
        <img src="../assets/ThirdCarouselAsset.jpg" alt="Carousel_Asset" />

        <div class="container">
          <div class="carousel-caption text-end">
            <h1>Евроремонт</h1>
            <p></p>
            <p>
              <a class="btn btn-lg btn-warning" href="#form">Оставьте заявку!</a>
            </p>
          </div>
        </div>
      </div>
    </div>
    <button
      class="carousel-control-prev"
      type="button"
      data-bs-target="#myCarousel"
      data-bs-slide="prev"
    >
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Previous</span>
    </button>
    <button
      class="carousel-control-next"
      type="button"
      data-bs-target="#myCarousel"
      data-bs-slide="next"
    >
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Next</span>
    </button>
  </div>
</template>

<style scoped>
#inSide{
  margin-bottom: 2rem;
}

.text-start {
  color: #ffe48a;
  font-size: 20px;
}
.middle {
  color: #ffe48a;
  font-size: 20px;
}
.text-end {
  color: #ffe48a;
  font-size: 20px;
}
</style>