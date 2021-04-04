<template>
  <div class="block">
      <div class="line-chart">
        <div class='graphic'>
          <ul class='axis-y'>
            <li data-marker='30'></li>
            <li data-marker='20'></li>
            <li data-marker='10'></li>
            <li data-marker='0'></li>
          </ul>
          <ul class='axis-x'>
            <li>JAN</li>
            <li>FEV</li>
            <li>MAR</li>
          </ul>
          <span data-values='25'>
          <span data-values='8'>
          <span data-values='13'>
          <span data-values='5'>   
          <span data-values='23'>   
          <span data-values='12'>
          <span data-values='15'>
          </span></span></span></span></span></span></span>
        </div>
      </div>
      <ul class="time-lenght horizontal-list">
          <li class="time-lenght-btn">Semana</li>
          <li class="time-lenght-btn">Mês</li>
          <li class="time-lenght-btn">Ano</li>
      </ul>
      <ul class="month-data">
          <li class="month-data-info">
              <p>JAN<span class="scnd-font-color"> 2021</span></p>
              <p>21%</p>
          </li>
          <li class="month-data-info">
              <p>FEV<span class="scnd-font-color"> 2021</span></p>
              <p>48%</p>
          </li>
          <li class="month-data-info">
              <p>MAR<span class="scnd-font-color"> 2021</span></p>
              <p>35%</p>
          </li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'LinearChart'
}
</script>

<style scoped>
  ul {
    list-style-type: none;
  }
  p{
    color: #312F2F;
  }
  .scnd-font-color {
		color: #777;
	}
  .horizontal-list {
    display: flex;
    align-items: center;
    justify-content: center;
    list-style-type: none;
  }
  .block {
    display: flex;
    flex-flow: column nowrap;
    min-width: 19rem;
    height: 23.5rem;
    margin: 1rem 0;
    background: #FFF;
    border-radius: 0.2rem;
    box-shadow: 
      0px 2px 4px -1px rgba(24, 39, 75, 0.12), 
      0px 4px 12px -2px rgba(24, 39, 75, 0.1);
    overflow: hidden;
  }
  .line-chart {
    height: 13rem;
    background: #312F2F;
  }
  .time-lenght {
    padding: 1rem 0;
  }
  .time-lenght-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 5rem;
    padding: 0.4rem 0;
    margin: 0 0.2rem;
    border-radius: 0.2rem;
    font-size: 0.8rem;
    text-align: center;
    background: #F1D77E;
  }
  .time-lenght-btn:hover {
    text-decoration: none;
    background: #D79D39;
  }
  .month-data {
    padding: 0 2rem;            
    font-size: 1rem;
  }
  .month-data-info {
    display: flex;
    justify-content: space-between;
    margin: 0.5rem 0;

  }
  .month-data p:last-child {
    font-weight: 500;
  }
  .graphic {
    position: relative;
    width: 100%;
    height: 100%;
    font-size: 0.8rem;
    color: #FFF;
  }
  .graphic span {
    position: absolute;
    bottom: 3rem;
    left: 2rem;
    height: 0;
    border-top: 2px solid #FFF;
    transform-origin: left center;
  }
  .graphic span > span {
    left: 100%; 
    bottom: 0;
  }
  [data-values='25'] {width: 75px; transform: rotate(-45deg);}
  [data-values='8'] {width: 24px; transform: rotate(65deg);}
  [data-values='13'] {width: 39px; transform: rotate(-45deg);}
  [data-values='5'] {width: 15px; transform: rotate(50deg);}
  [data-values='23'] {width: 69px; transform: rotate(-70deg);}
  [data-values='12'] {width: 36px; transform: rotate(75deg);}
  [data-values='15'] {width: 45px; transform: rotate(-45deg);}

  [data-values]:before {
    content: '';
    position: absolute;
    display: block;
    right: -4px;
    bottom: -3px;
    padding: 4px;
    background: #FFF;
    border-radius: 50%;
  }
  [data-values='23']:after {
    content: '+' attr(data-values) '%';
    position: absolute;
    right: -2.7rem;
    top: -1.7rem;
    padding: 0.3rem 0.5rem;
    border-radius: 0.5rem;
    transform: rotate(45deg);
    background: #F1D77E;
    color: #312F2F;
  }
  [class^='axis-'] {
    position: absolute;
    left: 0;
    bottom: 0rem;
    width: 100%;
    height: 80%;
    padding: 1rem 1rem 0 2rem;
  }
  .axis-x {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    height: 2.5rem;
    margin: 0.4rem 0;
    text-align: center;
  }
  .axis-y li {
    height: 25%;
    border-top: 1px solid #777;
  }
  [data-marker]:before {
    position: relative;
    content: attr(data-marker);
    display: inline-block;
    left: -2.5rem;
    top: -.5rem;
    width: 2rem;
    text-align: right;
  } 
</style>