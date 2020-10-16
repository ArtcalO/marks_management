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
                                type="text"
                                class="form-control">
                    </div>

                    <div class="form-group">
                        <label for="text">Last Name</label>
                        <input
                                type="text"
                                class="form-control">
                    </div>
                </div>
            </div>
           
          
            <hr>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <button
                            class="btn btn-primary"
                            >Submit!
                    </button>
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="isSubmitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Registered Student Student</h4>
                    </div>
                    <div class="panel-body">
                        
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
  
};
</script>

<style>

</style>
