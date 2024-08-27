<template>
  <div class="gift-card">
    <div class="gift-info">
      <p class="text-description">Подарочный сертификат автошколы <b>Viktorija</b></p>
      <h2 class="certificate-heading">Подарите свободу на дороге!</h2>
      <p class="text-description">
        Идеальный подарок для тех, кто мечтает стать уверенным водителем. Этот сертификат предоставляет возможность пройти курс обучения у лучших инструкторов, на современных автомобилях и по доступной цене. Сделайте особенный подарок, который откроет новые горизонты и подарит уверенность за рулём!
      </p>
      
      <div class="custom-component">
        <div class="image-block">
          <i class="fas fa-car fa-2x" style="color: #4CAF50;"></i>
        </div>
        <div class="text-block">
          <p class="green-text">
            <b>Доступные цены: </b>Выгодные пакетные предложения и скидки, подтверждённые положительными отзывами выпускников.
          </p>
        </div>
      </div>
      
      <div class="custom-component">
        <div class="image-block">
          <i class="fas fa-money-bill-wave fa-2x" style="color: #4CAF50;"></i>
        </div>
        <div class="text-block">
          <p class="green-text">
            <b>Лёгкий процесс покупки: </b>Простой и удобный способ приобрести сертификат онлайн.
          </p>
        </div>
      </div>
    </div>
    
    <div class="gift-certificate">
      <p class="text-description">Подарочный сертификат на обучение в автошколе <b>Viktorija.</b></p>
      <h2 class="certificate-heading">🎁 Купить подарочную карточку 🎁</h2>
      
      <form @submit.prevent="onSubmit" class="form-group">
        <label for="amount">Сумма:</label>
        <AppInput class="form-input" v-model="amount" id="amount" type="number" required />
        
        <label for="friendEmail">Email друга:</label>
        <AppInput class="form-input" v-model="friendEmail" type="email" id="friendEmail" required />
        
        <label for="yourEmail">Ваш email:</label>
        <AppInput class="form-input" v-model="yourEmail" type="email" id="yourEmail" required />
        
        <AppButton class="submit-btn" @click="onSubmit">Купить сертификат</AppButton>
        
        <Message v-if="message" :message="message" />
        
        <div v-if="certificate" class="certificate">
          <h3>Сертификат</h3>
          <div class="certificate-content">
            <p class="certificate-amount">Сумма: {{ certificate.amount }} euro</p>
            <p class="certificate-name">Для: {{ certificate.friendEmail }}</p>
            <p class="certificate-code">Код: {{ certificate.code }}</p>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
import AppButton from '@/components/UI/Controls/Button.vue'
import AppInput from '@/components/UI/Controls/Input.vue'
import Message from '@/components/UI/Message.vue'

export default {
  head: {
    link: [
      {
        rel: 'stylesheet',
        href: 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.6.0/css/all.min.css'
      }
    ]
  },
  components: { AppButton, AppInput, Message },
  data() {
    return {
      message: null,
      certificate: null,
      amount: '',
      friendEmail: '',
      yourEmail: ''
    };
  },
  methods: {
    onSubmit() {
      const uniqueCode = Math.random().toString(36).substr(2, 9).toUpperCase();
      this.certificate = {
        amount: this.amount,
        yourEmail: this.yourEmail,
        friendEmail: this.friendEmail,
        code: uniqueCode
      };
      this.message = 'Submitted!';
    }
  }
}
</script>

<style scoped>

.gift-card {
    display: flex;
    gap: 20px; /* Расстояние между блоками */
    padding: 20px;
  }
.gift-info {
  
  flex: 1; /* Чтобы блоки занимали равное пространство */
  border: 1px solid #ddd; /* Лёгкая граница для визуального отделения */
  padding: 20px; /* Внутренние отступы для блока */
  border-radius: 8px; /* Закруглённые углы */
  background-color: #f9f9f9; /* Лёгкий фоновый цвет */
  border: 1px solid #ddd;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  text-align: left;
  /* background-color: #f9f9f9; */
}
  .gift-certificate {
  
  flex: 1; /* Чтобы блоки занимали равное пространство */
  border: 1px solid #ddd; /* Лёгкая граница для визуального отделения */
  padding: 20px; /* Внутренние отступы для блока */
  border-radius: 8px; /* Закруглённые углы */
  background-color: #f9f9f9; /* Лёгкий фоновый цвет */
  border: 1px solid #ddd;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  text-align: center;
  background-color: #f9f9f9;
}
.certificate-heading {
  font-size: 24px;
  margin-bottom: 20px;
  color: #333;
}
.form-group {
  margin-bottom: 0px;
  
}
label {
  display: block;
  font-weight: bold;
  margin-bottom: 5px;
  color: #333;
}
.form-input {
  width: 100%;
  /* padding: 10px; */
  /* border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #fff; */
  font-size: 16px;
}
.submit-btn {
  display: inline-block;
  padding: 10px 20px;
  background-color: #11b445;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}
.submit-btn:hover {
  background-color: #0e9e38;
}
.message {
  margin-top: 20px;
  /* color: #3182ce; */
}
.certificate {
  max-width: 400px;
  margin-top: 20px;
  padding: 20px;
  border: 2px solid #3182ce;
  border-radius: 10px;
  background: #fff;
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
  font-family: 'Times New Roman', Times, serif;
  position: relative;
  background-image: url('@/assets/img/certificate_1.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  text-align: center;
}
.certificate-content {
  border-top: 1px solid #ddd;
  border-bottom: 1px solid #ddd;
  padding: 10px 0;
  margin: 20px 0;
}
.certificate-amount,
.certificate-code {
  font-size: 18px;
  margin: 10px 0;
}
.certificate-name {
  font-size: 16px;
  margin: 10px 0;
}
.certificate-amount {
  font-weight: bold;
}
.certificate-code {
  background: #f9f9f9;
  border: 1px dashed #4CAF50;
  padding: 5px;
  border-radius: 5px;
  display: inline-block;
}
.custom-component {
  display: flex; /* Размещаем блоки в ряд */
  align-items: center; /* Выравниваем по вертикали по центру */
  gap: 8px; /* Расстояние между блоками */
  /*padding: 20px;  Добавляем отступы */
}
.image-block {
  /* Дополнительные стили для блока с изображением (если необходимо) */
}
.text-block {
  display: flex; /* Размещаем текстовые блоки в ряд */
  flex-direction: row; /* Вертикальное расположение текстов */
  gap: 3px; /* Расстояние между текстами */
}
.green-text {
  color: #333; /* Устанавливаем зелёный цвет текста */
}
.orange-text {
  color: #333; /* Устанавливаем оранжевый цвет текста */
}
</style>