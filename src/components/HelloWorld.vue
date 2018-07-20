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
        <th scope="col">Status</th>
      </tr>
    </thead>
    <tbody v-for="(item,index) in response">
      <tr @click="onClick(index)">
        <td>{{item.uid}}</td>
        <td>{{item.name}}</td>
        <td>{{item.code}}</td>
        <td>{{item.description}}</td>
        <td>{{item.status}}</td>
      </tr>
    </tbody>
  </table>
  <b-modal ref="myModalRef" hide-footer title="Using Component Methods">
    <div class="d-block text-center">
      <b-form-group id="exampleInputGroup1"
                    label="Code"
                    label-for="exampleInput1">
      <b-form-input id="exampleInput1"
                    type="email"
                    v-model="code"
                    required>
      </b-form-input>
      </b-form-group>
      <b-form-group id="exampleInputGroup2"
                  label="Name"
                  label-for="exampleInput2">
      <b-form-input id="exampleInput2"
                    type="text"
                    v-model="name"
                    required>
      </b-form-input>
      </b-form-group>
      <b-form-group id="exampleInputGroup1"
                    label="description"
                    label-for="exampleInput1">
      <b-form-input id="exampleInput1"
                    type="email"
                    v-model="description"
                    required>
      </b-form-input>
      </b-form-group>
      <b-form-group id="exampleInputGroup3"
                  label="Status"
                  label-for="exampleInput3">
      <b-form-input id="exampleInput2"
                    type="text"
                    v-model="status"
                    required>
      </b-form-input>
      </b-form-group>
      <b-button @click="hideModal" type="reset" variant="danger">Cancel</b-button>
      <b-button @click="saveForm" type="submit" variant="primary">Submit</b-button>
      </div>
  </b-modal>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: ['response'],
  data () {
    return {
      name: '',
      code: '',
      description: '',
      uid: '',
      status: '',
      curIndex: '',
    }
  },
  created() {
    console.log('nested child: this one needs the click event')
  },
  methods: {
    onClick(index) {
      this.name = this.response[index].name;
      this.code = this.response[index].code;
      this.status = this.response[index].status;
      this.description = this.response[index].description;
      this.uid = this.response[index].uid;
      this.curIndex = index;
      this.$refs.myModalRef.show()
    },
    hideModal () {
      this.$refs.myModalRef.hide()
    },
    clearForm(curIndex) {
      this.name = '',
      this.code = '',
      this.description = '',
      this.uid = '',
      this.status = ''
    },
    saveForm(curIndex) {
      this.response[this.curIndex].name = this.name
      this.response[this.curIndex].code = this.code
      this.response[this.curIndex].description = this.description
      this.response[this.curIndex].uid = this.uid
      this.response[this.curIndex].status = this.status
      this.clearForm()
      this.hideModal ()
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
