<template>
  <div class="about d-flex align-items-end">
    <h1>Sorry, as soon as will be done! </h1>
    <span class="dot-typing">.</span>
  </div>
</template>
 


<style lang="scss" scoped>
.about{ 
 padding: 24px;

}
h1{
  color:#336CFB;
}
  .dot-typing {
  margin-left: 20px;
  position: relative;
  top: -1rem;
  left: -9999px;
  height: 5px !important;
  width: 5px !important;
  border-radius: 50%;
  color: #336CFB;
  // box-shadow: 9984px 0 0 0 #9880ff, 9999px 0 0 0 #9880ff, 10014px 0 0 0 #9880ff;
  animation: dotTyping 1.5s infinite linear;
}

@keyframes dotTyping {
  0% {
    box-shadow: 9984px 0 0 0 #336CFB, 9999px 0 0 0 #336CFB, 10014px 0 0 0 #336CFB;
  }
  16.667% {
    box-shadow: 9984px -10px 0 0 #336CFB, 9999px 0 0 0 #336CFB, 10014px 0 0 0 #336CFB;
  }
  33.333% {
    box-shadow: 9984px 0 0 0 #336CFB, 9999px 0 0 0 #336CFB, 10014px 0 0 0 #336CFB;
  }
  50% {
    box-shadow: 9984px 0 0 0 #336CFB, 9999px -10px 0 0 #336CFB, 10014px 0 0 0 #336CFB;
  }
  66.667% {
    box-shadow: 9984px 0 0 0 #336CFB, 9999px 0 0 0 #336CFB, 10014px 0 0 0 #336CFB;
  }
  83.333% {
    box-shadow: 9984px 0 0 0 #336CFB, 9999px 0 0 0 #336CFB, 10014px -10px 0 0 #336CFB;
  }
  100% {
    box-shadow: 9984px 0 0 0 #336CFB, 9999px 0 0 0 #336CFB, 10014px 0 0 0 #336CFB;
  }
}

</style>