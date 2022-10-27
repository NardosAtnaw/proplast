<template>
 <div>
    <section class="module ">
        <h3 class="section-title"><span>Contact </span><b>Us</b></h3>
        <div class="content"></div>
      </section>
      <section class="contact">
        <div class="container">
          <!-- <h2>Contact Us</h2> -->
          <p class="info-contact">
            Please contact us via social media or by filling out the form below.
          </p>
          <div class="contact-box">
            <div>
              <p class="header-contact"><b>Contact Form </b></p>
            </div>

            <p class="header-desc">
              To contact us, please fill out the form below and include the
              contact hours.
            </p>
            <div class="contact-wrapper">
              <div class="contact-form">
                <form action="#" method="post">
                  <div class="column">
                    <div class="box-column">
                      <div class="box">
                        <label for="the-name">Your Name</label>
                      </div>
                      <input type="text" name="name" id="the-name" />
                    </div>

                    <div class="box-column">
                      <div class="box">
                        <label for="the-name">Last Name</label>
                      </div>
                      <input type="text" name="name" id="the-name" />
                    </div>
                    <div class="box-column">
                      <div class="box">
                        <label for="the-name">Email</label>
                      </div>
                      <input type="email" name="email" id="the-email" />
                    </div>

                    <div class="box-column">
                      <div class="box">
                        <label for="the-name">Phone Number</label>
                      </div>
                      <input type="tel" name="phone" id="the-phone" />
                    </div>
                  </div>
                  <div class="box-column">
                    <div class="box">
                      <label for="the-name">Messages</label>
                    </div>
                    <textarea name="message" id="the-message"></textarea>
                  </div>

                  <div class="submit-buttons">
                    <a class="btn btn-secondary" href="#">Submit</a>
                  </div>
                </form>
              </div>
              <div class="line"></div>
              <div class="contact-info">
                <p>
                  Use the links below to contact us through our social media
                  platforms.
                </p>
                <div class="socials">
                  <ul class="social-links">
                    <li>
                      <a href=""
                        ><img
                          src="../assets/img/facebook2.svg"
                          alt=""
                        />https://www.facebook.com</a
                      >
                    </li>
                    <li>
                      <a href=""
                        ><img
                          src="../assets/img/youtube2.svg"
                          alt=""
                        />https://www.youtube.com</a
                      >
                    </li>
                    <li>
                      <a href=""
                        ><img
                          src="../assets/img/linkedin2.svg"
                          alt=""
                        />https://www.linkedin.com</a
                      >
                    </li>

                    <li>
                      <a
                        href="https://www.google.com/maps/dir//Moretech+industry+PLC,+Ethiopia,+Yeka+subcity+Woreda+07+COMOROS+STREET+Block+no+78%2F37,+Addis+Ababa,+Ethiopia/data=!4m6!4m5!1m1!4e2!1m2!1m1!1s0x164b8fbd21b0901b:0x8b85b87620e90d53?sa=X&ved=2ahUKEwjuqL7E1ff1AhVMSvEDHeQHDScQ48ADegQIAhBT"
                        ><span class="bold-spacing"> Location:</span> Gonder,
                        Ethiopia
                      </a>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
            <div class="socials2">
              <ul class="social-links">
                <li>
                  <a href=""
                    ><img src="../assets/img/facebook2.svg" alt=""
                  /></a>
                </li>
                <li>
                  <a href=""><img src="../assets/img/youtube2.svg" alt="" /></a>
                </li>
                <li>
                  <a href=""
                    ><img src="../assets/img/linkedin2.svg" alt=""
                  /></a>
                </li>
                <!-- <li>
                  <a href=""><img src="../assets/img/google2.svg" alt="" /></a>
                </li> -->
              </ul>
            </div>
          </div>
        </div>
      </section>
 </div>
  </template>
  
  <style></style>
  <script>
  import Footer from "../components/Footer.vue";
  export default {
    components: { Footer },
  };
  </script>
  