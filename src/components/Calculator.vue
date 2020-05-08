<template >
  <section id="calculator-section" class="mt-32 font-sans font-light text-brown">
    <div class="mb-6">
      <h1 class="font-serif text-center text-xl">Kalkulaator.</h1>
      <img class="mx-auto" src="../assets/heading-line.svg" alt="Line under heading" />
    </div>
    <div class="lg:mb-24 sm:mb-8">
      <p
        class="tracking-wide text-center leading-8 sm:mx-auto sm:max-w-lg sm:text-lg"
      >Hindamaks naiste mitterahalist panust.</p>
    </div>
    <div class="container">
      <p
        class="font-bold font-sans mb-8 tracking-wide leading-6 sm:text-left lg:text-left leading-8"
      >Kokku oleksite teeninud: <span> {{total | currency}} </span></p>

      <div id="calc-container">
        <form class="w-full">
          <div class="flex flex-wrap -mx-3 mb-6">
            <div class="lg:order-1 md:order-1 order-3 lg:w-2/12 md:w-5/12 w-9/12 px-3 mb-6 md:mb-0">
              <input
                class="appearance-none block w-full bg-yellow-light shadow-md text-gray-700 text-center rounded py-3 px-4 mb-3 leading-8 focus:outline-none placeholder-brown"
                id="input-hours"
                v-model="item.hours"
                type="number"
                inputmode="numeric"
                placeholder="Sisesta tunnid"
              />
            </div>
            <div class="lg:order-2 md:order-2 order-1 w-full lg:w-4/12 md:w-7/12 px-3 mb-6 md:mb-0">
              <div class="relative">
                <select
                  class="block appearance-none w-full bg-yellow-light shadow-md text-brown py-3 px-4 pr-8 rounded focus:outline-none leading-8"
                  id="input-occupation"
                  v-model="item.occupation"
                >
                  <option v-for="(occupation, index) in occupations" :key="index" :value="occupation">{{occupation.name}}</option>
                </select>
                <div
                  class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 text-gray-700"
                >
                  <svg
                    class="fill-current h-4 w-4"
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 20 20"
                  >
                    <path
                      d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"
                    />
                  </svg>
                </div>
              </div>
            </div>
            <div
              class="lg:order-3 md:order-3 order-2 w-full lg:w-5/12 md:w-10/12 md:mt-8 mb-8 lg:mt-0 px-3"
            >
              <input
                class="appearance-none block w-full bg-yellow-light shadow-md text-brown rounded py-3 px-4 leading-8 focus:outline-none placeholder-brown"
                id="input-comments"
                v-model="item.comment"
                type="text"
                placeholder="Märkus"
              />
            </div>
            <div class="order-4 w-3/12 md:w-2/12 lg:w-1/12 px-3">
              <button
                id="input-btn"
                @click.prevent="add(item)"
                class="focus:outline-none float-right bg-green lg:mt-0 md:mt-8 rounded transform hover:-translate-y-1 hover:scale-110 shadow text-white flex justify-center items-center shadow-lg"
              >
                <svg
                  class="stroke-current"
                  width="27" height="27"
                  stroke-width="3"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path class="a" d="M13.5 1.5v24M25.5 13.5h-24" />
                </svg>
              </button>
            </div>
          </div>
        </form>
        <transition-group name="list" class="container">
           <div class= "w-full flex items-center border-t border-gray h-16 " v-for="(item,index) in budget" :key="index">
             <div class="md:w-1/12 w-2/12 text-center font-bold leading-10 overflow-hidden">{{item.hours}}h</div>
             <div class="md:w-3/12 w-5/12 text-center font-normal leading-10 overflow-hidden">{{item.occupation.name}}</div>
             <div class="md:w-5/12 w-0 hidden sm:block text-center leading-8 overflow-hidden">{{item.comment}}</div>
             <div class="sm:hidden" v-tooltip="item.comment"><InfoIcon class="h-6 w-6" /></div>
             <div class="md:w-2/12 w-3/12 text-center font-bold leading-10 overflow-hidden">{{(item.hours*(item.occupation.rate*1.654321)) | currency }}</div>
             <div class="md:w-1/12 w-2/12  text-center transform hover:-translate-y-1 hover:scale-110 px-2">
             <button id="delete-btn"
              @click="remove(index)"
              class="flex items-center justify-center text-white bg-red rounded h-10">
               <svg class="fill-current" xmlns="http://www.w3.org/2000/svg"
               width="17.154" 
               height="21.176">
               <path class="a" d="M.497 8.13c.08.083 2.486 12.546 2.486 12.546h9.3L15.655 8.13z"/>
               <path class="b" d="M3.219 10.758l1.681 8.1M7.993 10.878l.004 8.063M13.064 10.818l-2.18 7.98"/>
               <path class="a" d="M16.016 6.772L1.222 2.098S4.29.293 9.11 1.934a13.907 13.907 0 016.906 4.838z"/></svg>
             </button>
             </div>
           </div>
        </transition-group>
        <div>
          <p class="text-gray mt-12">* tunnipalk on võetud Eesti Statistikaametist.</p>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
