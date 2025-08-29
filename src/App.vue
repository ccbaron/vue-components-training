<script setup>
import IdCard from './components/IdCard.vue';
import Random from './components/Random.vue';
import BoxColor from './components/BoxColor.vue';
import CreditCard from './components/CreditCard.vue';
import Rating from './components/Rating.vue';
import DriverCard from './components/DriverCard.vue';
import LikeButton from './components/LikeButton.vue';
import ClickablePicture from './components/ClickablePicture.vue';
import Dice from './components/Dice.vue';
import Carousel from './components/Carousel.vue';
import NumbersTable from './components/NumbersTable.vue';
import FaceBook from './components/FaceBook.vue';
import SignupPage from './components/SignupPage.vue';
import RGBColorPicker from './components/RGBColorPicker.vue';
</script>

<template>
  <div id="app">
    <h1>Creación de componentes con Vue</h1>
    <p>Crea a continuación todos los componentes del ejercicio.</p>

    <!-- Componente IdCard -->
    <IdCard
      lastName="Doe"
      firstName="John"
      gender="male"
      :height="178"
      :birth="new Date('1992-07-14')"
      picture="https://randomuser.me/api/portraits/men/44.jpg"
    />
    <IdCard
      lastName="Delores"
      firstName="Obrien"
      gender="female"
      :height="172"
      :birth="new Date('1988-05-11')"
      picture="https://randomuser.me/api/portraits/women/44.jpg"
    />

    <!-- Componente Random -->
    <Random :min="1" :max="6" />
    <Random :min="1" :max="100" />

    <!-- Componente BoxColor -->
    <BoxColor :r="255" :g="0" :b="0" />
    <BoxColor :r="128" :g="255" :b="0" />

    <!-- Componente CreditCard -->
    <CreditCard
      type="Visa"
      number="0123456789018845"
      :expiration-month="3"
      :expiration-year="2021"
      bank="BNP"
      owner="Maxence Bouret"
      bgColor="#11aa99"
      color="white"
    />
    <CreditCard
      type="Master Card"
      number="0123456789010995"
      :expiration-month="3"
      :expiration-year="2021"
      bank="N26"
      owner="Maxence Bouret"
      bgColor="#eeeeee"
      color="#222222"
    />

    <!-- Componente Rating -->
    <Rating :value="4.5" />

    <!-- Componente DriverCard -->
    <DriverCard
      name="Travis Kalanick"
      :rating="4.2"
      img="https://si.wsj.net/public/resources/images/BN-TY647_37gql_OR_20170621052140.jpg?width=620&height=428"
      :car="{ model: 'Toyota Corolla Altis', licensePlate: 'CO42DE' }"
    />

    <!-- Componente LikeButton -->
    <LikeButton />

    <!-- Componente ClickablePicture -->
    <ClickablePicture img="/public/maxence.png" img-clicked="/public/maxence-glasses.png" />

    <!-- Componente Dice -->
    <Dice />

    <!-- Componente Carousel -->
    <Carousel :images="['/public/visa.png', '/public/master-card.svg']" />

    <!-- Componente NumbersTable -->
    <NumbersTable :limit="12" />

    <!-- Componente FaceBook -->
    <FaceBook />

    <!-- Componente SignupPage -->
    <SignupPage />

    <!-- Componente RGBColorPicker -->
    <RGBColorPicker />
  </div>
</template>

<style scoped>
/* Add any global styles here */
</style>
