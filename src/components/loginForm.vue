<template>

    <v-app>
      <v-card>
        <v-card-title>
          <h1>Login</h1>
        </v-card-title>
        <v-card-text>
          <v-form>
              <v-text-field 
                label="username"
                name="username"
                prepend-icon="mdi-account"
                type="text"
              />
              <v-text-field
                label="password"
                name="password"
                prepend-icon="mdi-lock"
                type="password"
              />
              <v-btn
                href="/"
                large
                color="primary">
                login</v-btn>
          </v-form>
        </v-card-text>
      </v-card>
    </v-app>

</template>

<script>
export default {
  name: 'loginForm',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>