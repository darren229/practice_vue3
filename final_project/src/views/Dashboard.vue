<template>
  Dashboard
</template>

<script>
export default {
  created() {
    const token = document.cookie.replace(/(?:(?:^|.*;\s*)renToken\s*\s*([^;]*).*$)|^.*$/, '$1')
    console.log(token)
    this.$http.defaults.headers.common.Authorization = token
    const api = `${process.env.VUE_APP_API}api/user/check`
    this.$http.post(api, this.user).then((res) => {
      console.log(res)
    })
  }
}
</script>
