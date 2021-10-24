<template>
  <section id="experience">
    <AnimateOnVisible name="fadeDown" :duration="1">
      <Title
        class="title"
        title="EXPERIENCE"
        description="PROFESSIONAL AND ACADEMIC"
      />
    </AnimateOnVisible>

    <AnimateOnVisible name="fadeUp" :duration="1">
      <div class="container-fluid">
        <div class="row">
          <ExperienceColumn
            :posts="data.academic"
            title="Education"
            class="col-12 col-md left"
          />
          <ExperienceColumn
            :posts="data.professional"
            title="Professional"
            class="col-12 col-md right"
          />
        </div>
      </div>
    </AnimateOnVisible>
  </section>
</template>

<script>
import Title from "./Title.vue";
import ExperienceColumn from "./ExperienceColumn.vue";

export default {
  name: "Experience",
  props: ["content"],
  data() {
    return {
      data: {
        academic: [
          {
            year: "2020 - Now",
            title: "Bachelor’s degree",
            content: "Ha Noi University",
          },
          {
            year: "2017 - 2020",
            title: "Bachelor’s degree",
            content: "University of science and technology of Ha Noi",
          },
          {
            year: "2014 - 2017",
            title: "Student",
            content: "Le Quy Dong Ha Noi Hight School",
          }
        ],
        professional: [
          {
            year: "2020 - Now",
            title: "Employee",
            content: "LEARNING EXPERIENCE OFFICER ( TA SUP AND ADMIN)",
          },
          {
            year: "Nov 2019",
            title: "Delegate",
            content: "Participated in Scientific seminar: Breakthroughs in Sysmex diagnostic solution",
          },
          {
            year: "June 2018 - Aug 2018",
            title: "Member",
            content: "Volunteers for Department of Customer services of Vietnam National Children's Hospital",
          },
          {
            year: "March 2018",
            title: "Supporter",
            content: "Participated in USTH open day for students ",
          }
        ]
      },
    };
  },
  components: {
    Title,
    ExperienceColumn,
  },
};
</script>

<style scoped lang="scss">
@import "@/styles/constants.scss";

$linear: map-get($colors, dark);

#experience {
  // background-color: lighten(map-get($colors, primary), 5%);
   background-image: url("../assets/img/bg.jpg");
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 72%;
}

.title {
  color: map-get($colors, light);
}

.row {
  padding-top: 20px;
  text-align: center;
}

@media (min-width: #{map-get($breakpoints, small)}) {
  .left {
    text-align: right;
    border-right: 2px solid $linear;
  }
  .right {
    text-align: left;
  }
}

@media (max-width: #{map-get($breakpoints, small)}) {
  .right {
    margin-top: 20px;
  }
  .left:before {
    content: "";
    position: absolute;
    left: 20%;
    bottom: 0;
    height: 2px;
    width: 60%; /* or 100px */
    border-bottom: 2px solid $linear;
  }
}

/deep/ .text-wrapper {
  &:after {
    border-bottom: 1px solid map-get($colors, dark);
  }
}
</style>