import InfoIcon from './Info-icon';
export default {
  components: {
    InfoIcon
  },
  computed:{
    total(){
     if(this.budget.length) {return this.budget.reduce((acc,item)=>{
        return acc = acc + item.hours*(item.occupation.rate*1.654321)

      },0)}
      return 0
    }
  },
  data(){
    return{
      budget: [],
      occupations: [
        {name:"Lapsehoidja", rate:2.96},
        {name:"Ettelugeja", rate:4.33},
        {name:"Kokk", rate:4.52},
        {name:"Ettekandja", rate:4.62},
        {name:"Koristaja", rate:2.67},
        {name:"Nõudepesija", rate:2.69},
        {name:"Med.õde", rate:5.32},
        {name:"Hooldaja", rate:2.96},
        {name:"Nõustaja/Psühholoog", rate:5.32},
        {name:"Õpetaja", rate:5.84},
        {name:"Huvijuht", rate:4.33},
        {name:"Autojuht", rate:5.05},
        {name:"Logistik", rate:7.43},
        {name:"Ostleja", rate:3.50},
        {name:"Riiete pesija", rate:4.90},
        {name:"Õmbleja", rate:4.45},
        {name:"Juuksur", rate:3.53},
        {name:"Raamatupidaja", rate:5.03},
        {name:"Ehitaja", rate:5.13},
        {name:"Majahoidja", rate:2.67},
        {name:"Sisekujundaja", rate:7.22},
        {name:"IT-tugi", rate:4.47},
      ],
      item:{
        occupation:null,
        comment:null,
        hours:null,
      }
      }
  },
  methods:{
    add(item){
      if(this.item.hours === null || this.item.occupation === null) return;

      this.budget.push({
        occupation: item.occupation,
        comment: item.comment,
        hours: item.hours
      })

      this.clearFields();
    },
    remove(index){
      this.budget.splice(index,1)
    },
    clearFields() {
      for(let field in this.item) {
        this.item[field] = null
      }
    }
  },
  filters: {
    currency(amount){
      return `${amount.toFixed(2)} €`;
    }
  }
}
</script>

<style>
.container {
  width: 90%;
  max-width: 1088px;
  margin: auto;
  height: 100%;
}

button:active {
  transform: scale(0.95);
}

#input-btn {
  height: 56px;
  width: 70px;
}

#delete-btn {
  width: 50px;
}
.tooltip .tooltip-inner {
  background: #FFFAF0;
  color: black;
  border-radius: 5px;
  padding: 10px 20px;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
}
.list-item {
  display: inline-block;
  margin-right: 10px;
}
.list-enter-active, .list-leave-active {
  transition: all 1s;
}
.list-enter, .list-leave-to /* .list-leave-active below version 2.1.8 */ {
  opacity: 0;
  transform: translateY(30px);
}
</style>