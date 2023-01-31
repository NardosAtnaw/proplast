<template>
    <div>
      <Nav />
      <section class="page-header">
        <div class="container">
          <div class="page-wrapper">
            <article>
              <h1 class="site-title">Contact Us</h1>
            </article>
          </div>
        </div>
      </section>
  
      <div class="wrapper">
        <Contactus />
  
        <section class="map1 row-max-grid">
          <div class="container">
            <h1 class="title center">Our Location</h1>
            <p class="text center">
              If you want to register or contact us in person here is the link for
              our location.
            </p>
            <div class="separt1">
              <div class="container">
                <div class="box"></div>
              </div>
            </div>
  
            <div class="map-container">
              <div class="location">
                <div class="map-responsive">
                  <iframe
                    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d62299.41569535554!2d37.421428505145286!3d12.601125321440048!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x164328823d244edf%3A0x7826245358a8a65!2sGondar!5e0!3m2!1sen!2set!4v1666700544278!5m2!1sen!2set"
                    width="600"
                    height="450"
                    style="border: 0"
                    allowfullscreen=""
                    loading="lazy"
                    referrerpolicy="no-referrer-when-downgrade"
                  ></iframe>
                </div>
              </div>
            </div>
          </div>
        </section>
        <section></section>
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
            image: "_nuxt/assets/img/3.jpg",
          },
          {
            id: 1,
            image: "_nuxt/assets/img/3.jpg",
          },
          {
            id: 2,
            image: "_nuxt/assets/img/2.jpg",
          },
          {
            id: 3,
            image: "_nuxt/assets/img/4.jpg",
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
  