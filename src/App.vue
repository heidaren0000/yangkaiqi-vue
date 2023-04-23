<template>
<div>
    <table>
  <tr>
    <th>姓名</th>
    <th>数学成绩</th>
    <th>语文成绩</th>
    <th>英语成绩</th>
    <th>总成绩</th>
  </tr>
  <tr v-for="student in students" :key="student.name">
    <td>{{ student.name }}</td>
    <td>{{ student.math }}</td>
    <td>{{ student.chinese }}</td>
    <td>{{ student.english }}</td>
    <td>{{ student.english + student.chinese + student.math }}</td>
  </tr>
  <tr>
    <td>平均分</td>
    <td>{{ math_average }}</td>
    <td>{{ chinese_average }}</td>
    <td>{{ english_average }}</td>
    <td>{{ all_average }}</td>
  </tr>
</table>
</div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
       students: [
            { name: '赵云', math: 97, chinese: 89, english: 67 },
            { name: '关羽', math: 67, chinese: 52, english: 98 },
            { name: '张飞', math: 72, chinese: 87, english: 89 },
            { name: '马超', math: 92, chinese: 87, english: 59 },
            { name: '黄忠', math: 47, chinese: 85, english: 92 }
        ]
    }
  },
  methods: {
    // just a little abstraction
    get_single_course_average(coursename) {
      return this.students.reduce((sum, student, index, array) => {
            sum[coursename] += student[coursename];
            if(index === array.length-1) {
                return sum[coursename]/array.length;
            } else {
                return sum;
            }
        }, {
          [coursename]: 0
        })
    }
  },
  computed: {
    math_average() {
      return this.get_single_course_average("math");
    },
    chinese_average() {
      return this.get_single_course_average("chinese");
    },
    english_average() {
      return this.get_single_course_average("english");
    },
    all_average() {
      // get all courses
      const course_list = Object.getOwnPropertyNames(this.students[0]).slice(1, -1);
      // sum all average scores up
      return course_list.reduce((sum, course) => {
        sum += this[`${course}_average`];
        return sum;
      }, 0)
    }
  }
}
</script>

<style>
table, th, td {
    border: 1px solid black;
}
</style>