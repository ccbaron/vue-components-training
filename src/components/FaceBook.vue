<template>
  <div class="fb">
    <div class="filters">
      <button
        v-for="c in countries"
        :key="c"
        :class="{ active: c === activeCountry }"
        @click="toggleCountry(c)"
      >
        {{ c }}
      </button>
      <button @click="toggleCountry(null)">Reset</button>
    </div>

    <div class="cards">
      <div
        v-for="p in profiles"
        :key="p.firstName + p.lastName"
        class="card"
        :class="{ highlight: activeCountry && p.country === activeCountry }"
      >
        <img :src="p.img" alt="Profile picture" />
        <div>
          <p><strong>First name:</strong> {{ p.firstName }}</p>
          <p><strong>Last name:</strong> {{ p.lastName }}</p>
          <p><strong>Country:</strong> {{ p.country }}</p>
          <p><strong>Type:</strong> {{ p.isStudent ? 'Student' : 'Teacher' }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import profiles from '../data/berlin.json';

export default {
  name: 'FaceBook',
  data() {
    return { profiles, activeCountry: null };
  },
  computed: {
    countries() {
      return [...new Set(this.profiles.map((p) => p.country))];
    },
  },
  methods: {
    toggleCountry(c) {
      this.activeCountry = c;
    },
  },
};
</script>

<style scoped>
.fb {
  padding: 16px;
}
.filters {
  display: flex;
  gap: 8px;
  margin-bottom: 16px;
  flex-wrap: wrap;
}
.filters button {
  padding: 8px 12px;
  border: 1px solid #ccc;
  border-radius: 6px;
  background: #f1f5f9;
  cursor: pointer;
  transition: background-color 0.3s, color 0.3s;
}
.filters button.active {
  background: #3b82f6;
  color: #fff;
}
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
  gap: 16px;
}
.card {
  display: flex;
  gap: 12px;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 12px;
  background: #394b68;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: background-color 0.3s, border-color 0.3s;
}
.card.highlight {
  background: #7993b5;
  border-color: #93c5fd;
}
.card img {
  width: 80px;
  height: 80px;
  border-radius: 6px;
  object-fit: cover;
}
</style>
