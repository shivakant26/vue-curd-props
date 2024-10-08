<script setup>
import { ref, reactive } from 'vue';

// Form data reactive state
const formData = reactive({
  employeeName: "",
  employeeSalary: "",
  location: "",
})

// Employees data array
const data = reactive([]);

// Ref to store current edited item index
const storedId = ref(null);

// Locations dropdown options
const Rular = reactive([
  { label: "mahari", value: "mahari" },
  { label: "dol", value: "dol" },
  { label: "mou", value: "mou" },
  { label: "padari", value: "padari" },
])

// Handle form submission
function handleFormSubmit() {
  if (storedId.value !== null) {
    data[storedId.value] = { ...formData };
    storedId.value = null;
  } else {
    data.push({ ...formData });
  }

  // Reset form data
  formData.employeeName = "";
  formData.employeeSalary = "";
  formData.location = "";
}

// Handle delete
function handleDelete(index) {
  data.splice(index, 1);
}

// Handle edit
function handleEdit(index) {
  const item = data[index];
  formData.employeeName = item.employeeName;
  formData.employeeSalary = item.employeeSalary;
  formData.location = item.location;
  storedId.value = index;
}
</script>

<template>
  <main>
    <div class="home-page">
      <div class="center-wr">
        <div class="page-container">
          <!-- Form Section -->
          <div class="form-section w-50">
            <h2>{{ storedId !== null ? "Update Employee" : "Add Employee" }}</h2>
            <form @submit.prevent="handleFormSubmit">
              <div class="form-field">
                <input type="text" v-model="formData.employeeName" placeholder="Enter Emp Name" />
              </div>
              <div class="form-field">
                <input type="text" v-model="formData.employeeSalary" placeholder="Enter Emp Salary" />
              </div>
              <div class="form-field">
                <select v-model="formData.location">
                  <option value="none">---None---</option>
                  <option v-for="rular in Rular" :key="rular.value" :value="rular.value">
                    {{ rular.label }}
                  </option>
                </select>
              </div>
              <div class="form-field">
                <button type="submit" class="create-btn">
                  {{ storedId !== null ? "Update Employee" : "Create Employee" }}
                </button>
              </div>
            </form>
          </div>

          <!-- Table Section -->
          <div class="table-section w-50">
            <h2>Employee Table</h2>
            <table>
              <thead>
                <tr>
                  <th>Index</th>
                  <th>Employee Name</th>
                  <th>Employee Salary</th>
                  <th>Employee Location</th>
                  <th>Action</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="(item, index) in data" :key="index">
                  <td>{{ index }}</td>
                  <td>{{ item.employeeName }}</td>
                  <td>{{ item.employeeSalary }}</td>
                  <td>{{ item.location }}</td>
                  <td>
                    <button @click="handleEdit(index)">Edit</button>
                    <button @click="handleDelete(index)">Delete</button>
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.page-container {
  display: flex;
  justify-content: space-between;
}

.w-50 {
  width: 45%;
}

form {
  margin-top: 25px;
}

.form-field {
  margin-bottom: 20px;
}

input[type="text"],
select {
  padding: 8px 12px;
  width: 100%;
}

.create-btn {
  background-color: blueviolet;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
}

table {
  width: 100%;
  border-collapse: collapse;
}

td,
th {
  border: 1px solid gray;
  text-align: center;
}

button {
  margin-right: 10px;
  padding: 5px 10px;
  cursor: pointer;
}
</style>
