<template>
    <div class="rules">
        <div class="Lang">
            <p>ID</p>
            <label class="switch float-right">
                <input type="checkbox" @click="en">
                <span class="slider round" ></span>
            </label>
            <p>EN</p>
        </div>
        <input
        @change="toggleTheme"
        id="checkbox"
        type="checkbox"
        class="switch-checkbox"
      />
      <label for="checkbox" class="switch-label">
        <span>🌙</span>
        <span>☀️</span>
        <div
          class="switch-toggle"
          :class="{ 'switch-toggle-checked': userTheme === 'dark-theme' }"
        ></div>
      </label>
        <h2>{{header}}</h2>
        <!-- <h5 v-for="rule in winRule">{{rule}}</h5> -->

        
    </div>
</template>

<script>
const win=[
  "Batu VS Kertas Pemenang Kertas",
  "Batu VS Gunting Pemenang Batu",
  "Kertas VS Gunting Gunting",
];

const rule =[
  {no:1,decs:"Anda dapat memilih "},
  {no:2,desc:"Computer akan memilih pilihan Acak Antara Batu, Gunting dan Kertas"}
]
    export default{
        name:'GameRules',
        data(){
            return {
                userTheme: "light-theme",
                rule:"ini halaman Rule",
                header: "Cara Bermain Batu Gunting Kertas",
                rules1: "Game ini adalah game User Melawan Computer",
                rules2: "User Memilih pilihan yang ingin dia pilih untuk Melawan Computer",
                rules3: "Pilihan yang disediakan adalah Batu, Gunting, Kertas",
                rules4: "Pilihan Computer akan Dipilih secara Random dari Batu Gunting Kertas",
                rules5: "Pemenang Pilihan adalah",
                winRule : win,
                winner: "Pemenang ketika mencapai Skor 5 Dahulu dari maksimal 9 ronde"
            }
        },
        methods:{
            en(){
              this.rule="this Rule page for Scissors Game",
              this.header= "How to Play Scissors Game"
              return this.rule1="what the"
                // rules1: "Game ini adalah game User Melawan Computer",
                // rules2: "User Memilih pilihan yang ingin dia pilih untuk Melawan Computer",
                // rules3: "Pilihan yang disediakan adalah Batu, Gunting, Kertas",
                // rules4: "Pilihan Computer akan Dipilih secara Random dari Batu Gunting Kertas",
                // rules5: "Pemenang Pilihan adalah",
                // winRule : win,
                // winner: "Pemenang ketika mencapai Skor 5 Dahulu dari maksimal 9 ronde"
            },
            setTheme(theme){
              localStorage.setItem("en",theme);
              this.userTheme = theme;
              document.documentElement.className = theme;
            }
        },
        mounted() {
          const initUserTheme = this.getMediaPreference();
          this.setTheme(iniUserTheme);
        },
        
    };
</script>

<style>
.Lang{
    display: flex;
}
.lang p{
    padding: 5px 10px 5px 10px;
}
.switch {
  position: relative;
  display: inline-block;
  width: 60px;
  height: 34px;
}

.switch input { 
  opacity: 0;
  width: 0;
  height: 0;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: .4s;
  transition: .4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: .4s;
  transition: .4s;
}

input:checked + .slider {
  background-color: #2196F3;
}

input:focus + .slider {
  box-shadow: 0 0 1px #2196F3;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

/* Rounded sliders */
.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}</style>