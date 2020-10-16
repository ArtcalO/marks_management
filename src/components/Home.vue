<template>
	<div class="container">
	<app-header></app-header>
	<hr>
	   <div class="container">
		  <h1>Welcome to Mark management</h1>
		  <p>Click on the link to get redirected</p>
		</div> 
		<hr>
	<app-footer></app-footer>
	</div>
</template>

<script>
import Header  from './shared/Header.vue';
import Footer  from './shared/Footer.vue';

import Courses from './others/Courses.vue';
import Marks  from './others/Marks.vue';
import Students  from './others/Students.vue';
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