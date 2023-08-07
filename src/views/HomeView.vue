<template>
  <div class="home">
    <b-row class="section my-5 d-flex align-items-center">
      <b-col cols="7" class="left-aligned-text">
        <h3 class="title">Elevate Your Career to the Next Level</h3>
        <span class="desc"
          >Get expert-led instruction from experienced professionals in Industry
          and gain valuable skills and knowledge that can be applied to your
          career or personal life.</span
        >
        <div class="mt-5">
          <a href="/course" class="btn btn-find">Find a Course</a>
          <a class="link-more" href="#">Learn More</a>
        </div>
      </b-col>
      <b-col cols="5">
        <img :src="HeroImg" />
      </b-col>
    </b-row>

    <b-row>
      <b-col sm>
        <b-row>
          <b-col cols="2">
            <img :src="Icon1" />
          </b-col>
          <b-col class="left-aligned-text" cols="10">
            <h4 class="title-2">Self-paced Learning</h4>
            <span class="desc"
              >This feature allows learners to progress through the course at
              their own pace, rather than being tied to a fixed schedule. This
              can be especially useful for learners who have busy schedules or
              who prefer to learn at their own speed.</span
            >
          </b-col>
        </b-row>
      </b-col>

      <b-col sm>
        <b-row>
          <b-col cols="2">
            <img :src="Icon2" />
          </b-col>
          <b-col class="left-aligned-text" cols="10">
            <h4 class="title-2">Self-paced Learning</h4>
            <span class="desc"
              >This feature allows learners to progress through the course at
              their own pace, rather than being tied to a fixed schedule. This
              can be especially useful for learners who have busy schedules or
              who prefer to learn at their own speed.</span
            >
          </b-col>
        </b-row>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import Logo from "@/assets/LogoBaru.png";
import HeroImg from "@/assets/hero.png";
import Icon1 from "@/assets/icon-1.png";
import Icon2 from "@/assets/icon-2.png";

export default {
  name: "HomeView",
  components: {},
  data() {
    return {
      TumbnailImg: Logo,
      HeroImg: HeroImg,
      Icon1: Icon1,
      Icon2: Icon2,
    };
  },
};
</script>

<style>
.left-aligned-text {
  text-align: left; /* Teks akan rata kiri */
}

.title {
  color: #fff;
  font-family: Poppins;
  font-size: 45px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
}

.title-2 {
  color: #fff;
  font-family: Poppins;
  font-size: 18px;
  font-style: normal;
  font-weight: 600;
  line-height: 30px; /* 166.667% */
}

.card {
  background-color: #ffffff00;
}

.desc {
  color: rgba(255, 255, 255, 0.6);
  font-family: Poppins;
  font-size: 16px;
  font-style: normal;
  font-weight: 400;
  line-height: 32px; /* 200% */
}

.btn-find {
  padding: 12px 17px !important;
  margin-right: 37px;
  border-radius: 100px !important;
  background: #ff5c00 !important ;
  box-shadow: 0px 15px 30px 0px rgba(0, 26, 255, 0.2);
  border: none;
}

.link-more {
  color: #ff5c00;
  font-family: Poppins;
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
  text-decoration-line: underline;
}

/* Gaya CSS untuk mode lanskap tablet */
@media screen and (min-width: 768px) and (max-width: 1024px) {
  .section {
    flex-direction: column;
    flex-direction: column-reverse;
  }
  .left-aligned-text{
    text-align:center;
  }
}
</style>
