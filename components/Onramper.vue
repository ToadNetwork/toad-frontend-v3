<template>
<div class="onramper">
  <iframe
  width="100%"
  height="100%"
  id="onramper-widget"
  title="Onramper widget"
  frameborder="no"
  allow="accelerometer; autoplay; camera; gyroscope; payment;"
  src="https://widget.onramper.com?color=266678&apiKey=pk_prod_rZrnwLh6B5Ah9zaKFRS4uKTPFB1MtUcjGXrzNPuDoLE0">
  </iframe>
</div>
</template>
<style scoped>
.onramper {
  flex-grow: 1;
  border: none;
  margin: 0;
  padding: 0;
}
iframe {
  display: block;
  height: 100%;
  width: 100%;
  border: none;
}
</style>
