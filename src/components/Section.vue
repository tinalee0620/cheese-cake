<template>
  <section class="section">
    <h4 class="section__description">
            MEMBERS
         </h4>
  
    <div class="news">
      <h3 class="news__features">SocialNews</h3>
      <ul id="socialNews" class="list-group news__list">
      </ul>
    </div>
    <div class="news">
      <h3 class="news__features">EntertainmentNews</h3>
      <ul id="entertainmentNews" class="list-group news__list">
      </ul>
    </div>
    <div class="news">
      <h3 class="news__features">SportNews</h3>
      <ul id="sportNews" class="list-group news__list">
      </ul>
    </div>
    <div class="news">
      <h3 class="news__features">TaiwanNews</h3>
      <ul id="taiwanNews" class="list-group news__list">
      </ul>
    </div>
  </section>
</template>

<script>
 
export default {

  name: "Section",
    data() {
      return {
        data: [
          '<div class="example-slide">Slide 1</div>',
          '<div class="example-slide">Slide 2</div>',
          '<div class="example-slide">Slide 3</div>',
        ],
      };
    },
};
</script>

<style lang="postcss" scoped>
@import "../../styles/base/_variables.css";
@import "../../styles/base/_global.css";
@import "../../styles/modules/_section.css";
</style>