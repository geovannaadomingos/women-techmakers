<template>
  <div class="profile-card">
    <img :src="woman.photo" alt="Woman Photo" class="profile-img">
    <h2>{{ woman.name }}</h2>
    <p>{{ woman.position }} at {{ woman.company }}</p>
    <p>{{ woman.bio }}</p>
  </div>
</template>

<script>
export default {
  name: 'ProfileComponent',
  props: {
    woman: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.profile-card {
  background-color: #cae6ff;
  border-radius: 8px;
  padding: 20px;
  box-shadow: 0 4px 8px rgba(32, 52, 75, 0.1);
  transition: box-shadow 0.3s ease-in-out;
  margin-bottom: 20px;
  width: 450px;
}

.profile-card:hover {
  box-shadow: 0 8px 16px rgba(32, 52, 75, 0.2);
}

.profile-card .profile-img {
  width: 150px;
  border-radius: 8px;
  margin-bottom: 10px;
}

.profile-card h2 {
  font-size: 24px;
  margin-bottom: 5px;
}

.profile-card p {
  font-size: 16px;
  color: #20344b;
  margin-bottom: 10px;
}
</style>
