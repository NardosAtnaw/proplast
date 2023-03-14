<template>
  <div>
    <Nav />
    <section class="page-header">
      <div class="container">
        <div class="page-wrapper">
          <article>
            <h1 class="site-title">ABOUT US</h1>
          </article>
        </div>
      </div>
    </section>
    <section class="about-section row-max-grid">
      <div class="container">
        <!-- <h2>Our Story</h2> -->
        <p>
          PROPLAST PIPE AND FITTING MANUFACTURING is a private company
          established with a capital of 60 million birr in 2013 in E.C at Gondar
          to manufacture high quality uPVC Pipes, PPR Pipes,HDPE Pipes,uPVC
          FITTINGS, PPR FITTINGS
        </p>
        <p>
          A private firm named PROPLAST Pipe and Fitting Manufacturing was
          founded at Gondar with a capital of 60 million Birr to produce high
          quality uPVC Pipes, PPR Pipes, HDPE Pipes, and uPVC Fittings. PPR
          Fittings, Fittings
        </p>
      </div>
    </section>
    <section class="vm row-max-grid">
      <div class="container">
        <div class="vision">
          <img src="../assets/img/vision.svg" alt="" />
          <h4>Our Vision</h4>
          <p>
            To become regional leadership in plastic manufacturing industries
            with global standards.
          </p>
        </div>
        <div class="mission">
          <img src="../assets/img/mission.svg" alt="" />
          <h4>Our Mission</h4>
          <p>
            To become a supplier of choice by providing high quality PIPES and
            FITTINGS for government infrastructure projects construction
            companies and private home construction companies and private home
            builders
          </p>
        </div>
      </div>
    </section>
    <section class="gallery row-max-grid">
      <div class="gallery-wrapper">
        <img src="../assets/img/1.jpg" alt="" />
        <img src="../assets/img/2.jpg" alt="" />
        <img src="../assets/img/9.jpg" alt="" />
        <img src="../assets/img/4.jpg" alt="" />
        <img src="../assets/img/5.jpg" alt="" />
        <img src="../assets/img/6.jpg" alt="" />
      </div>
    </section>
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
