<template>
  <div class="home-page">

    <Hero/>

    <About/>

    <Gift/>

    <!-- Преимущества обучения -->
    <Benefits/>

     <!-- <Gallery/> -->
    <br>


    <!-- Отзывы учеников -->
    <section class="projects">
    <h2 class="text-2xl font-semibold text-black">Отзывы</h2>
    <div class="project transform transition hover:scale-105 hover:shadow-xl" v-for="project in projects" :key="project.title">
      <div class="project-header">
        <span>{{ project.date }}</span>
      </div>
      <div class="project-body">
        <h3 class="text-2xl font-semibold text-black">{{ project.title }}</h3>
        <p>{{ project.description }}</p>
        <AppButton class="project transform transition hover:scale-105 hover:shadow-xl">Комментировать</AppButton>
      </div>
    </div>
  </section>




    <!-- Ссылки на социальные сети -->
    <!-- <section class="social-media">

      <h2>Мы в социальных сетях</h2>
      <div class="social-links">
        <a v-for="social in socialMedia" :key="social.platform" :href="social.link">{{ social.platform }}</a>
      </div>
    </section> -->

    <!-- Форма подписки на новости -->
    <!-- <section class="newsletter">
      <h2>Подпишитесь на новости</h2>
      <form @submit.prevent="subscribeNewsletter">
        <label for="email">Email:</label>
        <input class="bg-gray-100" type="email" id="email" v-model="newsletterEmail" required />
        <button type="submit">Подписаться</button>
      </form>
    </section> -->
  </div>
</template>

<script>
import instructorsList from '~/components/Instructors/InstructorsList.vue';
import gallery from '~/components/Gallery.vue';
import gift from '~/components/Gift.vue';
export default {
  components: { instructorsList, gallery, gift  },

  data() {

    return {
      projects: [
        // { date: '18.11.2020', title: 'Сергей', description: 'Хорошо и понятно все объясняют. Хорошо преподают вождение. Многие мои знакомые рады этой школе.' },
        // { date: '13.11.2020', title: 'Aisel Agajeva', description: 'Очень счастлива что именно в этой автошколе я училась, так как все экзамены что у них что и в эрка сдала с первого раза! И сдавала в Таллинне, где говорили что тяжело сдать с первого раза, но благодаря чудесным учителям, я это сделала! Спасибо большое!' },
        // { date: '13.11.2020', title: 'Ульяна Зыкова', description: 'Шикарная автошкола, отличные преподаватели. Все доступно объясняют. Хорошее отношение к ученикам)) советую всем 100%.' },
        { date: '13.11.2020', title: 'Leonid', description: 'Väga hea autokool.' },
        { date: '05.11.2020', title: 'Taavi.T', description: 'Meeldis väga, kõik väga sõbralikud!' },
        // { date: '31.10.2020', title: 'Erik', description: '3 дня назад получил права благодаря автошколе Viktorija Autokool. Преподаватели в школе-настоящие профессионалы, это чувствуется. Мой преподаватель теории и по вождению Игорь Колесник, объяснял всё очень подробно и доступно, поэтому на экзамене проблем не возникло, всё без ошибок. На теории Игорь объяснял нам все возможные ситуации, которые могут возникнуть во время вождения на машине, теоретические вопросы, разбирали ошибки и ситуации. Всё было по доброму, от этого человека исходила уверенность в нас, приятно видеть когда в нас «неуверенных чайников « верят. Вот и началось вождение, сначала Кадриорг, а потом город. Для меня каждый раз вождение это был праздник! Игорь был уверен, что мы все сможем, верил в меня и подбадривал, некоторые моменты не получались, а он настраивал, что всё получится, всё сможем!!! Это самый лучший инструктор! Мастер своего дела! Строгость и доброта в одном человеке! С ним легко осваиваются все трудности, которые были при вождении в машине. Игорь Колесник смог настроить меня в момент мандража, перед экзаменом. Я с этим инструктором сдал все экзамены с первого раза!!!))) И благодаря о таком учении!) От души, спасибо, за такое обучение и подход к своим ученикам!!!' },
      ],
      categories: [
        { id: 'A', title: 'Категория A', description: 'Описание категории A...' },
        { id: 'A1', title: 'Категория A1', description: 'Описание категории A1...' },
        { id: 'A2', title: 'Категория A2', description: 'Описание категории A2...' },
        { id: 'AM', title: 'Категория AM', description: 'Описание категории AM...' },
        { id: 'B', title: 'Категория B', description: 'Описание категории B...' }
      ],
      reviews: [
        { id: 1, text: 'Отзыв 1', author: 'Автор 1' },
        { id: 2, text: 'Отзыв 2', author: 'Автор 2' }
      ],

      videos: [
        { id: 1, src: 'path/to/video1.mp4' },
        { id: 2, src: 'path/to/video2.mp4' }
      ],


      socialMedia: [
        { platform: 'Facebook', link: 'https://facebook.com' },
        { platform: 'Instagram', link: 'https://instagram.com' }
      ],
      newsletterEmail: ''
    };
  },
  methods: {
    subscribeNewsletter() {
      // Обработка подписки на новости
      alert(`Подписка на новости с email: ${this.newsletterEmail}`);
      this.newsletterEmail = '';
    }
  },
  computed: {
    postsLoaded () {
      return this.$store.getters.getPostsLoaded
    }
  }
}
</script>

<style>

.hero-banner h1 {
  font-size: 2.5em;
}

.hero-banner p {
  font-size: 1.2em;
}

.hero-banner button {
  padding: 10px 20px;
  font-size: 1em;
  margin-top: 20px;
}

.main-nav ul {
  display: flex;
  justify-content: center;
  list-style: none;
  padding: 0;
}

.main-nav ul li {
  margin: 0 15px;
}

.main-nav ul li a {
  text-decoration: none;
  color: #007BFF;
}

.about-us, .advantages, .categories, .testimonials, .certificates, .photo-gallery, .video-lessons, .instructors, .news-updates, .social-media, .newsletter {
  padding: 20px;
  background-color: #fff;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

h2 {
  margin-bottom: 20px;
}

ul {
  list-style-type: disc;
  padding-left: 20px;
}

.gallery, .videos, .social-links {
  display: flex;
  flex-wrap: wrap;
  justify-content: center; /* Centers the block horizontally */
}

.gallery img, .videos video {
  width: 100%;
  max-width: 200px;
/*  margin: 10px; */
}

.social-links a {
  margin: 0 10px;
  text-decoration: none;
  color: #007BFF;
}

form {
  display: flex;
  flex-direction: column;
}

form label {
  margin: 10px 0 5px;
}

form input, form button {
  padding: 10px;
  margin-bottom: 20px;
}

form button {
  background-color: #007BFF;
  color: white;
  border: none;
  cursor: pointer;
}

.projects {
  background: #e1e1e1;
  padding: 20px;
}
.project {
  background: #fff;
  border: 2px solid #000;
  margin-bottom: 20px;
  padding: 20px;
  box-shadow: 5px 5px 0 #000;
}
.project-header {
  background: #fc3d93;
  padding: 10px;
}
.project-body h3 {
  margin: 0 0 10px;
}
.project-body p {
  margin: 0 0 10px;
}
.project-body button {
  padding: 10px 20px;
  background: #9dff00;
  color: #141313;
  border: none;
  cursor: pointer;
}

</style>
