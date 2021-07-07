<template>
  <div class="md:w-1/4 w-full px-3 md:px-0">
    <div class="bg-white mb-6 pb-6">
      <div class="h-48 bg-card rounded-t-lg pt-6">
        <span class="text-primary">Add cover photo</span>
      </div>
      <div class="flex justify-center -mt-24">
        <img class="rounded flex items-center justify-center... w-36 h-36" src="../../assets/img/ellipse.png"/>
      </div>
      <div class="font-bold text-xl">Emily Chan</div> 
      <div class="text-sm">Designer | creative team</div> 
    </div>
    <div class="bg-white p-6">
      <div class="flex">
        <div class="w-1/2">
          <div class="font-semibold">Suggested People</div>
        </div>
        <div class="w-1/2 flex justify-end">
          <button class="focus:outline-none">
            <img class="w-5" src="../../assets/img/refresh.svg" />
          </button>
        </div>
      </div>
      <div v-for="item in suggested" :key="item.name" class="flex mt-6 pb-3 border-b w-full">
        <div class="flex w-3/4">
          <div>
            <img class="w-12" :src="require(`@/assets/img/${item.img}`)" />
          </div>
          <div class="pl-3 text-left">
            <div class="font-semibold">{{ item.name }}</div>
            <div class="text-xs">{{ item.position }}</div>
            <div class="text-xs">{{ item.team }}</div>
          </div>
        </div>
        <div class="flex w-1/4 justify-end">
          <button class="focus:outline-none">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-primary" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6" />
            </svg>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      suggested: [
        {
          name: 'People 1',
          position: 'Senior Manager',
          team: 'Development Team',
          img: 'suggested1.png',
        },
        {
          name: 'People 2',
          position: 'Senior Manager',
          team: 'Development Team',
          img: 'suggested2.png',
        },
        {
          name: 'People 3',
          position: 'Senior Manager',
          team: 'Development Team',
          img: 'suggested3.png',
        },
        {
          name: 'People 4',
          position: 'Senior Manager',
          team: 'Development Team',
          img: 'suggested4.png',
        },
        {
          name: 'People 5',
          position: 'Senior Manager',
          team: 'Development Team',
          img: 'suggested5.png',
        },
      ]
    }
  }
}
</script>