<template>
  <div class="container">
    <div class="row">
      <div class="offset-lg-3 col-lg-6">
        <h1 class="text-center">Form đăng ký</h1>
        <div class="form-group">
          <input type="text" class="form-control" placeholder="Username" v-model="user.username" />
        </div>
        <div class="form-group">
          <input type="text" class="form-control" placeholder="Email" v-model="user.email" />
        </div>
        <div class="form-group">
          <input type="text" class="form-control" placeholder="Password" v-model="user.password" />
        </div>

        <div class="form-group text-center">
          <button @click="submitFormFunc" class="btn btn-success">Đăng ký ngay</button>
        </div>
        
        <div class="form-group">
          <ul class="list-group">
            <li v-for="(user, index) in users" :key="index" class="list-group-item">
              {{user.email}}
            </li>
          </ul>
        </div>

        {{jsonData}}

      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'app',
    data () {
      return {
        user: {
          username: '',
          email: '',
          password: ''
        },
        users: [],
        jsonData: ''
      }
    },
    mounted() {
      this.$http.get('')
        .then(response => {
          return response.json();
        })
        .then(data => {
          const arr = [];
          for(let key in data) {
            arr.push(data[key]);
          }
          this.users = arr;
        });

      // var vm = this;
      // this.$http.get('https://yesno.wtf/api')
      //   .then(response => {
      //     console.log(response);
      //     vm.jsonData = response.data;
      //   }, error => {
      //     console.log(error);
      //   })
    },

    methods: {
      submitFormFunc: function() {
        this.$http.put('', this.user)
          .then(response => {
            console.log(response);
          }, error => {
            console.log(error);
          })
      }
    }
}
</script>
