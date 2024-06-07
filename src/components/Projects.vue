<template>
  <div class="projects">
    <h1>Daftar Mata Kuliah</h1>
    <p>Berikut adalah beberapa mata kuliah yang tersedia.</p>
    <button @click="showTable = !showTable">
      {{ showTable ? 'Sembunyikan' : 'Tampilkan' }} Jadwal Mata Kuliah
    </button>
    <button @click="toggleForm">
      {{ showForm ? 'Sembunyikan' : 'Tambah' }} Mata Kuliah
    </button>
    <slot></slot>
    <form v-if="showForm" @submit.prevent="saveCourse">
      <div>
        <label>Kode Mata Kuliah:</label>
        <input v-model="newCourse.code" required />
      </div>
      <div>
        <label>Nama Mata Kuliah:</label>
        <input v-model="newCourse.name" required />
      </div>
      <div>
        <label>Dosen:</label>
        <input v-model="newCourse.lecturer" required />
      </div>
      <div>
        <label>SKS:</label>
        <input v-model="newCourse.sks" type="number" required />
      </div>
      <div>
        <label>Hari:</label>
        <input v-model="newCourse.day" required />
      </div>
      <button type="submit">{{ editIndex === -1 ? 'Tambah' : 'Update' }} Mata Kuliah</button>
      <button type="button" @click="resetForm">Batal</button>
    </form>
    <table v-if="showTable">
      <thead>
        <tr>
          <th>Kode Mata Kuliah</th>
          <th>Nama Mata Kuliah</th>
          <th>Dosen</th>
          <th>SKS</th>
          <th>Hari</th>
          <th>Aksi</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(course, index) in courses" :key="course.code">
          <td>{{ course.code }}</td>
          <td>{{ course.name }}</td>
          <td>{{ course.lecturer }}</td>
          <td>{{ course.sks }}</td>
          <td>{{ course.day }}</td>
          <td>
            <button @click="editCourse(index)">Edit</button>
            <button @click="deleteCourse(index)">Hapus</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showTable: false,
      showForm: false,
      courses: [
        { code: 'MK001', name: 'Algoritma dan Struktur Data', lecturer: 'Dr. Budi Santoso', sks: 3, day: 'Senin' },
        { code: 'MK002', name: 'Pemrograman Web', lecturer: 'Dr. Siti Aminah', sks: 3, day: 'Selasa' },
        { code: 'MK003', name: 'Basis Data', lecturer: 'Dr. Anwar Abdullah', sks: 3, day: 'Rabu' },
      ],
      newCourse: {
        code: '',
        name: '',
        lecturer: '',
        sks: 0,
        day: ''
      },
      editIndex: -1
    };
  },
  methods: {
    toggleForm() {
      this.showForm = !this.showForm;
      if (!this.showForm) {
        this.resetForm();
      }
    },
    saveCourse() {
      if (this.editIndex === -1) {
        this.courses.push({ ...this.newCourse });
      } else {
        Object.assign(this.courses[this.editIndex], this.newCourse);
      }
      this.resetForm();
      this.showForm = false;
    },
    editCourse(index) {
      this.newCourse = { ...this.courses[index] };
      this.editIndex = index;
      this.showForm = true;
    },
    deleteCourse(index) {
      this.courses.splice(index, 1);
    },
    resetForm() {
      this.newCourse = {
        code: '',
        name: '',
        lecturer: '',
        sks: 0,
        day: ''
      };
      this.editIndex = -1;
    }
  }
};
</script>

<style>
.projects {
  padding: 40px 20px;
  text-align: center;
  background-color: #1c1c1c;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
  color: #f5f5f5;
}

.projects h1 {
  font-size: 2.5em;
  margin-bottom: 20px;
  color: #ffdd57;
}

.projects p {
  font-size: 1.2em;
  color: #b5b5b5;
  margin-bottom: 20px;
}

button {
  background-color: #ffdd57;
  color: #1c1c1c;
  border: none;
  padding: 10px 20px;
  font-size: 1em;
  cursor: pointer;
  border-radius: 5px;
  transition: background-color 0.3s ease;
  margin: 5px;
}

button:hover {
  background-color: #e6c847;
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
  color: #f5f5f5;
  border: 1px solid #3c3c3c;
}

th, td {
  padding: 12px;
  text-align: left;
  border: 1px solid #3c3c3c;
}

th {
  background-color: #ffdd57;
  color: #1c1c1c;
}

tbody tr {
  background-color: #2c2c2c;
}

tbody tr:hover {
  background-color: #3c3c3c;
}

form div {
  margin: 10px 0;
}

form label {
  display: inline-block;
  width: 150px;
  text-align: right;
  margin-right: 10px;
  color: #b5b5b5;
}

form input {
  padding: 5px;
  width: 200px;
  border: 1px solid #3c3c3c;
  border-radius: 5px;
}
</style>
