<template>
  <div class="about">
    <p>{{ setData }}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  setup() {
    const setData = [];

    const shoppingData = async () => {
      const URL = "https://openapi.naver.com/v1/search/movie.json";
      const ClientID = "DeHyXTOI0F6OhYCzWQk8";
      const ClientSecret = "0RDDq8mv2N";

      await axios
        .get(URL, {
          headers: {
            "X-Naver-Client-Id": ClientID,
            "X-Naver-Client-Secret": ClientSecret,
          },
        })
        .then((res) => setData(res.data))
        .catch((err) => console.log(err));
    };
    shoppingData();

    return {
      setData,
    };
  },
};
</script>

<style></style>
