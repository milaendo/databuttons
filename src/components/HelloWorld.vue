<template>
  <div class="hello">
    <h2>Im the nested child with the click event</h2>
    <table class="table table-hover">
    <thead>
      <tr>
        <th scope="col">UID</th>
        <th scope="col">code</th>
        <th scope="col">Name</th>
        <th scope="col">Description</th>
      </tr>
    </thead>
    <tbody v-for="(item,index) in response">
      <tr @click="onClick(index)">
        <td>{{item.uid}}</td>
        <td>{{item.name}}</td>
        <td>{{item.code}}</td>
        <td>{{item.description}}</td>
      </tr>
    </tbody>
  </table>
  <b-modal v-if="shown" ref="myModalRef" hide-footer title="Using Component Methods">
    <div class="d-block text-center">
      <h3>Hello {{userData.name}}</h3>
    </div>
    <b-btn class="mt-3" variant="outline-danger" block @click="hideModal">Close Me</b-btn>
  </b-modal>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: ['response'],
  data () {
    return {
      shown: false,
      userData: null
    }
  },
  created() {
    console.log('nested child: this one needs the click event')
  },
  methods: {
    onClick(index) {
      this.showModal(index)
      console.log("I was clicked by:", index, this.response[index].name)
    },
    showModal (index) {
      this.$refs.myModalRef.show()
      this.userData = JSON.parse(JSON.stringify(this.response[index]));
      console.log(this.userData)
    },
    hideModal () {
      this.$refs.myModalRef.hide()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
