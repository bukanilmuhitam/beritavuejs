<template>
  <main style="margin-top:40px;">
    <div class="container">
      <div class="row">
        <div class="col-lg-8">
          <div class="row">
            <div class="col-lg-12 mt-4" v-for="item  in topHeadnews" :key="item.topHeadnews">
              <div class="card">
                <div class="card-header"  v-if="item.author != null">
                   Author : {{ item.author }}
                </div>
                <div class="card-header" v-else>
                    Author : Anonymous
                </div>
                <div class="card-body">
                  <h5 class="card-title">
                      {{ item.title}}
                  </h5>
                  <p class="card-text" style="overflow: hidden; text-overflow: ellipsis; white-space: nowrap; width: 100%; display: inline-block;">
                    {{ item.description }}
                  </p>
                  <a href="#" class="btn btn-primary">Readmore</a>
                  <br/>
                  <br />
                  <small class="mt-4">URL : <a v-bind:href="item.url">{{ item.url }}</a></small>
                </div>
              </div>
              <!-- <ul id="example-1">
                <li v-for="item  in topHeadnews" :key="item.topHeadnews">
                  {{ item.author }} 
                </li>
              </ul> -->
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      topHeadnews: [],
    };
  },
  methods: {
    getTopheadline() {
      axios
        .get(
          "https://newsapi.org/v2/top-headlines?country=id&apiKey=a86c939e3b854dec875b4a4409c78259"
        )
        .then((response) => {
          this.topHeadnews = response.data.articles;
            // console.log(response.data.articles.author);
        });
    },
  },
  mounted() {
    this.getTopheadline();
  },
};
</script>
