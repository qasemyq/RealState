<template>
  <div>
    <div
      class="modal fade"
      id="login"
      tabindex="-1"
      role="dialog"
      aria-labelledby="loginTitle" 
      aria-hidden="true" 
    >
      <div class="modal-dialog modal-dialog-centered" role="document">
        <div class="modal-content">
          <div class="modal-body">
            <ul
              class="nav nav-fill nav-pills mb-3"
              id="pills-tab"
              role="tablist"
            >
              <li class="nav-item">
                <a
                  class="nav-link active"
                  id="pills-home-tab"
                  data-toggle="pill"
                  href="#pills-login"
                  role="tab"
                  aria-controls="pills-login"
                  aria-selected="true"
                  >Login</a
                >
              </li>
              <li class="nav-item">
                <a
                  class="nav-link"
                  id="pills-register-tab"
                  data-toggle="pill"
                  href="#pills-register"
                  role="tab"
                  aria-controls="pills-register"
                  aria-selected="false"
                  >Signup</a
                >
              </li>
            </ul>

            <div class="tab-content" id="pills-tabContent">
              <div
                class="tab-pane fade show active"
                id="pills-login"
                role="tabpanel"
                aria-labelledby="pills-login-tab"
              >
                <h5 class="text-center"><b>Login Please</b></h5>
                <div class="form-group">
                  <label for="exampleInputEmail1">Email address</label>
                  <input
                    type="email"
                    class="form-control"
                    id="exampleInputEmail1"
                    aria-describedby="emailHelp"
                    placeholder="Enter email"
                  />
                  <small class="form-text text-muted"
                    >We'll never share your email with anyone else.</small
                  >
                </div>
                <div class="form-group">
                  <label for="exampleInputPassword1">Password</label>
                  <input
                    type="password"
                    class="form-control"
                    id="exampleInputPassword1"
                    placeholder="Password"
                  />
                </div>

                <div class="form-group">
                  <button class="btn btn-primary">Login</button>
                </div>
              </div>
              <div
                class="tab-pane fade"
                id="pills-register"
                role="tabpanel"
                aria-labelledby="pills-register-tab"
              >
                <h5 class="text-center"><b>Create New Account</b></h5>

                <div class="form-group">
                  <label for="name">Your name</label>
                  <input
                    v-model="name"
                    type="text"
                    class="form-control"
                    id="name"
                    placeholder="Your nice name"
                  />
                </div>

                <div class="form-group">
                  <label for="email">Email address</label>
                  <input
                    v-model="email"
                    type="email"
                    class="form-control"
                    id="email"
                    aria-describedby="emailHelp"
                    placeholder="Enter email"
                  />
                </div>
                <div class="form-group">
                  <label for="password">Password</label>
                  <input
                    v-model="password"
                    type="password"
                    class="form-control"
                    id="password"
                    placeholder="Password"
                  />
                </div>
                <div class="form-group">
                  <button class="btn btn-primary" @click="register">
                    Signup
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import fb from "../firebaseDb";

export default {
  data() {
    return {
      name: null,
      email: null,
      password: null,
    };
  },
  methods: {
    register() {
      fb.auth()
        .signInWithEmailAndPassword(this.email, this.password)
        .then((userCredential) => {
          // Signed in
          var user = userCredential.user;
          console.log(user)
          // ...
        })
        .catch((error) => {
          
            console.log(error);
          
        });
    },
  },
};
</script>

<style scoped></style>
