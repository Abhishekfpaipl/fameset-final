<template>
  <DashboardNav />
  <router-view />
  <FooterBar v-if="!hidden" />
</template>
<script>
import DashboardNav from "@/components/DashboardNav.vue";
import FooterBar from "@/components/FooterBar.vue";
export default {
  name: "App",
  components: {
    DashboardNav,
    FooterBar,
  },
  computed: {
    hidden() {
      const hiddenPages = ['DigitalCard']
      return hiddenPages.includes(this.$route.name)
    },
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.brand-bg {
  background: linear-gradient(90deg, rgba(24, 13, 0, 1) 0%, rgba(47, 28, 8, 1) 50%, rgba(24, 13, 0, 1) 100%);
}

.top-padding {
  padding-top: 70px;
}

.brand-btn:hover {
  background-color: gold !important;
  color: black !important;
}

.brand-btn {
  border: 1px solid gold !important;
}

.form-control {
  box-shadow: none !important;
}

.form-control:focus {
  border-color: white !important;
}

.method1 {
  background: linear-gradient(90deg, rgba(254, 242, 159, 1) 0%, rgba(210, 163, 73, 1) 50%, rgba(254, 242, 159, 1) 100%);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}

:root {
  --bg-primary: #014c75;
  --bg-secondary: #EB5E28;
  --bg-tertiary: #FEC007;
  --bg-forth: #FBF4F4;
  --brand-color: #F5C518 !important;
  --bg-glow: linear-gradient(90deg, rgba(254, 242, 159, 1) 0%, rgba(210, 163, 73, 1) 50%, rgba(254, 242, 159, 1) 100%) !important;
}

.text-ellipsis {
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}

.text-ellipsis2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}

.text-ellipsis3 {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}

.text-ellipsis4 {
  display: -webkit-box;
  -webkit-line-clamp: 4;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}

.text-ellipsis5 {
  display: -webkit-box;
  -webkit-line-clamp: 5;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;

}

.text-ellipsis7 {
  display: -webkit-box;
  -webkit-line-clamp: 7;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}

.smaller {
  font-size: 12px !important;
}

#scroll::-webkit-scrollbar {
  display: none;
}

.bill {
  overflow: hidden;
  text-align: center;
}

.bill>span {
  position: relative;
  display: inline-block;
}

.bill>span:before,
.bill>span:after {
  content: "";
  position: absolute;
  top: 50%;
  width: 900px;
  /* Adjust width as needed */
  margin: 0 20px;
}

.bill>span:before {
  right: 100%;
  border-bottom: 2px solid;
  border-image: linear-gradient(to left, black 0, transparent 10%);
  border-image-slice: 1;
}

.bill>span:after {
  left: 100%;
  border-bottom: 2px solid;
  border-image: linear-gradient(to right, black 0, transparent 10%);
  border-image-slice: 1;
}

@keyframes slideTop {

  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(5px);
  }
}

.slide {
  display: inline-block;
  animation: slideTop 1.5s ease-in-out infinite;
}


.before-enter {
  opacity: 0;
  transform: translateY(80px);
  transition: opacity 1.5s ease-out, transform 1.5s ease-out;
}

.enter {
  opacity: 1;
  transform: translateY(0);
}

@keyframes rotate {

  0%,
  100% {
    transform: scale(1);
  }

  50% {
    transform: scale(1.15);
  }
}

.rotate {
  display: inline-block;
  animation: rotate 1.5s ease-in-out infinite;
} 
@keyframes shake {
    0% {
        transform: translateX(0);
    }

    25% {
        transform: translateX(-10px);
    }

    50% {
        transform: translateX(10px);
    }

    75% {
        transform: translateX(-10px);
    }

    100% {
        transform: translateX(0);
    }
} 
.icon-shake:hover {
    animation: shake 0.5s ease-in-out;
    animation-iteration-count: 1;
}
</style>
