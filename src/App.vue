 <template>
    <div class="navbar">
        <ul class="nav-item">
            <li><router-link to="/">Start Game</router-link></li>
            <li><a href="/">home</a></li>
            <li><a href="/rules">rules</a></li>
            <li><router-link to="/rules">Rules</router-link></li>
        </ul>
    </div>
    <router-view/>
</template>

<script>
export default{};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.navbar{
  margin: 50px 100px 50px;
  /* background-color:#2c3e50; */
  display: flex;
  justify-content: center;
  align-items: center;
}
.nav-item{
  display: flex;
  margin-left:-100px;
}
.nav-item li{
  list-style: none;
  display: block;
  /* color: white; */
  text-transform: uppercase;
  font-style:initial;
  text-decoration: none;
}
.nav-item li+li:before{
  content: "|";
  padding: 0;
  margin: 0 40px;
  position: relative;
  top:-2px;
  color:#2c3e50;
}
</style>
