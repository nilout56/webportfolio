<template>
  <div class="space">
    <div class="sun"></div>
    <div class="earth">
      <div class="dino"></div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'IPage',
  head() {
    return {
      title: 'Under Development',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'This page is under development.',
        },
      ],
    }
  },
  data() {
    return {}
  },
}
</script>
<style scoped>
.space {
  width: 300px;
  height: 300px;
  margin: 0 auto;
  border-radius: 100%;
  background-image: url('https://images.unsplash.com/photo-1535007726788-fed8106a64cd?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=750&q=80');
  overflow: hidden;
  animation-name: spin;
  animation-duration: 100s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
}
.sun {
  background-image: url('https://www.borntodev.com/wp-content/uploads/2020/03/b2dsun.png');
  width: 60px;
  height: 60px;
  border-radius: 30px;
  margin: 0 auto;
  background-size: contain;
  position: relative;
  top: 10%;
  animation-name: spin, scale;
  animation-duration: 0.5s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
}
.earth {
  width: 250px;
  height: 250px;
  border-radius: 300px;

  background-image: url('https://www.borntodev.com/wp-content/uploads/2020/03/earth.png');
  margin: 0 auto;
  background-size: contain;
  animation-name: spin;
  animation-duration: 10s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
  position: relative;
  top: 60%;
}
.dino {
  margin: 0 auto;
  background-image: url('https://www.borntodev.com/wp-content/uploads/2020/03/b2d-2.png');
  border-radius: 50px;
  background-size: contain;
  width: 75px;
  height: 75px;
  top: -35px;
  position: relative;

  animation-name: spin;
  animation-duration: 1s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
  z-index: 2;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
@keyframes scale {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(0.8);
  }
  100% {
    transform: scale(1);
  }
}
</style>
