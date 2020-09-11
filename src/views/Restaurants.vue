// ./src/views/Restaurants.vue
<template>
  <div class="container py-5">
    <NavTabs />
    <h1 class="mt-5">首頁 - 餐廳列表</h1>
    <NavPills />
    <RestaurantCard :initialRestaurant="initialRestaurant" />
  </div>
</template>

<script>
import NavTabs from "../components/NavTabs";
import NavPills from "../components/NavPills";
import RestaurantCard from "../components/RestaurantCard";

const dummyData = {
  restaurants: [
    {
      id: "1",
      name: "dummytest1",
      tel: "1234567",
      opening_hours: "12:00",
      description: "description test",
      address: "address test",
      image: "image test",
      viewCount: "0",
      favoriteCount: "0",
    },
    {
      id: "2",
      name: "dummytest2",
      tel: "7654321",
      opening_hours: "12:00",
      description: "description test2",
      address: "address test2",
      image: "image test2",
      viewCount: "0",
      favoriteCount: "0",
    },
  ],
};
export default {
  components: {
    NavTabs,
    NavPills,
    RestaurantCard,
  },
  data() {
    return {
      initialRestaurant: [],
    };
  },
  methods: {
    fetchData() {
      const { restaurants } = dummyData;
      this.initialRestaurant = restaurants;
    },
  },
  created() {
    this.fetchData();
  },
};
</script>