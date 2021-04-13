<template>
  <div>
    <section>
      <h2>{{ experience.name }}</h2>
      <div class="experience-details">
        <img
          :src="require(`@/assets/${experience.image}`)"
          :alt="experience.name"
        />
        <p>{{ experience.description }}</p>
      </div>
    </section>
  </div>
</template>

<script>
import store from "@/store.js";
export default {
  props: {
    slug: {
      type: String,
      required: true,
    },
    experienceSlug: {
      type: String,
      reuqired: true,
    },
  },
  computed: {
    destination() {
      return store.destinations.find(
        (destination) => destination.slug === this.slug
      );
    },
    experience() {
      return this.destination.experiences.find(
        (experience) => experience.slug === this.experienceSlug
      );
    },
  },
};
</script>

<style scoped>
.experience-details {
  display: flex;
  justify-content: space-between;
  padding: 40px 0;
}

p {
  margin: 0 40px;
  font-size: 20 px;
  text-align: left;
}
</style>
