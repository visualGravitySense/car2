<template>
  <footer class="footer">
    <div class="footer__container">
      

      <div class="footer__row">
        <div class="footer__column">
          <div class="footer__logo">
            <nuxt-link class="flex pt-8 sm:pt-0" to="/">
              <img src="@/assets/img/viktorija-logo-1a.png" alt="logo-viktorija">


              
            </nuxt-link>    
          </div>
        </div>
        <div class="footer__column">
          
          <div class="footer__contact">
  <p><strong>Адрес:</strong> <a href="https://www.google.com/maps/place/Jaama+1a,+N%C3%B5mme,+Tallinn" target="_blank" rel="noopener noreferrer">Jaama 1a, Nõmme, Tallinn</a></p>
  <p><strong>Телефон:</strong> <a href="tel:+37253464508">+372 53464508</a></p>
  <p><strong>Email:</strong> <a href="mailto:info@viktorijaautokool.ee">info@viktorijaautokool.ee</a></p>
</div>

          
        </div>
      </div>

      <div class="footer__nav">
        <p class="footer__description">Автошкола Viktorija: Обучение, которое ведет к мастерству!</p>

            <ul class="footer__nav-list">
              <li class="footer__nav-item"><NuxtLink to="/">Главная</NuxtLink></li>
              <li class="footer__nav-item"><NuxtLink to="/about">О нас</NuxtLink></li>
              <li class="footer__nav-item"><NuxtLink to="/services">Услуги</NuxtLink></li>
              <li class="footer__nav-item"><NuxtLink to="/reviews">Отзывы</NuxtLink></li>
              <li class="footer__nav-item"><NuxtLink to="/contact">Контакты</NuxtLink></li>
            </ul>
          </div>

      

      <div class="footer__social">
        <a href="https://facebook.com" class="footer__social-link" target="_blank" rel="noopener noreferrer">
          <i class="fab fa-facebook-f">Facebook</i>
        </a>
        <a href="https://youtube.com" class="footer__social-link" target="_blank" rel="noopener noreferrer">
          <i class="fab fa-youtube">Youtube</i>
        </a>
        <a href="https://instagram.com" class="footer__social-link" target="_blank" rel="noopener noreferrer">
          <i class="fab fa-instagram">Instagram</i>
        </a>
      </div>

      
    </div>

    <div class="footer__bottom">
      <p>&copy; 2024 Автошкола Viktorija. Все права защищены.</p>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      email: ''
    };
  },
  methods: {
    subscribe() {
      // Логика подписки на новости
      alert(`Вы подписались на новости с email: ${this.email}`);
    }
  }
};
</script>

<style scoped>

.footer__contact a {
  color: #fff;
  text-decoration: none;
}
.footer__contact a:hover {
  text-decoration: underline;
}

.footer {
  background-color: #080e1e;
  color: #fff;
  padding: 20px 0;
}
.footer__container {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.footer__row {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  margin-top: 20px;
}

.footer__column {
  flex: 1 1 45%;
  margin-bottom: 20px;
}

.footer__logo {
  
}
.footer__logo-img {
  max-width: 150px;
}
.footer__description {
  margin-top: 10px;
  font-size: 14px;
}
.footer__nav {
  margin-top: 20px;
}
.footer__nav-list {
  list-style: none;
  padding: 0;
}
.footer__nav-item {
  display: inline;
  margin: 0 10px;
} 
.footer__nav-item a {
  color: #fff;
  text-decoration: none;
}
.footer__contact {
  margin-top: 20px;
}
.footer__social {
  margin-top: 20px;
}
.footer__social-link {
  color: #fff;
  margin: 0 10px;
  font-size: 20px;
}
.footer__subscribe {
  margin-top: 20px;
}
.footer__subscribe input {
  padding: 10px;
  border: none;
  border-radius: 5px;
}
.footer__subscribe button {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  background-color: #555;
  color: #fff;
  cursor: pointer;
}
.footer__bottom {
  margin-top: 20px;
  text-align: center;
  
}
</style>
