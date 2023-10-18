<template>
  <div class="container mt-4"> 
    <div class="row">
      <div class="col-sm-6 mx-auto">
        <form class="p-4" @submit="saveData">
          <div class="form-group">
            <label for="citySelect">Город</label>
            <select class="form-control" id="citySelect" v-model="selectedCity" required>
              <option v-for="city in cities" :key="city"> {{ city }}</option>
            </select>
          </div>

          <div class="form-group">
            <label for="facilitySelect">Цех</label>
            <select class="form-control" id="facilitySelect" v-model="selectedFacility" required>
              <option v-for="facility in filteredFacilities" :key="facility.name"> {{ facility.name }}</option>
            </select>
          </div>

          <div class="form-group">
            <label for="employeeSelect">Сотрудник</label>
            <select class="form-control" id="employeeSelect" v-model="selectedEmployee" required>
              <option v-for="employee in filteredEmployees" :key="employee.id"> {{ employee.name }}</option>
            </select>
          </div>

          <div class="form-group">
            <label for="brigadeSelect">Бригада</label>
            <select class="form-control" id="brigadeSelect" v-model="selectedBrigade" required>
              <option v-for="brigade in brigades" :key="brigade"> {{ brigade }}</option>
            </select>
          </div>

          <div class="form-group">
            <label for="shiftSelect">Смена</label>
            <select class="form-control" id="shiftSelect" v-model="selectedShift" required>
              <option v-for="shift in shifts" :key="shift"> {{ shift }}</option>
            </select>
          </div>

          <button type="submit" class="btn btn-primary">Сохранить</button>
        </form>
      </div>
    </div>
  </div>
  
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      selectedCity: null, 
      selectedFacility: null,
      selectedEmployee: null,
      selectedBrigade: null,
      selectedShift: null,

      cities: ['Москва', 'Самара', 'Казань'],

      facilities: [
        { name: 'Цех1', city: 'Москва' },

        { name: 'Цех2', city: 'Москва' },

        { name: 'Цех3', city: 'Самара' },
        
        { name: 'Цех4', city: 'Казань' },
      ],

      employees: [
        {id: '1', name: 'Иванов Иван Иванович', facility: 'Цех1'},

        {id: '2', name: 'Петров Петр Петрович', facility: 'Цех2'},
        
        {id: '3', name: 'Соколов Ян Владимирович', facility: 'Цех2'},

        {id: '4', name: 'Сидоров Михаил Федорович', facility: 'Цех3'},

        {id: '5', name: 'Назаров Виктор Петрович', facility: 'Цех4'},
      ],

      brigades: ['1 бригада', '2 бригада'],

      shifts: ['8:00 - 20:00', '20:00 - 8:00'],

    }
  },
  computed: {
    filteredFacilities() {
      return this.facilities.filter(item => item.city === this.selectedCity);
    },

    filteredEmployees() {
      return this.employees.filter(item => item.facility === this.selectedFacility);
    }
  },

  watch: {
    selectedCity() {
      this.selectedFacility = null;
    }
  }, 

  methods: {
    saveData() {
      const formData = this.getFormdata();
      document.cookie = JSON.stringify(formData);
      alert(document.cookie);
    },

    getFormdata() {
      return { city: this.selectedCity, facility: this.selectedFacility, employee: this.selectedEmployee, brigade: this.selectedBrigade, shift: this.selectedShift };
    },
  },

}
</script>



<style>
form {
  border: 1px solid #2c3e50;
  border-radius: 5px;
  background-color: #f3f3f3;
}

label {
  display: flex;
}

.btn-primary {
  background-color: coral;
  border: 0px;
}

.btn:hover {
  background-color: rgb(255, 103, 47);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
