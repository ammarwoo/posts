<script>

import{ ref,onMounted } from "vue";

let prayerTime=ref([])

onMounted(async function(){

  let response=await fetch('https://www.e-solat.gov.my/index.php?r=esolatApi/TakwimSolat&period=today&zone=WLY01')
  let data=await response.json()
  prayerTimes.value=data.prayerTime
  console.log(data.prayerTime)

}


)
</script>

<tbody>
  
</tbody>
<template>

  <table>
    <thead>
      <th>hijri</th>
      <th>date</th>
      <th>day</th>
      <th>imsak</th>
      <th>fajr</th>
      <th>syuruk</th>
      <th>dhuhr</th>
      <th>asr</th>
      <th>maghrib</th>
      <th>isha</th>
    </thead>

     <div v-for="x in prayerTimes">
      <p class="text-xl">{{x.fajr}}</p>
      <p class="text-xl">{{x.dhuhr}}</p>
      <p class="text-xl">{{x.asr}}</p>
      <p class="text-xl">{{x.maghrib}}</p>
      <p class="text-xl">{{x.isha}}</p>

     </div>

     <tr>
       <td>1446-04-23</td>
        <td>26-Oct-2024</td>
        <td>Saturday</td>
        <td>05:38:00</td>
        <td>05:48:00</td>
        <td>06:56:00</td>
        <td>06:56:00</td>
        <td>16:19:00</td>
        <td>18:59:00</td>
        <td>20:09:00</td>
     </tr>
  </table>
  
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
