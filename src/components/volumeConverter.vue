<template>
  <div class="container">
    Volume Converter
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
  name: "volumeConverter",
  data() {
    return {
      teacherValue: "",
      teacherDropdown: [
        { key: "liters", value: "liters" },
        { key: "tablespoons", value: "tablespoons" },
        { key: "cubic-inches", value: "cubic-inches" },
        { key: "cups", value: "cups" },
        { key: "cubic-feet", value: "cubic-feet" },
        { key: "gallons", value: "gallons" },
      ],
      selectedteacherValue: "",
      studentValue: "",
      studentDropdown: [
        { key: "liters", value: "liters" },
        { key: "tablespoons", value: "tablespoons" },
        { key: "cubic-inches", value: "cubic-inches" },
        { key: "cups", value: "cups" },
        { key: "cubic-feet", value: "cubic-feet" },
        { key: "gallons", value: "gallons" },
      ],
      selectedstudentValue: "",
      convertedValue: "",
      result: "",
    };
  },
  methods: {
    converter() {
      // console.log("convert");
      /// liters
      if (this.selectedteacherValue === "liters") {
        if (this.selectedstudentValue === "tablespoons") {
          // console.log("answer",(this.teacherValue * 67.628));
          this.convertedValue = this.teacherValue * 67.628;
        }
        if (this.selectedstudentValue === "cubic-inches") {
          // console.log("answer",(this.teacherValue * 61.024));
          this.convertedValue = this.teacherValue * 61.024;
        }
        if (this.selectedstudentValue === "cups") {
          // console.log("answer",(this.teacherValue * 4.167));
          this.convertedValue = this.teacherValue * 4.167;
        }
        if (this.selectedstudentValue === "cubic-feet") {
          // console.log("answer",(this.teacherValue / 28.317));
          this.convertedValue = this.teacherValue / 28.317;
        }
        if (this.selectedstudentValue === "gallons") {
          // console.log("answer",(this.teacherValue / 3.785));
          this.convertedValue = this.teacherValue / 3.785;
        }
        if (this.studentValue.includes(this.convertedValue)) {
          // console.log('correct')
          this.result = "correct";
        } else {
          // console.log('incorrect')
          this.result = "incorrect";
        }
      }
      /// tablespoon
      if (this.selectedteacherValue === "tablespoons") {
        if (this.selectedstudentValue === "liters") {
          // console.log("answer",(this.teacherValue / 67.628));
          this.convertedValue = this.teacherValue / 67.628;
        }
        if (this.selectedstudentValue === "cubic-inches") {
          // console.log("answer",(this.teacherValue / 1.108));
          this.convertedValue = this.teacherValue / 1.108;
        }
        if (this.selectedstudentValue === "cups") {
          // console.log("answer",(this.teacherValue / 16.231));
          this.convertedValue = this.teacherValue / 16.231;
        }
        if (this.selectedstudentValue === "cubic-feet") {
          // console.log("answer",(this.teacherValue / 1915));
          this.convertedValue = this.teacherValue / 1915;
        }
        if (this.selectedstudentValue === "gallons") {
          // console.log("answer",(this.teacherValue / 256));
          this.convertedValue = this.teacherValue / 256;
        }
        if (this.studentValue.includes(this.convertedValue)) {
          // console.log('correct')
          this.result = "correct";
        } else {
          // console.log('incorrect')
          this.result = "incorrect";
        }
      }
      ///cubic-inches
      if (this.selectedteacherValue === "cubic-inches") {
        if (this.selectedstudentValue === "tablespoons") {
          // console.log("answer",(this.teacherValue * 1.108));
          this.convertedValue = this.teacherValue * 1.108;
        }
        if (this.selectedstudentValue === "liters") {
          // console.log("answer",(this.teacherValue * 61.024));
          this.convertedValue = this.teacherValue * 61.024;
        }
        if (this.selectedstudentValue === "cups") {
          // console.log("answer",(this.teacherValue / 14.646));
          this.convertedValue = this.teacherValue / 14.646;
        }
        if (this.selectedstudentValue === "cubic-feet") {
          // console.log("answer",(this.teacherValue / 1728));
          this.convertedValue = this.teacherValue / 1728;
        }
        if (this.selectedstudentValue === "gallons") {
          // console.log("answer",(this.teacherValue / 231));
          this.convertedValue = this.teacherValue / 231;
        }
        if (this.studentValue.includes(this.convertedValue)) {
          // console.log('correct')
          this.result = "correct";
        } else {
          // console.log('incorrect')
          this.result = "incorrect";
        }
      }
      ///cups
      if (this.selectedteacherValue === "cups") {
        if (this.selectedstudentValue === "tablespoons") {
          // console.log("answer",(this.teacherValue * 16.231));
          this.convertedValue = this.teacherValue * 16.231;
        }
        if (this.selectedstudentValue === "cubic-inches") {
          // console.log("answer",(this.teacherValue * 14.646));
          this.convertedValue = this.teacherValue * 14.646;
        }
        if (this.selectedstudentValue === "liters") {
          // console.log("answer",(this.teacherValue / 4.167));
          this.convertedValue = this.teacherValue / 4.167;
        }
        if (this.selectedstudentValue === "cubic-feet") {
          // console.log("answer",(this.teacherValue / 118));
          this.convertedValue = this.teacherValue / 118;
        }
        if (this.selectedstudentValue === "gallons") {
          // console.log("answer",(this.teacherValue / 15.772));
          this.convertedValue = this.teacherValue / 15.772;
        }
        if (this.studentValue.includes(this.convertedValue)) {
          // console.log('correct')
          this.result = "correct";
        } else {
          // console.log('incorrect')
          this.result = "incorrect";
        }
      }
      ///cubic-feet
      if (this.selectedteacherValue === "cubic-feet") {
        if (this.selectedstudentValue === "tablespoons") {
          // console.log("answer",(this.teacherValue * 1915));
          this.convertedValue = this.teacherValue * 1915;
        }
        if (this.selectedstudentValue === "cubic-inches") {
          // console.log("answer",(this.teacherValue * 1728));
          this.convertedValue = this.teacherValue * 1728;
        }
        if (this.selectedstudentValue === "cups") {
          // console.log("answer",(this.teacherValue * 118));
          this.convertedValue = this.teacherValue * 118;
        }
        if (this.selectedstudentValue === "liters") {
          // console.log("answer",(this.teacherValue * 28.317));
          this.convertedValue = this.teacherValue * 28.317;
        }
        if (this.selectedstudentValue === "gallons") {
          // console.log("answer",(this.teacherValue * 7.481));
          this.convertedValue = this.teacherValue * 7.481;
        }
        if (this.studentValue.includes(this.convertedValue)) {
          // console.log('correct')
          this.result = "correct";
        } else {
          // console.log('incorrect')
          this.result = "incorrect";
        }
      }
      ///gallons
      if (this.selectedteacherValue === "gallons") {
        if (this.selectedstudentValue === "tablespoons") {
          // console.log("answer",(this.teacherValue * 256));
          this.convertedValue = this.teacherValue * 256;
        }
        if (this.selectedstudentValue === "cubic-inches") {
          // console.log("answer",(this.teacherValue * 231));
          this.convertedValue = this.teacherValue * 231;
        }
        if (this.selectedstudentValue === "cups") {
          // console.log("answer",(this.teacherValue * 15.773));
          this.convertedValue = this.teacherValue * 15.773;
        }
        if (this.selectedstudentValue === "liters") {
          // console.log("answer",(this.teacherValue * 3.785));
          this.convertedValue = this.teacherValue * 3.785;
        }
        if (this.selectedstudentValue === "cubic-feet") {
          // console.log("answer",(this.teacherValue / 7.48));
          this.convertedValue = this.teacherValue / 7.48;
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

<style></style>
