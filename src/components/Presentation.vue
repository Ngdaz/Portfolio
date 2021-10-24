<template>
  <div class="paragraph">
    <h3>WHO AM I ?</h3>
    <div class="begin">
      As an undergraduate student of Medical Science and Technology program at
      University of Science and Technology of Hanoi (USTH), I would like to work
      for Laboratory, research institute
    </div>
    <!-- <p>{{content.metadata.pres_second}}</p> -->
  </div>
</template>

<script>
export default {
  name: "Description",
  props: ["content"],
};
</script>

<style scoped lang="scss">
@import "@/styles/constants.scss";

.paragraph {
  color: map-get($colors, primary);
  .begin {
    color: map-get($colors, secondary);
  }
}
</style>
