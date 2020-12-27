<template>
      <div class="flex items-center">
          <div class="flex-shrink-0 sm:mr-2">
            <div class="flex items-center justify-center h-12 w-12 rounded-md bg-indigo-500 text-white">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"></path></svg>
            </div>
          </div>
          <div class="ml-4">
            <dt class="flex text-lg leading-6 font-medium text-gray-900">
                {{title}}
            </dt>
            <dd class="mt-2 text-base text-gray-500">
              <slot></slot>
            </dd>
          </div>
        </div>
</template>
<script>
export default {
      props:{
            title:{
                  type:String,
            },
      }
}
</script>