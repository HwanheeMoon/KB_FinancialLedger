<script setup>
import Calendar from "./components/Calendar.vue"
</script>

<template>
  <div class="financial-summary">
    <section class="summary-content">
      <article class="summary-box">
        <div class="chart-image-secondary">
          <Calendar></Calendar>
        </div>
      </article>
    </section>
    <aside class="add-button">
      <button aria-label="Add new entry">+</button>
    </aside>
  </div>
</template>
<style scoped>
.financial-summary {
  background-color: #f8f8f8;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-bottom: 37px;
}


.summary-content {
  align-self: center;
  z-index: 10;
  display: flex;
  margin-top: -19px;
  width: 100%;
  max-width: 1022px;
  align-items: center;
  gap: 20px;
}

@media (max-width: 991px) {
  .summary-content {
    max-width: 100%;
    max-height: 100%;
    flex-wrap: wrap;
    padding : 0;
  }
}

.summary-box {
  border-radius: 30px;
  box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.62);
  background-color: #faebcd;
  align-self: start;
  display: flex;
  flex-direction: column;
  font-weight: 700;
  flex-grow: 1;
  flex-basis: 0;
  width: fit-content;
  padding: 27px 80px 80px;
}

@media (max-width: 991px) {
  .summary-box {
    max-width: 100%;
    padding: 30px 20px;
  }
}

.income-expense {
  display: flex;
  gap: 20px;
  margin: 0 17px;
}



.income,
.expense {
  align-self: start;
  font-family: Inter, sans-serif;
  font-size: 11px;
  white-space: nowrap;
}

@media (max-width: 991px) {

  .income,
  .expense {
    white-space: initial;
  }
}

.income {
  color: #6293ce;
}

.expense {
  color: #f66464;
}

.total {
  color: #434343;
  font-family: Inter, sans-serif;
  font-size: 14px;
  flex-grow: 1;
  flex-basis: auto;
}

.chart-image,
.chart-image-secondary {
  aspect-ratio: 1.47;
  object-fit: auto;
  object-position: center;
  width: 100%;
  align-self: center;
  margin: 6px 17px 0;

}


.chart-image {
  aspect-ratio: 20;
  box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.83);
}

.chart-image-secondary {
  box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.59);
  border: 1px solid rgba(255, 255, 255, 1);
}

.add-button {
  align-self: end;
  display: flex;
  margin-top: 552px;
  flex-direction: column;
  font-size: 64px;
  color: #f8f8f8;
  font-weight: 500;
  white-space: nowrap;
  line-height: 150%;
  justify-content: center;
}

@media (max-width: 991px) {
  .add-button {
    margin-top: 40px;
    font-size: 40px;
    white-space: initial;
  }
}

.add-button button {
  text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  font-family: Inter, sans-serif;
  filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
  background-color: #f2b74e;
  border-radius: 50%;
  align-items: center;
  justify-content: center;
  width: 90px;
  height: 90px;
  padding: 0 25px;
}

@media (max-width: 991px) {
  .add-button button {
    font-size: 40px;
    padding-left: 20px;
    white-space: initial;
  }
}
</style>