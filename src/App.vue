 <template>
 <div class="container">
  <div class="row mt-5">
    <div class="col-5">
      <GameSection></GameSection>
    </div>
    <div class="col-7" >
      <GameRules></GameRules>
    </div>
  </div>
 </div>
</template>

<script>
import GameSection from "./components/Game"
import GameRules from "./components/Rules" 

export default{
  name:'app',
  components:{
    GameSection,
    GameRules
  }
};

</script>

<style>
body{
  font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}
</style>

