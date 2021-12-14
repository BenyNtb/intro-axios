<template>
  <div class="hello">
    <!-- <input type="text" placeholder="Shorten a link here ...">
    <button>Shorten It!</button>
    {{ link }} -->
    <div class="row">
      <div class="col col-12 offset-0 mt-2">
        <h1 class="jumbotron text-center text-white bg-primary">Create Click-Worthy Links</h1>
      </div>
    </div>
 
    <div class="col col-8 align-middle mt-5 offset-2">
      <div class="card">
        <div class="card-body">
          <form @submit.prevent="submit(url)">
            <div class="form-group">
              <label for="url">Enter Url</label>
              <textarea type="url" class="form-control" v-model="url" style="height:150px" />
            </div>
            <div class="for-group" v-show="shortUrl">
              <p>
                Short URL: :
                <a :href="shortUrl" class="text-primary">{{shortUrl}}</a>
              </p>
            </div>
            <div class="form-group">
              <button class="btn btn-primary" type="submit">Shorten URl</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data: () => {
    return {
      url: "",
      shortUrl: "",
    }
  },

  methods: {
    submit(url) {
        axios.get('https://api.shrtco.de/v2/shorten?url='+url)
        .then(response => this.shortUrl = response.data.result.full_short_link)
    },
  }
};
// export default {
//   name: 'HelloWorld',
//   data(){
//     return{
//       link: null,
//     }
//   },
//   props: {
//     msg: String
//   },
//   mounted () {
//     axios
//     .get('https://app.shrtco.de/')
//     .then((response) => {
//       this.link = response;
//     console.log(this.link)
//   });
//   },
// }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
