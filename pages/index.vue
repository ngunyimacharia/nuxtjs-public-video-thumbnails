<template>
<div class="bg-white">
  <main>
    <!-- Header -->
    <div class="py-24 bg-gray-50 sm:py-32">
      <div class="max-w-md mx-auto pl-4 pr-8 sm:max-w-lg sm:px-6 lg:max-w-7xl lg:px-8">
        <h1 class="text-4xl leading-10 font-extrabold tracking-tight text-gray-900 text-center sm:text-5xl sm:leading-none lg:text-6xl">Public video thumbnails</h1>
        <p class="mt-6 max-w-3xl mx-auto text-xl leading-normal text-gray-500 text-center">
          Let us fetch thumbnails of public videos from the internet
        </p>
      </div>
    </div>

    <!-- Form Section -->
    <div class="relative bg-white">
      <div class="lg:absolute lg:inset-0">
        <div class="lg:absolute lg:inset-y-0 lg:right-0 lg:w-1/2">
          <img class="h-56 w-full object-cover lg:absolute lg:h-full" src="https://images.unsplash.com/photo-1556761175-4b46a572b786?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1567&q=80" alt="">
        </div>
      </div>
      <div class="relative py-16 px-4 sm:py-24 sm:px-6 lg:px-8 lg:max-w-7xl lg:mx-auto lg:py-32 lg:grid lg:grid-cols-2">
        <div class="lg:pr-8">
          <div class="max-w-md mx-auto sm:max-w-lg lg:mx-0">
            <form action="#" method="POST" class="mt-9 grid grid-cols-1 gap-y-6 sm:grid-cols-2 sm:gap-x-8">
              <div class="sm:col-span-2">
                <label for="type" class="block text-sm font-medium text-gray-700">Type</label>
                <div class="mt-1">
                  <input id="type" name="type" type="text" class="block w-full shadow-sm sm:text-sm focus:ring-grape-500 focus:border-grape-500 border-gray-300 rounded-md">
                </div>
              </div>
              <div class="sm:col-span-2">
                <label for="identifier" class="block text-sm font-medium text-gray-700">Identifier (URL or unique identifier)</label>
                <div class="mt-1">
                  <input type="text" name="identifier" id="identifier" class="block w-full shadow-sm sm:text-sm focus:ring-grape-500 focus:border-grape-500 border-gray-300 rounded-md">
                </div>
              </div>
              <div class="text-right sm:col-span-2">
                <button type="submit" class="inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-grape-600 hover:bg-grape-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-grape-500">
                  Submit
                </button>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </main>
</div>

</template>

<script>
export default {
  name: 'IndexPage'
}
</script>
