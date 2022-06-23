<template>
   <div class="h-1/2 lg:h-screen bg-gradient-to-t from-indigo-200 relative">
       <nav class="w-full fixed top-0 bg-white">
           <div class="container mx-auto py-5 flex justify-between items-center">
               <div class="flex items-center gap-2">
                <img class="w-8" src="/logo.png" alt="" />
                <span class="text-2xl text-indigo-900 font-bold">Markeys.</span>
               </div>
               <ul class="hidden md:flex space-x-10 text-gray-600 font-md text-sm uppercase">
                  <li class="hover:text-gray-500" v-for="navItem in navItems" :key="navItem.text"><nuxt-link :to="navItem.link">{{navItem.text}}</nuxt-link></li>
               </ul>
              <div class="hidden md:flex"><button class="ring-1  shadow-sm rounded-md px-5 py-2 text-sm">My Resume</button></div>
              <div class="md:hidden cursor-pointer space-y-1 z-20" @click="toggleNavbar">
                  <div class="w-6 h-0.5 bg-black"></div>
                  <div class="w-6 h-0.5 bg-black"></div>
                  <div class="w-6 h-0.5 bg-black"></div>
              </div>
              <ul v-if="showNav" class="absolute top-0 left-0 w-full p-10 rounded-b-3xl space-y-10 bg-indigo-500">
                  <li class="text-white text-center" v-for="navItem in navItems" :key="navItem.text"><nuxt-link :to="navItem.link">{{navItem.text}}</nuxt-link></li>
              </ul>
           </div>
       </nav>
       <p>Hello world</p>
   </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data(){
    return {
      showNav : false,
      navItems : [
        {text : 'Work', link : '/#'},
        {text : 'Contributions', link : '/#'},
        {text : 'Talks', link : '/#'},
        {text : 'Community', link : '/#'},
        {text : 'Contact me', link : '/#'},
      ]
    }
  },
  methods : {
    toggleNavbar(){
       this.showNav = !this.showNav
    }
  }
}
</script>
