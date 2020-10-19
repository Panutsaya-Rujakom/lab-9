<template>
  <div id="bg">
    <div>
      
      <b-navbar toggleable="lg" type="dark" variant="Light">
        <b-navbar-toggle target="nav-collapse"  />
        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav class="ml-auto">
            <b-navbar-nav>
              <b-nav-item  to="/">
                <b id="aa">Home</b>
              </b-nav-item>
            </b-navbar-nav>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>
    <Nuxt />
    <br><br><br><br><br>
  </div>
</template>
<script>
export default {}
</script>
<style>
#bg {
  background-image: url(https://www.shutterstock.com/th/blog/wp-content/uploads/sites/16/2018/09/13.jpg?w=750);
  background-size: cover;
}
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #110ef7;
  color: #350af3;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: rgb(0, 0, 0);
  background-color: #1f08f0;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: rgb(0, 0, 0);
  background-color: #047bfa;
}
#aa{
  color: rgb(8, 8, 8);
}
</style>
