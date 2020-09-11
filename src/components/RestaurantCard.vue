<template>
  <div class="col-md-6 col-lg-4">
    <div class="card mb-4">
      <div class="card-body">
        <p class="card-text title-warp">
          <a href="#">restaurant name</a>
        </p>
        <span class="badge badge-secondary">category</span>
        <p class="card-text text-truncate">restaurant description</p>
      </div>
      <div class="card-footer">
        <button
          v-if="restaurant.isFavorited"
          type="button"
          class="btn btn-danger mr-2"
          @click.stop.prevent="deleteFavorite"
        >移除最愛</button>
        <button
          v-else
          type="button"
          class="btn btn-primary mr-2"
          @click.stop.prevent="addFavorite"
        >加入最愛</button>
        <button
          v-if="restaurant.isLike"
          type="button"
          class="btn btn-danger mr-2"
          @click.stop.prevent="deleteLike"
        >Unlike</button>
        <button v-else type="button" class="btn btn-primary mr-2" @click.stop.prevent="addLike">Like</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    initialRestaurant: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      restaurant: {
        isFavorited: false,
        isLike: false,
      },
    };
  },
  methods: {
    addFavorite() {
      this.restaurant.isFavorited = true;
    },
    deleteFavorite() {
      this.restaurant.isFavorited = false;
    },
    addLike() {
      this.restaurant.isLike = true;
    },
    deleteLike() {
      this.restaurant.isLike = false;
    },
  },
};
</script>