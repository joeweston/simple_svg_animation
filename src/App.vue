<template>
  <div id="app">
    <div class="normal-container">
      <h1>Vue Svg Animation</h1>
      <p>This is an svg animation, using two-way binding on individual elements of an inline svg.</p>
      <p>Click the image to see animation.</p>
      <svg @click="changePattern" width="400px" height="400px" version="1.1" viewBox="0 0 264.58333 264.58335" xmlns="http://www.w3.org/2000/svg">
       <g transform="translate(0 -32.417)">
        <circle :cx="data.cx1" :cy="data.cy1" r="13.229" :style="color1"/>
        <circle :cx="data.cx2" :cy="data.cy2" r="13.229" :style="color1"/>
        <circle :cx="data.cx3" :cy="data.cy3" r="13.229" :style="color1"/>
        <circle :cx="data.cx4" :cy="data.cy4" r="13.229" :style="color1"/>
        <circle :cx="data.cx5" :cy="data.cy5" r="13.229" :style="color1"/>
        <circle :cx="data.cx6" :cy="data.cy6" r="13.229" :style="color1"/>
        <circle :cx="data.cx7" :cy="data.cy7" r="6.6146" :style="color1"/>
        <circle :cx="data.cx8" :cy="data.cy8" r="6.6146" :style="color1"/>
        <circle :cx="data.cx9" :cy="data.cy9" r="6.6146" :style="color1"/>
        <circle :cx="data.cx10" :cy="data.cy10" r="6.6146" :style="color1"/>
        <circle :cx="data.cx11" :cy="data.cy11" r="6.6146" :style="color1"/>
        <circle :cx="data.cx12" :cy="data.cy12" r="6.6146" :style="color1"/>
        <circle :cx="data.cx13" :cy="data.cy13" r="6.6146" :style="color1"/>
        <circle :cx="data.cx14" :cy="data.cy14" r="6.6146" :style="color1"/>
        <circle transform="scale(-1)" :cx="data.cx15" :cy="data.cy15" r="13.229" :style="color2"/>
        <circle transform="scale(-1)" :cx="data.cx16" :cy="data.cy16" r="13.229" :style="color2"/>
        <circle transform="scale(-1)" :cx="data.cx17" :cy="data.cy17" r="13.229" :style="color2"/>
        <circle transform="scale(-1)" :cx="data.cx18" :cy="data.cy18" r="13.229" :style="color2"/>
        <circle transform="scale(-1)" :cx="data.cx19" :cy="data.cy19" r="13.229" :style="color2"/>
        <circle transform="scale(-1)" :cx="data.cx20" :cy="data.cy20" r="13.229" :style="color2"/>
        <circle transform="scale(-1)" :cx="data.cx21" :cy="data.cy21" r="6.6146" :style="color2"/>
        <circle transform="scale(-1)" :cx="data.cx22" :cy="data.cy22" r="6.6146" :style="color2"/>
        <circle transform="scale(-1)" :cx="data.cx23" :cy="data.cy23" r="6.6146" :style="color2"/>
        <circle transform="scale(-1)" :cx="data.cx24" :cy="data.cy24" r="6.6146" :style="color2"/>
        <circle transform="scale(-1)" :cx="data.cx25" :cy="data.cy25" r="6.6146" :style="color2"/>
        <circle transform="scale(-1)" :cx="data.cx26" :cy="data.cy26" r="6.6146" :style="color2"/>
        <circle transform="scale(-1)" :cx="data.cx27" :cy="data.cy27" r="6.6146" :style="color2"/>
        <circle transform="scale(-1)" :cx="data.cx28" :cy="data.cy28" r="6.6146" :style="color2"/>
       </g>
      </svg>
      <p>By changing data bound to svg properies and adding the css propety 'transition' - a smooth tranition can occur. </p>
    <button @click="showCode">{{codeShown?"Hide Code":"Show Code (simplified)"}}</button>
    </div>
    <div v-if="codeShown">
      <div class="normal-container"><p>This is the code for animating the position of one element of my SVG (in the context of a vue component using the vue-cli)</p></div>
      <pre><code>{{code}}</code></pre>
    </div>
  </div>
</template>

<script>

