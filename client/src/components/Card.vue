<template>
  <div class="album py-5 bg-light">
    <h1 id="outSide">Внешняя отделка</h1>
    <div class="container">
      <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 g-3">
        <div class="col">
          <div class="card shadow-sm">
            <img
              src="../assets/FirstOutsideAsset.jpg"
              alt="Outside_Asset"
              class="img-round"
            />

            <div class="card-body">
              <p class="card-text">
                This is a wider card with supporting text below as a natural
                lead-in to additional content. This content is a little bit
                longer.
              </p>
              <button type="button" class="btn btn btn-outline-warning">
                Отправить заявку.
              </button>
            </div>
          </div>
        </div>
        <div class="col">
          <div class="card shadow-sm">
            <img
              src="../assets/SecondOutsideAsset.jpg"
              alt="Outside_Asset"
              class="img-round"
            />

            <div class="card-body">
              <p class="card-text">
                This is a wider card with supporting text below as a natural
                lead-in to additional content. This content is a little bit
                longer.
              </p>
              <button type="button" class="btn btn btn-outline-warning">
                Отправить заявку.
              </button>
            </div>
          </div>
        </div>
        <div class="col">
          <div class="card shadow-sm">
            <img
              src="../assets/ThirdOutsideAsset.jpg"
              alt="Outside_Asset"
              class="img-round"
            />

            <div class="card-body">
              <p class="card-text">
                This is a wider card with supporting text below as a natural
                lead-in to additional content. This content is a little bit
                longer.
              </p>
              <button type="button" class="btn btn btn-outline-warning">
                Отправить заявку.
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<style scoped>
#outSide{
  margin-bottom: 2rem;
}

.card {
  border-radius: 25%;
}
.img-round {
  border-radius: 25%;
}
</style>