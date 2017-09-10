<template>
    <div class="container">
        <form>
            <div class="row"  v-show="!isSubmitted">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">

                    <form>
                        <div class="form-group">
                          <label for="fullname">Full name:</label>
                          <input type="text" class="form-control" id="fullname" @input="updateName($event.target.value)">
                        </div>
                        <div class="form-group">
                          <label for="email">Mail:</label>
                          <input type="email" class="form-control" id="email" v-model="userData.email">
                        </div>
                        <div class="form-group">
                          <label for="pwd">Password:</label>
                          <input type="password" class="form-control" id="password" v-model="userData.password">
                        </div>
                        <div class="form-group">
                          <label><input type="checkbox" :checked="userData.store == true" v-model="userData.store">Store data</label>
                        </div>
                        <button @click.prevent="submitted">Submit</button>
                    </form>



                    <!-- Exercise 3 -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-show="isSubmitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ userData.firstname }} {{ userData.lastname}}</p>
                        <p>Mail: {{ userData.email }}</p>
                        <p>Password: {{ userData.password }}</p>
                        <p>Store in Database?: {{ userData.store }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
      data() {
        return {
          isSubmitted: false,
          userData: {
            firstname: "",
            lastname: "",
            mail: "",
            password: "",
            store: true
          }
        }
      },
      methods: {
        submitted() {
          this.isSubmitted = true;
        },
        updateName(value) {
          this.userData.firstname = value.split(' ')[0];
          this.lastname = value.split(' ')[1];
        }
      }
    }
</script>

<style>
</style>
