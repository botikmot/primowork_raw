<template>
  <div class="home max-w-none mx-auto lg:max-w-7xl">
    <div class="text-left mt-16 px-3 md:px-0">
      <span class="text-3xl font-semibold">Engage</span>
    </div>
    <div class="block md:flex mt-10 px-3 md:px-0">
        <div class="md:w-3/5 w-full">
          <div class="font-bold text-xl text-primary text-left py-3">Announcement</div>
          <div>
            <img class="flex items-center justify-center..." src="../assets/img/Component.png" />
          </div>
        </div>
        <div class="md:w-2/5 w-full">
          <div class="py-3 flex justify-end">
            <span class="text-sm pr-3 pt-1">View all</span>
            <div class="cursor-pointer">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-7 w-7 text-primary" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm1-11a1 1 0 10-2 0v2H7a1 1 0 100 2h2v2a1 1 0 102 0v-2h2a1 1 0 100-2h-2V7z" clip-rule="evenodd" />
              </svg>
            </div>
          </div>
          <div class="text-left bg-white">
            <div class="absolute">
              <img class="" src="../assets/img/component_1.png" />
            </div>
            <div v-for="(item, i) in announcements" :key="item.dept" class="px-6 py-3">
              <div @mouseover="show[i] = true" @mouseleave="show[i] = false" class="border-b pb-4">
                <div class="flex">
                  <span class="text-sm w-1/2 pt-2 font-semibold">{{ item.dept }}</span>
                  <div class="flex w-1/2 justify-end">
                    <div :class="`${show[i] ? '': 'hide'} flex`">
                      <div class="p-2  rounded-full hover:bg-gray-200 cursor-pointer">
                        <img class="w-5" src="../assets/img/pencil.svg" />
                      </div>
                      <div class="p-2  rounded-full hover:bg-gray-200 cursor-pointer">
                        <img class="w-5" src="../assets/img/share.svg" />
                      </div>
                    </div>
                    <div class="p-2  rounded-full hover:bg-gray-200 cursor-pointer">
                      <img v-if="!show[i]" class="w-5" src="../assets/img/paperclip.svg" />
                      <img v-else class="w-5" src="../assets/img/pushpin.svg" />
                    </div>
                  </div>
                </div>
                <div class="font-semibold pt-2 truncate">{{ item.title }}</div>
                <div class="font-semibold text-xs truncate pt-1">{{ item.subtitle }}</div>
                <div class="text-xs pt-3">{{ item.date }}</div>
              </div>
            </div>
            <div class="flex justify-end w-full px-6 py-2">
              <span class="text-sm">
              <a class="px-2 text-primary" href="#">1</a>|
              <a class="px-2" href="#">2</a>|
              <a class="px-2" href="#">3</a>
              </span>
            </div>
          </div>
        </div>
    </div>
    <div class="mt-14">
      <div class="font-bold text-xl text-primary text-left px-3 md:px-0">New section name TBC</div>
      <div class="md:flex mt-3">
        <SideSection />
        <NewsFeed />
      </div>
    </div>
  </div>
</template>

<script>
import { SideSection, NewsFeed } from '@/components/layouts/'

export default {
  name: 'Home',
  components: {
    SideSection,
    NewsFeed
  },
  data () {
    return {
      show: [],
      dropdownOpen: false,
      announcements: [
        {
          dept: 'Department 3',
          title: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod..',
          subtitle: 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque..',
          date: '2021.05.20, 9:36am',
        },
        {
          dept: 'Department 4',
          title: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod..',
          subtitle: 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque..',
          date: '2021.05.20, 9:36am',
        },
        {
          dept: 'Department 5',
          title: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod..',
          subtitle: 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque..',
          date: '2021.05.20, 9:36am',
        },
      ],
      
    }
  },
}
</script>

<style scoped>
.hide {
  display: none;
}
</style>
