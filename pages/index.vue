<template>
  <div>
    <h1>Welcome to the Home Page</h1>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  // Head Tag
  head() {
    return {
        title: 'Home Page',
        meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Best dad jokes home page'
        }
      ]
    }
  }
}
</script>
