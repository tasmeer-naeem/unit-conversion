<template>
  <div class="container">
    Temperature Converter
    <div class="teacher">
      <label>Teacher's Input</label>
      <input
        type="text"
        v-model="teacherValue"
        placeholder="enter any number"
      />
      <select @change="teacherselectUnit($event)">
        <option selected disabled>Choose any one</option>
        <option v-for="(item, index) in teacherDropdown" :key="index">
          {{ item.value }}
        </option>
      </select>
    </div>
    <div class="student">
      <label>Student's Input</label>
      <input
        type="text"
        v-model="studentValue"
        placeholder="enter any number"
      />
      <select @change="studentselectUnit($event)">
        <option selected disabled>Choose any one</option>
        <option v-for="(item, index) in studentDropdown" :key="index">
          {{ item.value }}
        </option>
      </select>
    </div>
    <button class="button" type="submit" v-on:click="converter">Convert</button>
    {{ this.result }}
  </div>
</template>

<script>
export default {
  name: "tempConverter",
  data() {
    return {
      teacherValue: "",
      teacherDropdown: [
        { key: "Kelvin", value: "Kelvin" },
        { key: "Celsius", value: "Celsius" },
        { key: "Fahrenheit", value: "Fahrenheit" },
        { key: "Rankine", value: "Rankine" },
      ],
      selectedteacherValue: "",
      studentValue: "",
      studentDropdown: [
        { key: "Kelvin", value: "Kelvin" },
        { key: "Celsius", value: "Celsius" },
        { key: "Fahrenheit", value: "Fahrenheit" },
        { key: "Rankine", value: "Rankine" },
      ],
      selectedstudentValue: "",
      convertedValue: "",
      result: "",
    };
  },
  methods: {
    converter() {
      // console.log("convert");
      /// celcius
      if (this.selectedteacherValue === "Celsius") {
        if (this.selectedstudentValue === "Fahrenheit") {
          // console.log("answer", (this.teacherValue * 9) / 5 + 32);
          this.convertedValue = (this.teacherValue * 9) / 5 + 32;
        }
        if (this.selectedstudentValue === "Kelvin") {
          // console.log("answer", Number(this.teacherValue) + Number(273.15));
          this.convertedValue = Number(this.teacherValue) + Number(273.15);
        }
        if (this.selectedstudentValue === "Rankine") {
          // console.log("answer", (this.teacherValue * 9) / 5 + 491.67);
          this.convertedValue = (this.teacherValue * 9) / 5 + 491.67;
        }
        if (
          this.selectedstudentValue === "Celsius" ||
          this.selectedstudentValue === ''
        ) {
          // console.log('incorrect')
          this.result = "incorrect";
        }
        if (this.studentValue.includes(this.convertedValue)) {
          // console.log('correct')
          this.result = "correct";
        } else {
          // console.log('incorrect')
          this.result = "incorrect";
        }
        if (!Number(this.teacherValue)) {
         //  console.log('invalid')
          this.result = "invalid";
        } 
      }
      /// fahrenheit
      if (this.selectedteacherValue === "Fahrenheit") {
        if (this.selectedstudentValue === "Celsius") {
          // console.log("answer", ((this.teacherValue - 32) * 5) / 9);
          this.convertedValue = ((this.teacherValue - 32) * 5) / 9;
        }
        if (this.selectedstudentValue === "Kelvin") {
          // console.log("answer", ((this.teacherValue - 32) * 5) / 9 + 273.15);
          this.convertedValue = ((this.teacherValue - 32) * 5) / 9 + 273.15;
        }
        if (this.selectedstudentValue === "Rankine") {
          // console.log("answer", Number(this.teacherValue) + Number(459.67));
          this.convertedValue = Number(this.teacherValue) + Number(459.67);
        }
        if (this.studentValue.includes(this.convertedValue)) {
          // console.log('correct')
          this.result = "correct";
        } else {
          // console.log('incorrect')
          this.result = "incorrect";
        }
      }
      ///kelvin
      if (this.selectedteacherValue === "Kelvin") {
        if (this.selectedstudentValue === "Fahrenheit") {
          // console.log("answer", ((this.teacherValue - 273.15) * 9) / 5 + 32);
          this.convertedValue = ((this.teacherValue - 273.15) * 9) / 5 + 32;
        }
        if (this.selectedstudentValue === "Celsius") {
          // console.log("answer", this.teacherValue - 273.15);
          this.convertedValue = this.teacherValue - 273.15;
        }
        if (this.selectedstudentValue === "Rankine") {
          // console.log("answer", this.teacherValue * 1.8);
          this.convertedValue = this.teacherValue * 1.8;
        }
        if (this.studentValue.includes(this.convertedValue)) {
          // console.log('correct')
          this.result = "correct";
        } else {
          // console.log('incorrect')
          this.result = "incorrect";
        }
      }
      ///rankin
      if (this.selectedteacherValue === "Rankine") {
        if (this.selectedstudentValue === "Fahrenheit") {
          // console.log("answer", this.teacherValue - 459.67);
          this.convertedValue = this.teacherValue - 459.67;
        }
        if (this.selectedstudentValue === "Kelvin") {
          // console.log("answer", (this.teacherValue * 5) / 9);
          this.convertedValue = (this.teacherValue * 5) / 9;
        }
        if (this.selectedstudentValue === "Celsius") {
          // console.log("answer", ((this.teacherValue - 491.67) * 5) / 9);
          this.convertedValue = ((this.teacherValue - 491.67) * 5) / 9;
        }
        if (this.studentValue.includes(this.convertedValue)) {
          // console.log('correct')
          this.result = "correct";
        } else {
          // console.log('incorrect')
          this.result = "incorrect";
        }
      }
    },
    teacherselectUnit($event) {
      // console.log($event.target.value);
      this.selectedteacherValue = $event.target.value;
    },
    studentselectUnit($event) {
      // console.log($event.target.value);
      this.selectedstudentValue = $event.target.value;
    },
  },
};
</script>

<style>
.container {
  color: black;
  font-weight: bold;
}

.teacher {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
}

.student {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
}

.button {
  display: inline-block;
  position: relative;
  top: 10px;
  padding: 12px 18px;
}
</style>
