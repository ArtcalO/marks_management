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
                            @click.prevent="addMark"
                            class="btn btn-primary"
                            >Submit!
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
                              </tr>
                            </thead>
                            <tbody>
                              <tr v-for="(course, index) in courses">
                                <td>{{ index }}</td>
                                <td>{{ course }}</td>
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
  props : ['courses'],
  data (){
    return {
        course_name : '',
        
    }
  },
  methods : {
    addMark(){
        console.log(this.course_name);
        this.$emit('courseCreated', this.course_name);
        this.course_name='';
    }
  }
};
</script>

<style>

</style>
