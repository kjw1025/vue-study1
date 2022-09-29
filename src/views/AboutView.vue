<template>
  <div class="about"></div>
</template>

<script>
import axios from "axios";
export default {
  setup() {
    let id = "DeHyXTOI0F6OhYCzWQk8";
    let pass = "0RDDq8mv2N";

    axios
      .get(
        "https://cors-anywhere.herokuapp.com/https://openapi.naver.com/v1/search/movie.json",
        {
          params: { query: "starwars", display: 20 },
          headers: {
            Accept: "*/*",
            "X-Naver-Client-Id": id,
            "X-Naver-Client-Secret": pass,
          },
        }
      )
      .then((response) => {
        let resData = response.data.items;
        console.log(resData);
      })
      .catch((err) => console.log(err));

    return {};
  },
};
</script>

<style></style>
