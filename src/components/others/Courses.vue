<template>
    <div class="container">
        <form>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <h1>Course Input</h1>
                    <hr>
                    <div class="form-group">
                        <label for="text">Course Name</label>
                        <input
                                v-model="course_name"
                                type="text"
                                class="form-control">
                    </div>
                </div>
            </div>
           
          
            <hr>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <button
                            @click.prevent="addCourse"
                            class="btn btn-primary"
                            >Submit!
                    </button><button
                            v-if="edit"
                            @click.prevent="modifyCourse"
                            class="btn btn-primary"
                            >Modify!
                    </button>
                    
                </div>
            </div>
        </form>
        <hr>
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Avaible course</h4>
                    </div>
                    <div class="panel-body">
                          <table class="table">
                            <thead>
                              <tr>
                                <th>ID</th>
                                <th>Course Name</th>
                                <th>Actions</th>
                              </tr>
                            </thead>
                            <tbody>
                              <tr v-for="(course, index) in courses">
                                <td>{{ index }}</td>
                                <td>{{ course }}</td>
                                <td>
                                    <button 

                                        type="button" 
                                        class="btn btn-primary btn-sm" 
                                        @click="getCourse(course)"

                                        >Edit
                                    </button>
                                    <button 

                                        type="button" 
                                        class="btn btn-danger btn-sm" 
                                        @click="deleteCourse(index)"
                                        >Delete

                                    </button>
                                </td>
                              </tr>
                            </tbody>
                          </table>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    computed : {
        courses(){
            return this.$store.state.courses;
        }
    },
  data (){
    return {
        course_name : '',
        course_index :0,
        edit : false
        
    }
  },
  methods : {
    addCourse(){
        this.$store.state.courses.push(this.course_name);
        this.course_name='';
    },
    getCourse(course){
        this.edit = true;
        this.course_name = course;
        this.course_index = this.$store.state.courses.indexOf(this.course_name);
        cosole.log(this.course_index);

    },

    deleteCourse(index){
        this.$store.state.courses.splice(index, 1);
    },

    modifyCourse(){
        this.$store.state.courses.splice(this.course_index, 1, this.course_name);
        this.course_name='';
        this.edit = false;

    }
  }
};
</script>

<style>

</style>
