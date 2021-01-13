<template>
    <h2 class="title__grey">{{titleG}} :</h2>
</template>
<script>
export default {
  props: ['titleG'],
  data: () => ({

  })
}
</script>
<style>
.title__grey {
    font-family: Montserrat;
    font-weight: 900;
    font-size: 34px;
    line-height: 34px;
    color: #999999;
    text-transform:uppercase;
}
</style>
