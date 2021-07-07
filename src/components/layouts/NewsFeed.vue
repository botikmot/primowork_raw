<template>
  <div class="md:w-3/4 px-6 w-full">
          <div class="flex">
            <button v-if="!searchEnable" @click="togglePost = !togglePost" class="bg-primary text-white py-2 px-4 rounded w-11/12">
              <div class="flex">
                <div class="w-3/4 text-left">What's in your mind?</div>
                <div class="w-1/4 flex justify-end">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z" />
                  </svg>
                </div>
              </div>
            </button>
            <div v-else class="flex w-11/12">
              <div class="text-left pr-3">
                <select class="p-2">
                  <option class="p-2">People</option>
                  <option class="p-2">Post</option>
                  <option class="p-2">Job title</option>
                  <option class="p-2">Department</option>
                </select>
              </div>
              <div class="w-11/12 border-l">
                <input class="bg-white appearance-none rounded w-full py-3 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-purple-500" id="inline-full-name" type="search" placeholder="Enter name, job title or post title">
              </div>
            </div>
            <button @click="searchEnable = !searchEnable" class="bg-primary text-white py-2 px-4 rounded ml-6">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
              </svg>
            </button>
          </div>
          <div v-if="newsfeeds.length === 0" class="mt-6 bg-white p-6">
            <div class="my-36">
              <div class="flex justify-center">
                <img class="" src="../../assets/img/address-card.svg" />
              </div>
              <div class="font-bold text-2xl text-primary mt-3">Welcome to News feed!</div>
              <div class="w-1/2 mx-auto">Write your first post and follow your workmate so you are up to update</div>
            </div>
          </div>
          <div v-else class="mt-6 bg-white p-6">
             <div class="flex border-b pb-3 border-primary">
                <div class="w-3/4 font-bold text-xl text-left">News feed</div>
                <div class="w-1/4 flex justify-end">
                  <button class="focus:outline-none text-xs bg-transparent flex">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-primary" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h7" />
                    </svg>
                    <span class="pl-3 pt-1">Sort by</span>
                   </button>
                </div>
             </div>
             <div v-for="(item, i) in newsfeeds" :key="i" class="mt-3 my-6 py-6 border-b">
                <div class="flex w-full">
                    <div class="flex w-3/4">
                        <div>
                            <img class="w-12" src="../../assets/img/ellipse.png" />
                        </div>
                        <div class="pl-3 text-left">
                            <div class="font-semibold">Emily Chan <span class="text-xs font-light">.20m</span></div>
                            <div class="text-xs">Senior Manager, Development team</div>
                        </div>
                    </div>
                    <div class="flex w-1/4 justify-end">
                        <button class="focus:outline-none">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h.01M12 12h.01M19 12h.01M6 12a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0z" />
                            </svg>
                        </button>
                    </div>
                </div>
                <div class="text-left w-full pt-3 pl-3">
                   {{ item.post }}
                </div>
                <div class="mt-3 w-full flex justify-center">
                   <img class="flex max-h-60 items-center justify-center..." :src="item.img" />
                </div>
                <div class="flex mt-3 pl-6">
                  <div class="flex pr-3">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-gray-400" viewBox="0 0 20 20" fill="currentColor">
                      <path fill-rule="evenodd" d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z" clip-rule="evenodd" />
                    </svg>
                    <span class="text-gray-400 pl-1">20</span>
                  </div>
                  <div class="flex pr-3">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-gray-400" viewBox="0 0 20 20" fill="currentColor">
                      <path fill-rule="evenodd" d="M18 5v8a2 2 0 01-2 2h-5l-5 4v-4H4a2 2 0 01-2-2V5a2 2 0 012-2h12a2 2 0 012 2zM7 8H5v2h2V8zm2 0h2v2H9V8zm6 0h-2v2h2V8z" clip-rule="evenodd" />
                    </svg>
                    <span class="text-gray-400 pl-1">20</span>
                  </div>
                  <div class="flex pr-3">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-gray-400" viewBox="0 0 20 20" fill="currentColor">
                      <path fill-rule="evenodd" d="M7.707 3.293a1 1 0 010 1.414L5.414 7H11a7 7 0 017 7v2a1 1 0 11-2 0v-2a5 5 0 00-5-5H5.414l2.293 2.293a1 1 0 11-1.414 1.414l-4-4a1 1 0 010-1.414l4-4a1 1 0 011.414 0z" clip-rule="evenodd" />
                    </svg>
                    <span class="text-gray-400 pl-1">20</span>
                  </div>
                </div>
                <div class="mt-3 flex pl-3 pr-6">
                    <div class="pr-3">
                        <img class="w-10" src="../../assets/img/ellipse.png" />
                    </div>
                    <div class="w-full">
                      <!--<input class="appearance-none block w-full text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"  type="text" placeholder="Add a comment">-->
                      <div class="flex flex-wrap items-stretch w-full relative h-15 bg-white mb-4 rounded border border-gray-200">
                        <input type="text"
                          class="flex-shrink flex-grow text-sm flex-auto leading-normal w-px h-10 px-3 relative focus:outline-none"
                          placeholder="Add a comment"
                        />
                        <div class="flex pt-2 pr-3">
                          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-gray-500" viewBox="0 0 20 20" fill="currentColor">
                            <path d="M10.894 2.553a1 1 0 00-1.788 0l-7 14a1 1 0 001.169 1.409l5-1.429A1 1 0 009 15.571V11a1 1 0 112 0v4.571a1 1 0 00.725.962l5 1.428a1 1 0 001.17-1.408l-7-14z" />
                          </svg>
                        </div>
                    </div>
                    </div>
                </div>
             </div>
          </div>
        </div>
      <!-- Modal Post -->
    <div v-if="togglePost" class="fixed overflow-x-hidden overflow-y-auto inset-0 flex z-50 justify-center items-center">
      <div class="relative mx-auto w-full lg:w-2/6">
        <div class="bg-white w-full rounded-lg p-12">
        <div class="font-bold text-xl text-primary text-left">Create Post</div>
          <div class="flex mt-6">
            <div class="flex w-1/2">
              <div>
                <img class="w-12" src="../../assets/img/ellipse.png" />
              </div>
              <div class="pl-3 text-left pt-3">
                <div class="font-semibold">Emily Chan</div>
              </div>
            </div>
            <div class="w-1/2 flex justify-end">
              <select class="p-2">
                <option class="text-primary" value="" disabled selected>Share with</option>
                <option class="p-2">Everyone</option>
                <option class="p-2">Department</option>
                <option class="p-2">Followers</option>
              </select>
            </div>
          </div>
          <div class="mt-3">
            <textarea v-model="post" class="resize border rounded-md w-full p-3" rows="4" placeholder="What's on your mind?"></textarea>
          </div>
          <div class="mt-3">
            <input
              ref="imageInput"
              type="file"
              style="display: none"
              accept="image/*"
              @change="updatePreview"
            />
            <button @click="$refs.imageInput.click()" class="border text-gray-500 py-2 px-4 rounded w-full">
              <div class="flex">
                <div class="w-3/4 text-left">Add to your post</div>
                <div class="w-1/4 flex justify-end">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z" />
                  </svg>
                </div>
              </div>
            </button>
          </div>
          <div class="p-3 flex justify-center">
            <img :src="imagePreview" class="w-40"/>
          </div>
          <div class="flex justify-end mt-6">
            <button @click="togglePost = false" class="bg-transparent hover:bg-green-200 text-green-500 py-2 px-4 border border-green-500 hover:border-transparent rounded-lg">
              Cancel
            </button>
            <button @click="confirmPost" class="bg-green-500 hover:bg-green-200 text-white py-2 px-4 hover:border-transparent rounded-lg ml-3">
              Confirm
            </button>
          </div>
        </div>
      </div>
    </div>
    <div v-if="togglePost" class="fixed inset-0 z-40 opacity-25 bg-black"></div>
</template>

<script>
export default {
  data () {
    return {
      togglePost: false,
      searchEnable: false,
      imagePreview: null,
      post: '',
      newsfeeds: [],
    }
  },
  methods: {
    updatePreview(e) {
      const files = e.target.files
      if (files.length === 0) {
        return
      }
      const reader = new FileReader()
      reader.onload = (e) => {
        this.imagePreview = e.target.result
      }
      reader.readAsDataURL(files[0])
    },
    confirmPost() {
       const d = new Date()
       let post = {
         username: 'Emily Chan',
         post: this.post,
         time: d.getMinutes(),
         img: this.imagePreview,
         comments: '14',
         likes: '50',
         reply: '15'
       }
       console.log(post)
       this.newsfeeds.unshift(post)
       this.imagePreview = null
       this.post = ''
       this.togglePost = false
       this.$toast.success(`Post has been created! `)
    }
  },
}
</script>