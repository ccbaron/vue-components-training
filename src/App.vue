<script setup>
// Importamos TODOS los componentes del lab para mostrarlos en secciones
import IdCard from './components/IdCard.vue'
import Random from './components/Random.vue'
import BoxColor from './components/BoxColor.vue'
import CreditCard from './components/CreditCard.vue'
import Rating from './components/Rating.vue'
import DriverCard from './components/DriverCard.vue'
import LikeButton from './components/LikeButton.vue'
import ClickablePicture from './components/ClickablePicture.vue'
import Dice from './components/Dice.vue'
import Carousel from './components/Carousel.vue'
import NumbersTable from './components/NumbersTable.vue'
import FaceBook from './components/FaceBook.vue'
import SignupPage from './components/SignupPage.vue'
import RGBColorPicker from './components/RGBColorPicker.vue'
</script>

<template>
  <div class="wrap">
    <h1>Vue Components Training</h1>

    <!-- Iteración 1: IdCard -->
    <section>
      <h2>IdCard</h2>
      <div class="row">
        <!-- Ejemplos de tarjetas -->
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
      </div>
    </section>

    <!-- Iteración 2: Random -->
    <section>
      <h2>Random</h2>
      <div class="row">
        <Random :min="1" :max="6" />
        <Random :min="1" :max="100" />
      </div>
    </section>

    <!-- Iteración 3: BoxColor -->
    <section>
      <h2>BoxColor</h2>
      <div class="row">
        <BoxColor :r="255" :g="0" :b="0" />
        <BoxColor :r="128" :g="255" :b="90" />
      </div>
    </section>

    <!-- Iteración 4: CreditCard -->
    <section>
      <h2>CreditCard</h2>
      <div class="row">
        <CreditCard
          type="Visa"
          number="0123456789018845"
          :expiration-month="3"
          :expiration-year="2027"
          bank="BNP"
          owner="Maxence Bouret"
          bgColor="#11aa99"
          color="#ffffff"
        />
        <CreditCard
          type="Master Card"
          number="0123456789010995"
          :expiration-month="3"
          :expiration-year="2026"
          bank="N26"
          owner="Maxence Bouret"
          bgColor="#eeeeee"
          color="#222222"
        />
      </div>
    </section>

    <!-- Iteración 5: Rating -->
    <section>
      <h2>Rating</h2>
      <div class="row">
        <Rating :value="0" />
        <Rating :value="1.4" />
        <Rating :value="3.7" />
        <Rating :value="5" />
      </div>
    </section>

    <!-- Iteración 6: DriverCard -->
    <section>
      <h2>DriverCard</h2>
      <DriverCard
        name="Travis Kalanick"
        :rating="4.2"
        img="https://randomuser.me/api/portraits/men/44.jpg"
        :car="{ model: 'Toyota Corolla Altis', licensePlate: 'CO42DE' }"
      />
    </section>

    <!-- Iteración 7: LikeButton -->
    <section>
      <h2>LikeButton</h2>
      <div class="row"><LikeButton /><LikeButton /></div>
    </section>

    <!-- Iteración 8: ClickablePicture -->
    <section>
      <h2>ClickablePicture</h2>
      <ClickablePicture
        img="https://i.pravatar.cc/150?img=12"
        imgClicked="https://i.pravatar.cc/150?img=65"
      />
    </section>

    <!-- Iteración 9: Dice -->
    <section>
      <h2>Dice</h2>
      <!-- Al hacer click, se mostrará un dado vacío 1s y luego un número aleatorio -->
      <Dice />
    </section>

    <!-- Iteración 10: Carousel -->
    <section>
      <h2>Carousel</h2>
      <Carousel
        :images="[
          'https://picsum.photos/seed/1/600/400',
          'https://picsum.photos/seed/2/600/400',
          'https://picsum.photos/seed/3/600/400',
          'https://picsum.photos/seed/4/600/400'
        ]"
      />
    </section>

    <!-- Iteración 11: NumbersTable -->
    <section>
      <h2>NumbersTable</h2>
      <NumbersTable :limit="24" />
    </section>

    <!-- Iteraciones 12–13: FaceBook (simple + avanzado) -->
    <section>
      <h2>FaceBook</h2>
      <!-- Si más abajo conectas berlin.json, este componente lo usará -->
      <FaceBook />
    </section>

    <!-- Iteración 14: SignupPage -->
    <section>
      <h2>SignupPage</h2>
      <SignupPage />
    </section>

    <!-- Iteración 15: RGBColorPicker -->
    <section>
      <h2>RGBColorPicker</h2>
      <RGBColorPicker />
    </section>
  </div>
</template>

<style scoped>
.wrap {
  display: grid;
  gap: 24px;
  padding: 20px;
  max-width: 980px;
  margin: 0 auto;
  background-color: #1e293b; /* Fondo oscuro para el contenedor principal */
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
}
section {
  border: 1px solid #334155;
  border-radius: 12px;
  padding: 16px;
  background: #475569; /* Fondo gris oscuro para las secciones */
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
.row {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
  align-items: flex-start;
}
h1 {
  margin: 0 0 4px;
  color: #f8fafc; /* Texto blanco para el título principal */
}
h2 {
  margin: 0 0 12px;
  font-size: 1.1rem;
  color: #e2e8f0; /* Texto gris claro para los subtítulos */
}
p, span, div {
  color: #f1f5f9; /* Texto blanco para el contenido */
}
</style>

