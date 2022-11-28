<template>
  <div>
    <Nav />
    <section class="page-header">
      <div class="container">
        <div class="page-wrapper">
          <article>
            <h1 class="site-title">Products</h1>
          </article>
        </div>
      </div>
    </section>
    <section class="product-list1 row-max-grid">
      <div class="container">
        <div class="new-product">
          <div class="text-desc">
            <h2>New Products</h2>
            <p>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sunt
              sedn commodi repellat magni dolor. Error corporis perspiciatis qui
              repellat accusantium, officiis in quo consectetur, ipsa
              praesentium non voluptates saepe harum!Lorem ipsum dolor sit, amet
              consectetur adipisicing elit. Sunt sed commodi repellat magni
              dolor. Error corporis perspiciatis qui repellat accusantium,
              officiis in quo consectetur, ipsa praesentium non voluptates saepe
              harum! Lorem ipsum dolor sit, amet consectetur adipisicing elit.
              Sunt sed commodi repellat magni dolor.
            </p>
            <button class="btn btn-secondary row-max-grid">Order Now</button>
          </div>
          <img src="../assets/img/proplast2.jpg" alt="" />
        </div>
        <div class="all-product">
          <div class="single-product"></div>
        </div>
      </div>
    </section>
    <div class="wrapper">
      <section class="module product-list">
        <h3 class="section-title"><b>List of</b><span>Products</span></h3>
      </section>
      <section class="product-all-list">
        <div class="list">
          <div class="container">
            <div class="single-list">
              <img src="../assets/img/HDPEPIPES.png" alt="" />
              <h4>HDPE PIPES</h4>
              <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit.
                Reiciendis fugit aliquid corporis rerum omnis quidem, libero
                ducimus nostrum quos laboriosam laborum vero officia tempora
                sint nesciunt.
              </p>
            </div>
            <div class="single-list">
              <img src="../assets/img/uPVCPIPES.jpg" alt="" />
              <h4>uPVC PIPES</h4>
              <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit.
                Reiciendis fugit aliquid corporis rerum omnis quidem, libero
                ducimus nostrum quos laboriosam laborum vero officia tempora
                sint nesciunt.
              </p>
            </div>
            <div class="single-list">
              <img src="../assets/img/PPRFITTINGS.jpg" alt="" />
              <h4>PPRFITTINGS</h4>
              <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit.
                Reiciendis fugit aliquid corporis rerum omnis quidem, libero
                ducimus nostrum quos laboriosam laborum vero officia tempora
                sint nesciunt.
              </p>
            </div>
            <div class="single-list">
              <img src="../assets/img/upc.jpg" alt="" />
              <h4>UPC</h4>
              <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit.
                Reiciendis fugit aliquid corporis rerum omnis quidem, libero
                ducimus nostrum quos laboriosam laborum vero officia tempora
                sint nesciunt.
              </p>
            </div>

            <div class="single-list">
              <img src="../assets/img/R-pvc.jpeg" alt="" />
              <h4>R-PVC</h4>
              <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit.
                Reiciendis fugit aliquid corporis rerum omnis quidem, libero
                ducimus nostrum quos laboriosam laborum vero officia tempora
                sint nesciunt.
              </p>
            </div>
            <div class="single-list">
              <img src="../assets/img/uPVCFITTINGS.jpg" alt="" />
              <h4>uPVC FITTINGS</h4>
              <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit.
                Reiciendis fugit aliquid corporis rerum omnis quidem, libero
                ducimus nostrum quos laboriosam laborum vero officia tempora
                sint nesciunt.
              </p>
            </div>
            <div class="single-list">
              <img src="../assets/img/pvc_fitting.webp" alt="" />
              <h4>PVC Fitting</h4>
              <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit.
                Reiciendis fugit aliquid corporis rerum omnis quidem, libero
                ducimus nostrum quos laboriosam laborum vero officia tempora
                sint nesciunt.
              </p>
            </div>
            <div class="single-list">
              <img src="../assets/img/upc.jpg" alt="" />
              <h4>UPC</h4>
              <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit.
                Reiciendis fugit aliquid corporis rerum omnis quidem, libero
                ducimus nostrum quos laboriosam laborum vero officia tempora
                sint nesciunt.
              </p>
            </div>

            <div class="single-list">
              <img src="../assets/img/R-pvc.jpeg" alt="" />
              <h4>R-PVC</h4>
              <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit.
                Reiciendis fugit aliquid corporis rerum omnis quidem, libero
                ducimus nostrum quos laboriosam laborum vero officia tempora
                sint nesciunt.
              </p>
            </div>
          </div>
        </div>
      </section>
      <Contactus />
    </div>
    <Footer />
  </div>
</template>

