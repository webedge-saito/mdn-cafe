<template>
    <header class="w-full absolute md:static bg-black px-2 py-2 z-50">
      <div class="md:max-w-3xl mx-auto px-6">
        <div
         class="w-full md:flex mx-auto md:px-0 flex justify-between items-center h-16"
        >
          <h1>
            <a 
             class="text-white text-sm font-bold leading-relaxed inline-block mr-4 py-2 whitespace-no-wrap"
             href="/"
            >
              MdN Cafe
            </a>
          </h1>
          <div class="text-white">
            <button class="focus:outline-none" v-if="!isOpen" @click="isOpen = true">
              <svg class="h-6 w-6 fill-current" viewBox="0 0 24 24">
                <path
                 d="M24 6h-24v-4h24v4zm0 4h-24v4h24v-4zm0 8h-24v4h24v-4z"
                />
              </svg>
            </button>
            <button class="focus:outline-none" v-else @click="isOpen = false">
              <svg class="h-6 w-6 fill-current" viewBox="0 0 24 24">
                <path
                  d="M24 20.188l-8.315-8.209 8.2-8.282-3.697-3.697-8.212 8.318-8.31-8.203-3.666 3.666 8.321 8.24-8.206 8.313 3.666 3.666 8.237-8.318 8.285 8.203z"
                />
              </svg>
            </button>
          </div>
        </div>
        <transition name="fade" mode="out-in">
          <nav
            class="w-full absolute left-0 bg-black z-20" v-if="isOpen"   
          >
          <ul class="md:max-w-3xl mx-auto">
            <li class="w-full">
              <a 
              href="/concept/"
              class="text-white inline-block py-6 px-6 w-full"
              >コンセプト</a>
            </li>
            <li class="w-full">
              <a 
              href="/shop/"
              class="text-white inline-block py-6 px-6 w-full"
              >店舗情報</a>
            </li>
            <li class="w-full">
              <a 
              href="/menu/"
              class="text-white inline-block py-6 px-6 w-full"
              >メニュー</a>
            </li>
            <li class="w-full">
              <a 
              href="/information/"
              class="text-white inline-block py-6 px-6 w-full"
              >お知らせ</a>
            </li>
          </ul>
          </nav>
        </transition>
      </div>
    </header>
</template>

<script>
export default {
    name: 'LayoutHeader',
    data() {
        return {
            isOpen: false,
        }
    },
}
</script>

<style lang="css">
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>