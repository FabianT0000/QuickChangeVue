<template>
  <h4 id="titulo1">Lo mas vendido </h4>
  <div class="allcontainer">
    <vue-horizontal responsive>
    <div class="product-container">
      <section class="product-card">
      <div class="product-image">
        <img src="../assets/blusa1.jpeg" class="product-thumb" alt="" />
        <button class="card-btn">agregar</button>
      </div>
      <div class="product-info">
        <h2 class="product-brand">brand</h2>
        <p class="product-short-description">Blusa gris </p>
        <span class="price">$75.000</span>
      </div>
    </section>
    <section class="product-card">
      <div class="product-image">
        <span class="discount-tag">25% off</span>
        <img src="../assets/chaqueta1.jpg" class="product-thumb" alt="" />
        <button class="card-btn">agregar</button>
      </div>
      <div class="product-info">
        <h2 class="product-brand">brand</h2>
        <p class="product-short-description">Chaqueta de piel</p>
        <span class="price">$200.000</span><span class="actual-price">$170.000</span>
      </div>
    </section>
    <section class="product-card">
      <div class="product-image">
     
        <img src="../assets/blusa2.jpg" class="product-thumb" alt="" />
        <button class="card-btn">agregar</button>
      </div>
      <div class="product-info">
        <h2 class="product-brand">brand</h2>
        <p class="product-short-description">Blusa de verano</p>
        <span class="price">$75.000</span>
      </div>
    </section>
    <section class="product-card">
      <div class="product-image">
        <span class="discount-tag">30% off</span>
        <img src="../assets/jean1.jpg" class="product-thumb" alt="" />
        <button class="card-btn">agregar</button>
      </div>
      <div class="product-info">
        <h2 class="product-brand">brand</h2>
        <p class="product-short-description">Jean con destroyer</p>
        <span class="price">$120.000</span><span class="actual-price">$95.000</span>
      </div>
    </section>
    <section class="product-card">
      <div class="product-image">
        <span class="discount-tag">25% off</span>
        <img src="../assets/jean4.jpeg" class="product-thumb" alt="" />
        <button class="card-btn">agregar</button>
      </div>
      <div class="product-info">
        <h2 class="product-brand">brand</h2>
        <p class="product-short-description"></p>
        <span class="price">$95.0000</span><span class="actual-price">$80.000</span>
      </div>
    </section>
    <section class="product-card">
      <div class="product-image">
        
        <img src="../assets/blusa3.jpg" class="product-thumb" alt="" />
        <button class="card-btn">agregar</button>
      </div>
      <div class="product-info">
        <h2 class="product-brand">brand</h2>
        <p class="product-short-description">Blusa</p>
        <span class="price">$70.000</span>
      </div>
    </section>
    </div>
      </vue-horizontal>

  </div>
  
</template>

<script>
import VueHorizontal from "vue-horizontal";
export default {
  components: { VueHorizontal },
  data() {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  margin-left: 3%;
  margin-right: 3%;
  margin-bottom:0;
}
#titulo1{
  width:20%;
  margin-top:25px;
  margin-bottom: 25px;
}

.product-category {
  padding: 0 10vw;
  font-size: 30px;
  font-weight: 500;
  margin-bottom: 40px;
  text-transform: capitalize;
}

.product-container {
  padding: 0 5vw;
  display: flex;
  overflow-x: initial;
  scroll-behavior: smooth;
}

.product-container::-webkit-scrollbar {
  display: none;
}

.product-card {
  flex: 0 0 auto;
  width: 250px;
  height: 450px;
  margin-right: 40px;
}

.product-image {
  position: relative;
  width: 100%;
  height: 350px;
  overflow: hidden;
}

.product-thumb {
  width: 98%;
  height: 95%;
  object-fit: cover;
}

.discount-tag {
  position: absolute;
  background: #fff;
  padding: 5px;
  border-radius: 5px;
  color: #ff7d7d;
  right: 10px;
  top: 10px;
  text-transform: capitalize;
}

.card-btn {
  position: absolute;
  bottom: 50px;
  left: 50%;
  transform: translateX(-50%);
  padding: 10px;
  width: 60%;
  text-transform: capitalize;
  border: none;
  outline: none;
  background: #fff;
  border-radius: 5px;
  transition: 0.5s;
  cursor: pointer;
  opacity: 0;
}

.product-card:hover .card-btn {
  opacity: 1;
}

.card-btn:hover {
  background: #ff7d7d;
  color: #fff;
}

.product-info {
  width: 100%;
  height: 100px;
  padding-top: 10px;
}

.product-brand {
  text-transform: uppercase;
}

.product-short-description {
  width: 100%;
  height: 20px;
  line-height: 20px;
  overflow: hidden;
  opacity: 0.5;
  text-transform: capitalize;
  margin: 5px 0;
}

.price {
  font-weight: 900px;
  font-size: 20px;
}

.actual-price {
  margin-left: 20px;
  opacity: 0.5;
  text-decoration: line-through;
}

.collection-container {
  width: 100%;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 10px;
}

.collection {
  position: relative;
}

.collection img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.collection p {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  color: #fff;
  font-size: 50px;
  text-transform: capitalize;
}

.collection:nth-child(3) {
  grid-column: span 2;
  margin-bottom: 10px;
}
</style>
