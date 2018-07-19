<template>
  <div id="app">
    <h1>Im the parent</h1>
    <hello-world v-bind:response="response"></hello-world>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld"
export default {
  components: { HelloWorld },
  data() {
    return {
  "response":[
     {
        "uid":"7168a8bd-dfc3-48c3-83f5-e696781924ac",
        "parent_role_id":null,
        "name":"name",
        "description":"desr",
        "code":"code",
        "created_at":"2018-07-17 03:05:49",
        "updated_at":"2018-07-18 23:45:54",
        "status":"ACTIVE",
        "total_users":0
     },
     {
        "uid":"7663b157-d673-4000-9fa9-33e5922c9bff",
        "parent_role_id":null,
        "name":"nice",
        "description":"new",
        "code":"hello",
        "created_at":"2018-07-17 03:05:49",
        "updated_at":"2018-07-18 23:44:28",
        "status":"DISABLED",
        "total_users":0
     },
     {
        "uid":"1eeb3937-fcca-4a7c-aadc-df09cbe20302",
        "parent_role_id":null,
        "name":"Administrator",
        "description":"Overall Administration of System",
        "code":"PROCESSMAKER_ADMIN",
        "created_at":"2018-06-27 16:14:37",
        "updated_at":"2018-06-27 16:14:37",
        "status":"ACTIVE",
        "total_users":1
     },
     {
        "uid":"b6679b4f-44f0-4ec2-9d1d-c5358dc32c1b",
        "parent_role_id":null,
        "name":"Manager",
        "description":"Allow management of cases,users and groups.",
        "code":"PROCESSMAKER_MANAGER",
        "created_at":"2018-06-27 16:14:37",
        "updated_at":"2018-06-27 16:14:37",
        "status":"ACTIVE",
        "total_users":0
     },
     {
        "uid":"239b6126-a52e-411a-994e-cb08aea85b20",
        "parent_role_id":null,
        "name":"Operator",
        "description":"Standard Users that allow login and execution of cases",
        "code":"PROCESSMAKER_OPERATOR",
        "created_at":"2018-06-27 16:14:37",
        "updated_at":"2018-06-27 16:14:37",
        "status":"ACTIVE",
        "total_users":0
     },
     {
        "uid":"20f871d5-5495-41a4-a90a-f6c938d58953",
        "parent_role_id":null,
        "name":"hh",
        "description":"thdrgeffsgdhfjyg",
        "code":"wqdefrdfg",
        "created_at":"2018-07-18 21:14:37",
        "updated_at":"2018-07-18 23:46:28",
        "status":"DISABLED",
        "total_users":0
     },
     {
        "uid":"c5c12b18-9f19-48a4-9628-8e4d568ab6d4",
        "parent_role_id":null,
        "name":"name",
        "description":"yes",
        "code":"yyyyy",
        "created_at":"2018-07-18 21:51:19",
        "updated_at":"2018-07-18 23:35:17",
        "status":"DISABLED",
        "total_users":0
     }
  ],
  "meta":{
     "total":7,
     "count":7,
     "per_page":10,
     "current_page":1,
     "total_pages":1,
     "filter":null,
     "sort_by":"",
     "sort_order":""
   }
  }
  },
  name: 'App',
  created() {
    console.log('child')
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
