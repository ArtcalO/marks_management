<template>
    <div class="container">
        <form>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <h1>Student Form</h1>
                    <hr>
                    <div class="form-group">
                        <label for="text">First Name</label>
                        <input
                                v-model="student_data.name"
                                type="text"
                                class="form-control">
                    </div>

                    <div class="form-group">
                        <label for="text">Last Name</label>
                        <input
                                v-model="student_data.subname"
                                type="text"
                                class="form-control">
                    </div>
                    <div class="form-group">
                        <label for="number">Age</label>
                        <input
                                v-model="student_data.age"
                                type="number"
                                class="form-control">
                    </div>
                </div>
            </div>
           
          
            <hr>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <button
                            @click.prevent="addStudent"
                            class="btn btn-primary"
                            >Submit!
                    </button>
                    <button
                            v-if="edit"
                            @click.prevent="modifyStudent"
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
                        <h4>Registered Student Student</h4>
                    </div>
                    <div class="panel-body">
                        <table class="table">
                            <thead>
                              <tr>
                                <th>ID</th>
                                <th>Name</th>
                                <th>Subname</th>
                                <th>Age</th>
                                <th>Actions</th>
                              </tr>
                            </thead>
                            <tbody>
                              <tr v-for="(student, index) in students">
                                
                                <td>{{ index }}</td>
                                <td>{{ student.Name }}</td>
                                <td>{{ student.Subname }}</td>
                                <td>{{ student.Age }}</td>
                                <td>
                                    <button 

                                        @click.prevent="getStudent(student, index)"
                                        type="button" 
                                        class="btn btn-primary btn-sm" 
                            
                                        >Edit
                                    </button>
                                    <button 
                                        @click.prevent="deleteStudent(index)"
                                        type="button" 
                                        class="btn btn-danger btn-sm" 
                                        
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
    data(){
        return {
            student_data : {
                name : '',
                subname : '',
                age : 0,
            },
            edit : false,
            std_index : 0
        }
    },
    computed : {
        students(){
            return this.$store.state.students;
        }
    },
    methods : {
        init(obj){
            this.name = '';
            this.subname = '';
            this.age = 0;
        },
        addStudent(){
            this.$store.state.students.push({
                Name : this.student_data.name,
                Subname : this.student_data.subname,
                Age : this.student_data.age
            });
        },
        getStudent(student, index){
            this.edit = true;
            this.student_data.name = student.Name;
            this.student_data.subname = student.Subname;
            this.student_data.age = student.Age;
            this.std_index = index;
        },
        modifyStudent(){
            this.$store.state.students.splice(this.std_index,1,{
                Name : this.student_data.name,
                Subname : this.student_data.subname,
                Age : this.student_data.age
            });
        },
        deleteStudent(index){
            this.$store.state.students.splice(index, 1);
        }

    }
  
};
</script>

<style>

</style>
