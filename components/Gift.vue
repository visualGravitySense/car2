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
/* Основные стили */
.gift-card {
  display: flex;
  flex-direction: column;
  gap: 20px;
  padding: 20px;
}

.gift-info, .gift-certificate {
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 15px;
  background-color: #fff;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
}

.text-description {
  color: #333;
}

.certificate-heading {
  font-size: 20px;
  margin-bottom: 15px;
  color: #333;
}

.custom-component {
  display: flex;
  align-items: center;
  gap: 10px;
}

.image-block i {
  color: #4CAF50;
}

.text-block {
  flex: 1;
}

.green-text {
  color: #4CAF50;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.form-input {
  padding: 8px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

.submit-btn {
  background-color: #4CAF50;
  color: #fff;
  padding: 10px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.submit-btn:hover {
  background-color: #45a049;
}

.certificate {
  max-width: 100%;
  padding: 15px;
  border: 1px solid #ddd;
  border-radius: 5px;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
  background-color: #fff;
}

.certificate-content {
  margin-top: 10px;
}

.certificate-amount, .certificate-code {
  font-weight: bold;
}

.certificate-code {
  background-color: #f0f0f0;
  padding: 5px;
  border: 1px dashed #4CAF50;
}

/* Медиазапросы для мобильных устройств */
@media (max-width: 600px) {
  .gift-card {
    padding: 10px;
  }
  
  .gift-info, .gift-certificate {
    padding: 10px;
  }

  .custom-component {
    flex-direction: column;
    align-items: flex-start;
  }

  .image-block i {
    font-size: 24px;
  }
}
</style>
