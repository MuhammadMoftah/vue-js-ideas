<template>
  <label
    class="flex items-center w-full my-2 rounded cursor-pointer hover:bg-gray-100"
  >
    <img width="100" class="bg-gray-100 rounded" v-if="img" :src="img" alt="" />
    <img
      width="100"
      class="p-6 bg-gray-100 rounded"
      v-else
      src="https://image.flaticon.com/icons/png/512/45/45141.png"
      alt=""
    />
    <input
      type="file"
      @change="selectImage($event.target)"
      hidden
      accept="image/*"
    />
    <p class="px-2 text-sm italic text-gray-500">Click to select image</p>
  </label>
</template>

<script>
export default {
  data() {
    return {
      img: null,
    }
  },
  methods: {
    selectImage(img) {
      this.img = URL.createObjectURL(img.files[0])
      this.$emit('getImage', img.files[0])
    },
  },
}
</script>

<style>
</style> 