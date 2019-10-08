<template>
  <div class="container">
    <form @submit.prevent="addSkill">
      <input type="text" placeholder="Enter a skill you have.." v-model="skill" />
    </form>
    <div class="holder">
      <ul>
        <li v-for="(data, index) in skills" :key="index">{{data.skill}}</li>
      </ul>
      <p>These are the skills that you possess.</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Skills",
  data() {
    return {
      name: "Learning Vue",
      // btnState: true,
      skill: "",
      skills: [{ skill: "Vue.js" }, { skill: "Frontend Developer" }],
      showAlert: true
    };
  },
  methods: {
    addSkill() {
      if (this.skill) {
        this.skills.push({ skill: this.skill });
        this.skill = "";
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style  scoped>
.container {
  box-shadow: 0px 0px 40px #61c4fd;
}

.holder {
  background: #fff;
  border-radius: 8px 0 0 0;
}

ul {
  margin: 0;
  padding: 0;
  list-style-type: none;
}

ul li {
  padding: 20px;
  font-size: 1.3em;
  background-color: #c2e4f7;
  border-left: 5px solid #3eb3f6;
  border-radius: 6px 0 0 6px;
  margin-bottom: 2px;
  color: #3e5252;
}

p {
  text-align: center;
  padding: 30px 0;
  color: gray;
}

input {
  width: calc(100% - 40px);
  border: 0;
  border-radius: 3px;
  padding: 20px;
  font-size: 1.3em;
  background-color: #323333;
  color: #687f7f;
}

.alert {
  background: #f84b3e;
  font-weight: bold;
  color: #687f7f;
  display: inline-block;
  padding: 5px;
  margin-top: -20px;
}
</style>
