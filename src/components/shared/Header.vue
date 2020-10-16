<template>
 <nav class="navbar navbar-expand-sm bg-light ">
	 <ul class="nav nav-pills">
 		<router-link to="/" tag="li" active-class="active" exact><a>Home</a></router-link>
 		<router-link to="/student" tag="li" active-class="active" ><a>Students</a></router-link>
 		<router-link to="/course" tag="li" active-class="active" ><a>Courses</a></router-link>
 		<router-link to="/mark" tag="li" active-class="active" ><a>Marks</a></router-link>
	</ul>
</nav> 
  
</template>

<script>
export default {

};
</script>

<style>

</style>
