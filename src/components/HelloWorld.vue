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
    <!-- <b-modal ref="myModalRef" hide-footer title="Using Component Methods">
    <div class="d-block text-center">
      <b-form v-if="show">
      <b-form-group id="exampleInputGroup1"
                    label=""
                    label-for="exampleInput1">
        <b-form-input id="exampleInput1"
                      type="email"
                      required
                      :placeholder="user.name">
        </b-form-input>
      </b-form-group>
      <b-form-group id="exampleInputGroup2"
                    label=""
                    label-for="exampleInput2">
        <b-form-input id="exampleInput2"
                      type="text"
                      required
                      :placeholder="user.code">
        </b-form-input>
      </b-form-group>
    </b-form>
    </div>
    <b-btn class="mt-3" variant="outline-danger" block @click="hideModal">Close Me</b-btn>
  </b-modal> -->
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: ['response'],
  data () {
    return {
      show: true,

    }
  },
  created() {
    console.log('nested child: this one needs the click event')
  },
  methods: {
    onClick(index) {
      console.log("I was clicked by:", index, this.response[index].name)
    },
    showModal () {
      this.$refs.myModalRef.show()
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
