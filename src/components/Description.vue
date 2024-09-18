<template>
  <section id="about">
    <AnimateOnVisible name="fadeDown" :duration="1">
      <Title title="About me" description="Hii minh la Minh Anh neee" />
    </AnimateOnVisible>

    <AnimateOnVisible name="fadeRight" :duration="1">
      <div class="section-content">
        <div class="container-fluid">
          <div class="row justify-content-center">
            <Photo  />
          </div>
          <div class="row">
            <div class="col-md-7 mr-auto card-mobile">
              <Presentation :content="content" />
            </div>
            <div class="col-md-4 card-mobile">
              <PersonnalCard :user="userInfor" :links="linkUser" />
            </div>
          </div>
        </div>
      </div>
    </AnimateOnVisible>
  </section>
</template>

<script>
import Title from "./Title.vue";
import PersonnalCard from "./PersonnalCard.vue";
import Presentation from "./Presentation.vue";
import Photo from "./Photo.vue";

export default {
  name: "AboutMe",
  props: ["user", "content", "links"],
  data() {
    return {
      userInfor: {
        name: "Minh Anh",
        email: "imminhanh@gmail.com",
        phone: "(+84)945251099",
        city: "Ha Noi",
        lang: "French, English",
      },
      linkUser: {
        slug: "links",
        title: "links",
        metadata: {
          facebook: "https://www.facebook.com/minhanhneeee",
          instagram: "https://www.instagram.com/imminhanh__/?hl=en",
          linkedin: "https://www.linkedin.com",
        //   github: "https://github.com/hbollon",
        },
      },
    };
  },
  components: {
    Title,
    PersonnalCard,
    Presentation,
    Photo,
  },
};
</script>

<style scoped lang="scss">
@import "@/styles/constants.scss";

#about {
  background-color: lighten(map-get($colors, dark), 100%);
}

@media (min-width: #{map-get($breakpoints, medium)}) {
  .section-content {
    width: 80%;
    margin: 0 auto;
  }
}

@media (max-width: #{map-get($breakpoints, medium)}) {
  .card-mobile {
    text-align: center !important;
    margin-top: 20px;
  }
}
</style>
