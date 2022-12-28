<script>
export default {
  name: 'app',
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
      courses: [
        {
          id: 1,
          title: 'VueJS',
          description: 'The demo description for vuejs',
        },
        {
          id: 2,
          title: 'Laravel',
          description: 'The demo description for Laravel',
        },
        {
          id: 3,
          title: 'NuxtJS',
          description: 'The demo description for NuxtJS',
        },
      ],
    }
  },
  methods: {
    test() {
      this.msg = 'changed';
    }
  }
};
</script>

<template>
  <header>
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </nav>
  </header>

  <RouterView></RouterView>

  <div class="container mx-auto">
    <h2 class="text-4xl font-bold text-state-900">{{ msg }}</h2>
  <button class="bg-red-500 text-white py-2 px-6 text-xl rounded mt-6" @click="test">Test</button>


    <h2 class="mt-8 text-2xl font-bold text-state-900">Courses</h2>


    <div v-for="course in courses" class="mt-2 shadow p-4 mb-4 rounded-lg border border-gray-500">
      <h2 class="text-xl font-bold text-state-900">{{ course.title }}</h2>
      <p>{{ course.description }}</p>
    </div>
  </div>
</template>