<template>
  <div id="app">
    <app-header></app-header>
    <hr>
    <app-course></app-course>
    <hr>
    <app-mark></app-mark>
    <hr>
    <app-student></app-student>
    <hr>
    <app-footer></app-footer>
  </div>
</template>

<script>

import Courses from './components/others/Courses.vue';
import Marks  from './components/others/Marks.vue';
import Students  from './components/others/Students.vue';

import Header  from './components/shared/Header.vue';
import Footer  from './components/shared/Footer.vue';

export default {
  components : {
    'app-course' : Courses,
    'app-mark' : Marks,
    'app-student' : Students,

    'app-header' : Header,
    'app-footer' : Footer
  }
  
};
</script>

<style>

</style>