<script>
import Footer from "../components/Footer.vue";
import Contactus from "../components/Contactus.vue";
import Nav from "../components/Nav.vue";
export default {
  name: "IndexPage",
  mounted() {
    window.addEventListener("load", (event) => {
      const arrowNext = document.querySelector(".button-next"),
        arrowPrev = document.querySelector(".button-prev"),
        imageActive = document.querySelector(".active img"),
        imageNext = document.querySelector(".next img"),
        slideActive = document.querySelector(".active"),
        slideNext = document.querySelector(".next");

      const images = [
        {
          id: 0,
          image: "https://rafaelalucas.com/dailyui/3/assets/angele-03.jpg",
        },
        {
          id: 1,
          image: "https://rafaelalucas.com/dailyui/3/assets/angele-10.jpg",
        },
        {
          id: 2,
          image: "https://rafaelalucas.com/dailyui/3/assets/angele-11.jpg",
        },
        {
          id: 3,
          image: "https://rafaelalucas.com/dailyui/3/assets/angele-12.jpg",
        },
      ];

      arrowNext.addEventListener("click", nextPhoto);
      arrowPrev.addEventListener("click", prevPhoto);

      function nextPhoto() {
        const nextId = ~~imageNext.dataset.id + 1,
          nextPicture = images.find((element) => element.id == nextId),
          bullet = document.querySelectorAll(".bullet"),
          activeBullet = [...bullet].find(
            (element) => element.dataset.id == ~~imageNext.dataset.id
          );

        // Add Classes to Anime Photos

        slideNext.classList.add("anime-next-in");
        slideActive.classList.add("anime-in");

        // To Remove the Class that anime in
        setTimeout(function () {
          slideActive.classList.remove("anime-in");
          slideNext.classList.remove("anime-next-in");
        }, 960);

        // To Populate the Active and Next Slide

        imageActive.src = imageNext.src;
        imageActive.dataset.id = imageNext.dataset.id;

        if (imageActive.dataset.id == images.length - 1) {
          imageNext.src = images[0].image;
          imageNext.dataset.id = images[0].id;
        } else {
          imageNext.src = nextPicture.image;
          imageNext.dataset.id = nextPicture.id;
        }

        // To Add Active bullets
        bullet.forEach(function (el) {
          el.classList.remove("selected");
        });
        activeBullet.classList.add("selected");
      }

      function prevPhoto() {
        const prevId = ~~imageActive.dataset.id - 1,
          prevPicture = images.find((element) => element.id == prevId),
          bullet = document.querySelectorAll(".bullet");
        let activeBullet = [...bullet].find(
          (element) => element.dataset.id == prevId
        );

        // Add Classes to Anime Photos

        slideActive.classList.add("anime-out");
        slideNext.classList.add("anime-next-out");

        // To Remove the Class that anime in
        setTimeout(function () {
          slideActive.classList.remove("anime-out");
          slideNext.classList.remove("anime-next-out");
        }, 960);

        // To Populate the Active and Next Slide
        if (imageActive.dataset.id == 0) {
          imageNext.src = imageActive.src;
          imageNext.dataset.id = imageActive.dataset.id;
          imageActive.src = images[images.length - 1].image;
          imageActive.dataset.id = images[images.length - 1].id;
          activeBullet = [...bullet].find(
            (element) => element.dataset.id == imageActive.dataset.id
          );
        } else {
          imageNext.src = imageActive.src;
          imageNext.dataset.id = imageActive.dataset.id;
          imageActive.src = prevPicture.image;
          imageActive.dataset.id = prevPicture.id;
        }

        // To Add Active bullets
        bullet.forEach(function (el) {
          el.classList.remove("selected");
        });
        activeBullet.classList.add("selected");
      }

      // To Populate the first images on page load
      imageActive.src = images[0].image;
      imageActive.dataset.id = images[0].id;

      imageNext.src = images[1].image;
      imageNext.dataset.id = images[1].id;

      // Sticky menu

      window.onscroll = function () {
        if (window.pageYOffset >= 90) {
          iconMenu.classList.add("sticky");
        } else {
          iconMenu.classList.remove("sticky");
        }
      };
      // open menu

      const iconMenu = document.querySelector(".icon-menu"),
        menuOverlay = document.querySelector(".main-nav"),
        body = document.querySelector("body");

      iconMenu.addEventListener("click", openMenu);

      // Sticky menu

      window.onscroll = function () {
        if (window.pageYOffset >= 90) {
          iconMenu.classList.add("sticky");
        } else {
          iconMenu.classList.remove("sticky");
        }
      };

      function openMenu() {
        if (iconMenu.classList.contains("icon-open")) {
          menuOverlay.classList.add("menu-close");
          iconMenu.classList.remove("icon-open");
          body.classList.remove("no-scroll");
          iconMenu.classList.remove("sticky");

          setTimeout(function () {
            menuOverlay.classList.remove("menu-open");
          }, 800);
          setTimeout(function () {
            menuOverlay.classList.remove("menu-close");
          }, 900);
        } else {
          menuOverlay.classList.remove("menu-close");
          menuOverlay.classList.add("menu-open");
          iconMenu.classList.add("icon-open");
          body.classList.add("no-scroll");

          setTimeout(function () {
            iconMenu.classList.remove("sticky");
          }, 500);
        }
      }

      // open modal video

      const videoItem = document.querySelectorAll(".video-item"),
        modalVideo = document.querySelector(".modal-video"),
        iconCloseVideo = document.querySelector(".close-video"),
        videoFrame = document.querySelector(".video-code iframe"),
        videoOpen = document.querySelector(".video-open");

      videoItem.forEach(function (el) {
        el.addEventListener("click", openVideo);
      });

      iconCloseVideo.addEventListener("click", closeVideo);
      // body.addEventListener("click", closeVideo);

      function openVideo(e) {
        const videoSrc = e.currentTarget.dataset.video;

        body.classList.add("no-scroll");

        modalVideo.classList.add("video-open");

        videoFrame.src = videoSrc;
      }

      // ytLink.href = videoUrl;

      function closeVideo() {
        body.classList.remove("no-scroll");
        modalVideo.classList.remove("video-open");
        videoFrame.src = "";
      }
    });
  },
  components: { Footer, Contactus, Nav },
};
</script>
