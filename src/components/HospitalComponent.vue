<template>

  <div class="container">
    <h1>Hospitals</h1>
    <table class="table table-striped">
      <thead>
        <tr>
          <th>Ttile</th>
          <th>Dean</th>
          <th>No of Doctors</th>
          <th>No of Patients</th>
          <th>Start Date</th>
          <th>Revenue</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(hospital, index) in hospitals"
        v-bind:item="hospital"
        v-bind:index="index"
        v-bind:key="hospital._id">
          <td>{{ hospital.title }}</td>
          <td>{{ hospital.dean }}</td>
          <td>{{ hospital.doctors }}</td>
          <td>{{ hospital.patients }}</td>
          <td>{{ hospital.startDate }}</td>
          <td>{{ hospital.revenue }}</td>
        </tr>
      </tbody>
    </table>
    <br><br><br>
  </div>
</template>

<script>
//import HospitalService from '../HospitalService.js';

export default {
  name: "HospitalComponent",
  data() {
    return {
      hospitals: [],
      error: "",
      text: "",
    };
  },
  methods: {
    async fetchHospitals() {
      const response = await fetch("https://polar-mountain-11158.herokuapp.com/api");
      const data = await response.json();
      //console.log(data);
      return data;
    },
  },
  async created() {
    try {
      this.hospitals = await this.fetchHospitals();
    } catch (err) {
      this.error = err.message;
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div.container {
  max-width: 800px;
  margin: 0 auto;
}

p.error {
  border: 1px solid rgba(203, 86, 86, 0.661);
  background-origin: rgba(210, 27, 27, 0.065);
}

div.hospital {
  position: relative;
  border: 1px solid rgb(95, 61, 221);
  background-color: rgb(232, 235, 243);
  padding: 10px 10px 30px 10px;
  margin-bottom: 15px;
}

p.text {
  font-size: 22px;
  font-weight: 700;
  margin-bottom: 0;
}

.table {
    border: solid 1px #DDEEEE;
    border-collapse: collapse;
    border-spacing: 0;
    font: normal 13px Arial, sans-serif;
}
.table thead th {
    background-color: #DDEFEF;
    border: solid 1px #DDEEEE;
    color: #336B6B;
    padding: 10px;
    text-align: left;
    text-shadow: 1px 1px 1px #fff;
}
.table tbody td {
    border: solid 1px #DDEEEE;
    color: #333;
    padding: 10px;
    text-shadow: 1px 1px 1px #fff;
}
</style>
