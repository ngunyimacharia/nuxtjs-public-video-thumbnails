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
          <img 
            class="h-56 w-full object-cover lg:absolute lg:h-full" 
            :src="thumbnail ? thumbnail : placeholderThumbnail" 
            alt="Public video thumbnail"
          />
        </div>
      </div>
      <div class="relative py-16 px-4 sm:py-24 sm:px-6 lg:px-8 lg:max-w-7xl lg:mx-auto lg:py-32 lg:grid lg:grid-cols-2">
        <div class="lg:pr-8">
          <div class="max-w-md mx-auto sm:max-w-lg lg:mx-0">
            <form @reset="thumbnail = null" @submit.prevent="submit" class="mt-9 grid grid-cols-1 gap-y-6 sm:grid-cols-2 sm:gap-x-8">
              <div class="sm:col-span-2">
                <label for="type" class="block text-sm font-medium text-gray-700">Type</label>
                <div class="mt-1">
                  <select required v-model="form.type" id="type" name="type" type="text" class="block w-full shadow-sm sm:text-sm focus:ring-grape-500 focus:border-grape-500 border-gray-300 rounded-md">
                    <option v-for="type in types" :value="type.value" :key="type.value">
                      {{type.text}}
                    </option>
                  </select>
                </div>
              </div>
              <div class="sm:col-span-2">
                <label for="identifier" class="block text-sm font-medium text-gray-700">Identifier (URL or unique identifier)</label>
                <div class="mt-1">
                  <input v-model="form.identifier" required type="text" name="identifier" id="identifier" class="block w-full shadow-sm sm:text-sm focus:ring-grape-500 focus:border-grape-500 border-gray-300 rounded-md">
                </div>
              </div>
              <div class="text-right sm:col-span-2">
                <button type="submit" class="inline-flex items-center px-3 py-2 border border-transparent text-sm leading-4 font-medium rounded-md shadow-sm text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
                  Submit
                </button>
                <button type="reset" class="inline-flex items-center px-3 py-2 border border-transparent text-sm leading-4 font-medium rounded-md text-indigo-700 bg-indigo-100 hover:bg-indigo-200 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
                  Reset
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
  name: 'IndexPage',
  data(){
    return {
      types:[
        {text:"YouTube", value:"youtube"}, 
        {text:"Hulu", value:"hulu"}, 
        {text:"Vimeo", value:"vimeo"}, 
        {text:"Animoto", value:"animoto"}, 
        {text:"World Star HipHop", value:"worldstarhiphop"}, 
        {text:"Daily Motion", value:"dailymotion"}
      ],
      form:{
        type:null,
        identifier:null
      },
      placeholderThumbnail:'https://via.placeholder.com/850x500?text=Public+video+thumbnail',
      thumbnail: null
    }
  },
  methods:{
    submit(){
      this.thumbnail = this.$cloudinary.image
                .url( this.form.identifier, {type: this.form.type} );
    }
  }
}
</script>
