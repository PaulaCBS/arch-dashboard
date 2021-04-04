<template>  
  <div class="block">
    <h2 class='title'>EVENTOS</h2>
    <div class='graphic bar-chart'>
       <ul class='axis-y'>
         <li data-axisY='60'></li>
         <li data-axisY='45'></li>
         <li data-axisY='30'></li>
         <li data-axisY='15'></li>
         <li data-axisY='0'></li>
       </ul>
       <ul class='axis-x'>
         <li data-axisX='37'><i>2015</i></li>
         <li data-axisX='56'><i>2016</i></li>
         <li data-axisX='25'><i>2017</i></li>
         <li data-axisX='18'><i>2018</i></li>
         <li data-axisX='45'><i>2019</i></li>
         <li data-axisX='50'><i>2020</i></li>
         <li data-axisX='33'><i>2021</i></li>
       </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BarChart'  
}

</script>
<style scoped>
  ul {
    list-style-type: none;
  }
  h2 {
    font-size: 1.2rem;
    color: #312F2F;
  }
  .block {
    min-width: 19rem;
    height: 23.5rem;
    margin: 1rem 0;
    border-radius: 5px;
    background: #FFF;
    box-shadow: 
      0px 2px 4px -1px rgba(24, 39, 75, 0.12), 
      0px 4px 12px -2px rgba(24, 39, 75, 0.1);
    overflow: hidden;
  }
  .title {
    margin: 1rem 0 1.5rem 0;
    text-align: center;
  }
  .graphic {
    position: relative;
    width: 100%;
    height: 60%;
    font-size: 0.8rem;
    background: #312F2F;
    color: #FFF;
  }
  [class^='axis-'] {
    position: absolute;
    left: 0;
    bottom: 0rem;
    width: 100%;
    height: 80%;
  }
  .axis-x {
    height: 4rem;
    display: flex;
    align-items: center;
  }
  .axis-y li {
    height: 25%;
    border-top: 1px solid #777;
  }
  [data-axisY]:before {
    position: relative;
    content: attr(data-axisY);
    display: inline-block;
    width: 2rem;
    text-align: right;
    left: -2.5rem;
    top: -0.5rem;
  } 
  .bar-chart [class^='axis-'] {
    padding: 0 1rem 0.5rem 2rem;
    bottom: 1rem;
  }
  .bar-chart .axis-x {
    bottom: 0;
  }
  .bar-chart .axis-y li {
    height: 20%;
    border-top: 1px solid #FFF;
  }
  .bar-chart .axis-x li {
    position: relative;
    width: 14%;
  }
  .bar-chart .axis-x li i {
    transform: rotatez(-45deg) translatex(-0.2rem);
    transform-origin: 30% 60%;
    display: block;
  }
  .bar-chart .axis-x li:before {
    position: absolute;
    content: '';
    bottom: 1.9rem;
    width: 70%;
    right: 5%;
    box-shadow: 3px 0 rgba(0,0,0,.1), 3px -3px rgba(0,0,0,.1);
  }
  .bar-chart .axis-x li:nth-child(1):before {
    height: 570%;
    background: #E64C65;  
  }
  .bar-chart .axis-x li:nth-child(2):before {
    height: 900%;
    background: #11A8AB;  
  }
  .bar-chart .axis-x li:nth-child(3):before {
    height: 400%;
    background: #FCB150;  
  }
  .bar-chart .axis-x li:nth-child(4):before {
    height: 290%;
    background: #4FC4F6;  
  }
  .bar-chart .axis-x li:nth-child(5):before {
    height: 720%;
    background: #FFED0D;  
  }
  .bar-chart .axis-x li:nth-child(6):before {
    height: 820%;
    background: #F46FDA;  
  }
  .bar-chart .axis-x li:nth-child(7):before {
    height: 520%;
    background: #15BFCC;  
  }
</style>