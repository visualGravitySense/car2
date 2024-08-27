<template>
  <div class="home-page">
    <Hero/>
    <About/>
    <!-- <Gift/> -->

    <!-- Преимущества обучения -->
    <Benefits/>
     <!-- <Gallery/> -->
    <!-- <br> -->


    <!-- Отзывы учеников -->
    <section class="reviews-bg">
      <div class="reviews-container">
        <h2 class="reviews-title">Отзывы</h2>
          <div class="review" v-for="project in projects" :key="project.title">
            <div class="review-header">
              <span>{{ project.date }}</span>
            </div>
            <div class="review-body">
              <h3 class="review-title">{{ project.title }}</h3>
              <p class="review-description">{{ project.description }}</p>
              <AppButton class="review-button">Комментировать</AppButton>
            </div>
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

.reviews {
  background-color: #f5f5f5; /* более мягкий цвет фона */
  padding: 20px;
}

.reviews-title {
  font-size: 1.5rem;
  font-weight: 600;
  color: #333;
  margin-bottom: 20px;
}

.review {
  background-color: #fff;
  border: 1px solid #ddd; /* более мягкая граница */
  margin-bottom: 15px;
  padding: 15px;
  border-radius: 5px; /* округление углов для мягкости */
  transition: background-color 0.3s ease; /* простой эффект при наведении */
}

.review:hover {
  background-color: #f0f0f0; /* легкий эффект изменения фона при наведении */
}

.review-header {
  font-size: 0.875rem;
  color: #666;
  margin-bottom: 10px;
}

.review-title {
  font-size: 1.25rem;
  font-weight: 600;
  color: #222;
  margin-bottom: 10px;
}

.review-description {
  font-size: 1rem;
  color: #444;
  margin-bottom: 15px;
}

.review-button {
  padding: 8px 16px;
  background-color: #007bff; /* более нейтральный цвет кнопки */
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.review-button:hover {
  background-color: #0056b3; /* темнее при наведении */
}

/* Контейнер для отзывов */

.reviews-bg {
  background-color: #f5f5f5; 
}

.reviews-container {
  max-width: 800px; /* Максимальная ширина для отзывов */
  margin: 0 auto; /* Центрируем контейнер на странице */
  padding: 20px;
  /* background-color: #f5f5f5; Фон всей секции */
  border-radius: 8px; /* Округленные углы у контейнера */
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Легкая тень для контейнера */
}

/* Заголовок секции отзывов */
.reviews-title {
  font-size: 1.5rem;
  font-weight: 600;
  color: #333;
  margin-bottom: 20px;
  text-align: center; /* Центрируем заголовок */
}

/* Карточка одного отзыва */
.review {
  background-color: #fff;
  border: 1px solid #ddd; /* Тонкая граница */
  margin-bottom: 15px;
  padding: 15px;
  border-radius: 5px; /* Округленные углы карточки */
  transition: background-color 0.3s ease; /* Эффект изменения фона при наведении */
}

/* Эффект при наведении на карточку */
.review:hover {
  background-color: #f0f0f0; /* Легкое изменение фона */
}

/* Заголовок карточки */
.review-header {
  font-size: 0.875rem;
  color: #666;
  margin-bottom: 10px;
}

/* Текст заголовка отзыва */
.review-title {
  font-size: 1.25rem;
  font-weight: 600;
  color: #222;
  margin-bottom: 10px;
}

/* Описание отзыва */
.review-description {
  font-size: 1rem;
  color: #444;
  margin-bottom: 15px;
}

/* Кнопка в карточке */
.review-button {
  padding: 8px 16px;
  background-color: #007bff; /* Основной цвет кнопки */
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

/* Эффект при наведении на кнопку */
.review-button:hover {
  background-color: #0056b3; /* Темный цвет кнопки при наведении */
}



</style>
