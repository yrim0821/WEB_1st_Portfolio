<template>
<v-app>
  <v-header>
    <span style="position:fixed; z-index:6; background-color:white; width:100% ">
      <h3>
        <nav class="navbar navbar-expand-lg navbar-light bg-light">
          <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav">
              <li class="nav-item active">
                <router-link to="/">홈</router-link>
              </li>
              <li class="nav-item">
                <router-link to="/post">포스트</router-link>
              </li>
              <li class="nav-item">
                <router-link to="/portfolio">포트폴리오</router-link>
              </li>
              <li class="nav-item">
                <router-link to="/login">로그인</router-link>
              </li>
            </ul>
          </div>
        </nav>
      </h3>
    </span>
  </v-header>

  <v-content>
    <router-view />
  </v-content>

  <v-footer>
    <h2>Footer</h2>
  </v-footer>
</v-app>
</template>

<script>
import store from './store'

export default {
  name: 'App',
  store,
  data() {
    return {
      //
    }
  }
}
</script>
