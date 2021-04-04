<template>
  <div class="block"> 
    <h2 class="title">SERVIÇOS</h2>
    <div class="pie-chart">
      <div id="slice1" class="slice">
        <div class="service-type mobile" data-rel="21"></div>
      </div>
      <div id="slice2" class="slice">
        <div class="service-type mac" data-rel="39"></div>
      </div>
      <div id="slice3" class="slice">
        <div class="service-type win" data-rel="31"></div>
      </div>
      <div id="slice4" class="slice">
        <div class="service-type linux" data-rel="9"></div>
      </div>
      <p class="center-date">
        ABRIL<br><span class="scnd-font-color">2021</span>
      </p>        
    </div>
    <ul class="service-percentages horizontal-list">
      <li>
        <p class="mobile service scnd-font-color">Mobile</p>
        <p class="service-percentage">21%</p>
      </li>
      <li>
        <p class="mac service scnd-font-color">Mac</p>
        <p class="service-percentage">39%</p>
      </li>
      <li>
        <p class="linux service scnd-font-color">Linux</p>
        <p class="service-percentage">9%</p>
      </li>
      <li>
        <p class="win service scnd-font-color">Win</p>
        <p class="service-percentage">31%</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'PieChart'
}
</script>

<style scoped>
  .block {
    display: flex;
    flex-flow: column nowrap;
    justify-content: space-between;
    align-items: center;
    width: 18.5rem;
    height: 23.5rem;
    margin: 1rem 0;
    background: #FFF;
    border-radius: 0.2rem;
    box-shadow: 
      0px 2px 4px -1px rgba(24, 39, 75, 0.12), 
      0px 4px 12px -2px rgba(24, 39, 75, 0.1);
    overflow: hidden;
  }
  ul {
    list-style-type: none;
  }
  p {
    font-size: 0.8rem;
  }
  h2{
    font-size: 1.2rem;
    color: #312F2F;
  }
  p, span{
    color: #fff;
  }
  .scnd-font-color {
    color: #F1D77E;
  }
  .title {
    margin: 1.2rem 0;
    text-align: center;
  }
  .horizontal-list {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .service-percentages li {
    width: 4.6rem;
    text-align: center;					
    border-left: 1px solid #555;
    background: #312F2F;
  }
  .service {
    padding: 0.7rem 0 0.5rem 0;
    font-size: 0.9rem;		
  }
  .service.mobile {
    border-top: 4px solid #e64c65;
  }
  .service.mac {
    border-top: 4px solid #11a8ab;
  }
  .service.linux {
    border-top: 4px solid #fcb150;
  }
  .service.win {
    border-top: 4px solid #4fc4f6;
  }
  .service-percentage {
    margin-bottom: 0.7rem;
    font-size: 1.1rem;
  }
  .pie-chart {
    position: relative;
    width: 12.5rem;
    height: 12.5rem;
    margin-bottom: 2rem;
    border-radius: 100%
  }
  .center-date {
    position: absolute;
    top:0;left:0;bottom:0;right:0;
    width: 8.5rem;
    height: 8.5rem;
    margin: auto;
    padding: 1.7rem 0;
    border-radius: 50%;
    text-align: center;
    font-size: 1.6rem;
    line-height: 2.5rem;
    background: #312F2F;
  }
  .slice {
    position: absolute;
    clip: rect(0px, 200px, 200px, 100px);
    width: 100%;
    height: 100%;
    border-radius: 50%;
  }
  .service-type {
    position: absolute;
    clip: rect(0px, 100px, 200px, 0px);
    height: 100%;
    width: 100%;
    border-radius: 50%;
  }
  #slice1 {
    transform: rotate(0deg);
  }
  #slice1 .service-type {
    transform: rotate(76deg);
    background-color: #E64C65;
  }
  #slice2 {
    transform: rotate(76deg);
  }
  #slice2 .service-type {
    transform: rotate(140deg);
    background-color: #11A8AB;
  }
  #slice3 {
    transform: rotate(215deg);
  }
  #slice3 .service-type {
    transform: rotate(113deg);
    background-color: #4FC4F6;
  }
  #slice4 {
    transform:rotate(-32deg);
  }
  #slice4 .service-type {
    transform: rotate(32deg);
    background-color: #FCB150;
  }
</style>