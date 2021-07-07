<template>
  <div>
    <div class="p-3 bg-white h-16">
      <div class="max-w-none mx-auto lg:max-w-7xl flex">
        <div class="flex w-1/3">
          <span class="cursor-pointer">
            <img class="flex items-center justify-center..." src="../../assets/img/primowork.png" width="180"/>
          </span>
        </div>
        <div class="flex w-2/3 justify-end ...">
          <div class="pr-4 hidden sm:flex">
            <button class="bg-primary hover:bg-blue-700 text-white py-2 px-4 rounded text-sm">
              Invite members
            </button>
          </div>
          <div class="pr-4 pt-2">
            <button class="focus:outline-none">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9" />
              </svg>  
            </button>
          </div>
          <div class="pr-4 pt-2">
            <button class="focus:outline-none">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" />
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
              </svg>  
            </button>
          </div>
          <div class="flex cursor-pointer">
            <div class="pr-2">
                <span>
                <img class="rounded flex items-center justify-center..." src="../../assets/img/ellipse.png" width="40" height="40"/>
                </span>  
            </div>
            <div class="hidden md:flex">
                <button class="focus:outline-none">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-primary" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
                    </svg>
                </button>
            </div>
          </div>
          <div class="xl:hidden pt-2 pl-3">
            <button class="focus:outline-none" @click="toggle">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
              </svg>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      toggleSidebar: false,
    }
  },
  methods: {
    toggle() {
        this.toggleSidebar = !this.toggleSidebar
        this.$emit('toggleSidebar', this.toggleSidebar)
    }
  }
}
</script>