const DATA1 = {
cx1:"44.223" ,cy1:"66.812"
,cx2:"75.001" ,cy2:"106.88" 
,cx3:"50.271" ,cy3:"236.15"
,cx4:"72.085" ,cy4:"172.65" 
,cx5:"106.21" ,cy5:"65.301" 
,cx6:"74.137" ,cy6:"66.057" 
,cx7:"58.775" ,cy7:"84.766" 
,cx8:"85.234" ,cy8:"147.51" 
,cx9:"70.601" ,cy9:"197.4" 
,cx10:"92.793" ,cy10:"86.278" 
,cx11:"31.507" ,cy11:"254.86" 
,cx12:"63.149" ,cy12:"215.55" 
,cx13:"65.579" ,cy13:"147.51" 
,cx14:"77.296" ,cy14:"131.64" 
,cx15:"-221.82" ,cy15:"-263.36" 
,cx16:"-191.04" ,cy16:"-223.29" 
,cx17:"-215.77" ,cy17:"-94.027" 
,cx18:"-193.96" ,cy18:"-157.53" 
,cx19:"-159.83" ,cy19:"-264.87" 
,cx20:"-191.9" ,cy20:"-264.12" 
,cx21:"-207.27" ,cy21:"-245.41" 
,cx22:"-180.81" ,cy22:"-182.66" 
,cx23:"-195.44" ,cy23:"-132.77" 
,cx24:"-173.25" ,cy24:"-243.89" 
,cx25:"-234.53" ,cy25:"-75.317" 
,cx26:"-202.89" ,cy26:"-114.63" 
,cx27:"-200.46" ,cy27:"-182.66" 
,cx28:"-188.75" ,cy28:"-198.54" 
}
const DATA2 = {
  cx1:"77.485",cy1:"153.75",
  cx2:"155.13",cy2:"219.51",
  cx3:"114.53",cy3:"124.26",
  cx4:"125.76",cy4:"181.72",
  cx5:"123.6",cy5:"228.59",
  cx6:"179.97",cy6:"184.74",
  cx7:"138.91",cy7:"93.838",
  cx8:"99.597",cy8:"179.26",
  cx9:"157.54",cy9:"103.67",
  cx10:"95.817",cy10:"101.4",
  cx11:"175.89",cy11:"160.36",
  cx12:"184.1",cy12:"121.81",
  cx13:"76.162",cy13:"211.01",
  cx14:"135.5",cy14:"142.22",
  cx15:"-84.235",cy15:"-123.51",
  cx16:"-149.46",cy16:"-161.31",
  cx17:"-109.18",cy17:"-155.26",
  cx18:"-100.97",cy18:"-205.91",
  cx19:"-75.163",cy19:"-183.99",
  cx20:"-161.67",cy20:"-131.07",
  cx21:"-119.58",cy21:"-97.996",
  cx22:"-133.18",cy22:"-206.1",
  cx23:"-190.9",cy23:"-145.62",
  cx24:"-96.141",cy24:"-229.53",
  cx25:"-197.49",cy25:"-163.01",
  cx26:"-139.39",cy26:"-115.38",
  cx27:"-155.86",cy27:"-191.73",
  cx28:"-181.19",cy28:"-209.88",
}



export default {
  data(){
    return {
      firstPattern: true,
      data:DATA1,
      color1: "fill:#ff2a2a",
      color2: "fill:#0f0",
      codeShown: false,
      code: 
`<template>
  <div>
    <svg @click="changePattern" width="400px" height="400px" viewBox="0 0 264.58333 264.58335">
      <g transform="translate(0 -32.417)">
        <circle :cx="data.cx1" :cy="data.cy1" r="13.229" :style=""fill:#ff2a2a"/>
      <g>
    </svg>
  </div>
</template>

<script>

const DATA1 = {
  cx1:"44.223", cy1:"66.812"
}
const DATA2 = {
  cx1:"77.485", cy1:"153.75"
}
export default {
  data(){
    return {
      firstPattern: true,
      data:DATA1
    }
  }
methods:{
    changePattern(){
      if (this.firstPattern){
        this.data = DATA2;
      } else {
        this.data = DATA1;
      }
      this.firstPattern = !this.firstPattern;
    }
  }

<\/script>

<style lang="scss" scoped>

circle{
  transition: all 5s;
}

</style>`
    };
  },
  methods:{
    changePattern(){
      if (this.firstPattern){
        this.data = DATA2;
        [this.color1, this.color2] = ["fill:cyan", "fill:yellow"];
      } else {
        this.data = DATA1;
        [this.color1, this.color2] = ["fill:#ff2a2a", "fill:#0f0"];
      }
      this.firstPattern = !this.firstPattern;
    },
    showCode(){
      this.codeShown = !this.codeShown;
    }


  }
}
</script>

<style lang="scss">
@import './assets/reset';
html { margin-left: calc(100vw - 100%); } //scrollbar flicker hack
body{
  font-family: Arial, Helvetica, sans-serif;
  margin: 40px 0;
}

pre code{
  font-family: "Lucida Console", Monaco, monospace;
  font-size: 12px;
}
pre{
  max-width: 740px;
  padding: 10px;
  margin: 0 auto;
  background-color:#ded;
  border-radius: 20px;
}
h1{
  font-size: 40px;
  line-height: 60px;
}
button{
  margin: 5px 0;
  font-size: 20px;
  border-radius: 5px;
}
p{
  font-size: 20px;
  line-height: 30px;
  margin: 10px;
}
svg{
  margin: 10px 0 30px;
  cursor: pointer;
  border: 3px solid black;
  border-radius: 20px;
}
circle{
  transition: all 5s;
}
.normal-container{
  margin: 0 auto;
  display:flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  width: 600px;
}

</style>

