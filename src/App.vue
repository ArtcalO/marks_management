<template>
  <div class="container">
    <app-header></app-header>
    <hr>
    <div>
      <router-view 
        :courses="courses"
        @courseCreated="createCourse"
        ></router-view>
    </div>
    <hr>
    <app-footer></app-footer>
  </div>
</template>

<script>
import Header  from './components/shared/Header.vue';
import Footer  from './components/shared/Footer.vue';

export default {
  data (){
    return {
      courses : ['Kirundi']
    }
  },
  components : {
    'app-header' : Header,
    'app-footer' : Footer
  },
  methods : {
    createCourse($emit){
      this.course.push($emit);
    }
  }
};
</script>

<style>

</style>
