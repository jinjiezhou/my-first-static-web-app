<template>
  <div>Hello {{ message }}</div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      message: ""
    };
  },
  async mounted() {
    const { text } = await (await get("/api/message")).json();
    this.message = text;
  }
};
</script>
