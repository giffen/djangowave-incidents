<template>
  <div>
    <NotificationBar />
    <TheHeader />
      <transition
        enter-active-class="animated slideInLeft"
        mode="out-in"
        leave-active-class="animated slideOutRight"
      >
        <nuxt />
      </transition>
    <TheFooter />
  </div>
</template>

<script>
import NotificationBar from '@/components/visitors/general/NotificationBar'
import TheHeader from '@/components/visitors/general/TheHeader'
import TheFooter from '@/components/visitors/general/TheFooter'

export default {
  components: { TheHeader, TheFooter, NotificationBar }
}
</script>

<style>
body {
  font-family: Montserrat;
}
body, html {
  margin: 0px; padding: 0px;
}
h2, h3, h1, h4 {
  margin-top: 5px; margin-bottom: 5px;
}
a, a:focus, a:visited, a:hover {
  color: #000; text-decoration: none;
}
.issue, .yellow {
  background: #F1C21A;
}
.down, .red {
  background: #CD5C5C;
}
.up, .green {
  background: #2EE779;
}
/* CSS3 Animation Styles */
.animated {
  -webkit-animation-duration: 0.2s;
  animation-duration: 0.2s;
  -webkit-animation-fill-mode: both;
  animation-fill-mode: both;
}
@keyframes slideInLeft {
  from {
    transform: translate3d(-1%, 0, 0);
    opacity: 0;
    visibility: visible;
  }
  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}
@keyframes slideOutRight {
  from {
    transform: translate3d(0, 0, 0);
    opacity: 1;
    visibility: visible;
  }
  to {
    opacity: 0;
    transform: translate3d(1%, 0, 0);
  }
}
.slideOutRight {
  animation-name: slideOutRight;
}
.slideInLeft {
  animation-name: slideInLeft;
}
</style>
