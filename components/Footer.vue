<template>
  <footer>
    <div class="content">
      <article>
        <div class="quick-links">
          <div class="container">
            <div class="links">
              <h3>Quick Links</h3>
              <div class="line"></div>
              <ul>
                <li>
                  <nuxt-link to="/" class="lg-link">Home</nuxt-link>
                </li>
                <li>
                  <nuxt-link to="/product" class="lg-link">Products</nuxt-link>
                </li>
                <li>
                  <nuxt-link to="/order" class="lg-link">Order Now</nuxt-link>
                </li>
                <li>
                  <nuxt-link to="/about" class="lg-link">About Us</nuxt-link>
                </li>
                <li>
                  <nuxt-link to="/contact" class="lg-link"
                    >Contact Us</nuxt-link
                  >
                </li>
              </ul>
            </div>
            <div class="links">
              <h3>Products</h3>
              <div class="line"></div>
              <nuxt-link to="/product">HDPE PIPES</nuxt-link>
              <nuxt-link to="/product">UPVC PIPES</nuxt-link>
              <nuxt-link to="/product">PPR FITTINGS</nuxt-link>
              <nuxt-link to="/product">UPVC FITTINGS</nuxt-link>
              <nuxt-link to="/product">PPR PIPES</nuxt-link>
              <nuxt-link to="/product">Conduits</nuxt-link>
            </div>
            <div class="links">
              <h3>Social Media link</h3>
              <div class="line"></div>
              <a href="">facebook</a>
              <a href="">telegram</a>
              <a href="">mail</a>
              <a href="">google</a>
              <a href="">linkedin</a>
            </div>
          </div>
        </div>
        <p class="text">PROPLAST & copy 2022— all rights reserved</p>
        <p class="credits">
          design by
          <a href="https://versavvymedia.com/" target="_blank"
            ><span>VERSAVVY MEDIA PLC</span></a
          >
        </p>
      </article>
    </div>
  </footer>
</template>

<style></style>
<script>
import Footer from "../components/Footer.vue";
export default {
  components: { Footer },
};
</script>
