<script>
import { initializeApp } from "firebase/app";
import { getDatabase, ref, set, onValue, update, remove, get, push, child } from "https://www.gstatic.com/firebasejs/9.17.1/firebase-database.js";
// TODO: Replace the following with your app's Firebase project configuration
// See: https://firebase.google.com/docs/web/learn-more#config-object
const firebaseConfig = {
  // ...
  // The value of `databaseURL` depends on the location of the database
  databaseURL: "https://hakkl-gdsc-default-rtdb.firebaseio.com",
};
// Initialize Firebase
const app = initializeApp(firebaseConfig); 

// Initialize Realtime Database and get a reference to the service
const database = getDatabase(app);

console.log("DATABASE" + database);
const covidData = ref(database, "covid");

export default {
  data() {
    return {
      NowVaccinated: '50',
    }
  }
} 


</script>

<template>
  <main class="relative flex flex-wrap items-center justify-between py-5 pb-12 bg-white text-black">
    <div class="container flex-wrap mx-auto px-32 items-center">
      <div>
        <h1 class="mainHeading py-3">COVID-19 Vaccination Overview</h1>
        <p class="mainParagraph">
          Currently,
          <b>{{ NowVaccinated }}%</b>
          of the Philippine population has received at
          least one dose of a COVID-19 vaccine.
          <b>{{ individualDoses }} million</b>
          doses have been administered nationally, and
          <b>{{ dailyDosesCommas }}</b>
          are now administered each day. Meanwhile,
          <b>{{ digosVaccinationPercentage }}%</b>
          of the
          Digoseño population in Digos City has received at least one dose of
          COVID-19 vaccine, and a total of
          <b>{{ digosTotalVaccinesCommas }}</b> doses were administered.
        </p>
      </div>
      <div class="py-5">
        <img src="https://svgshare.com/i/g7k.svg" alt />
      </div>
    </div>
  </main>
</template>

<style scoped>
</style>