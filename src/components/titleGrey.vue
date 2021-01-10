<template>
    <h2 class="title__grey">{{titlesGr}} :</h2>
</template>
<script>
export default {
  props: ['titlesGr'],
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
    color: #C4C4C4;
}
</style>
