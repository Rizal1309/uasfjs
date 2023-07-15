<template>
  <Header></Header>
  <div class="container mx-auto mt-8">
    <div class="relative overflow-x-auto">
      <button
        type="button"
        class="text-white bg-green-500 hover:bg-green-600 focus:outline-none focus:ring-4 focus:ring-green-100 font-medium rounded-full text-sm px-5 py-2.5 text-center mr-2 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800"
      >
        <NuxtLink to="/matakuliah/CreateData">Tambah Data</NuxtLink>
      </button>
      <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
        <thead
          class="text-xs text-gray-700 uppercase bg-sky-500 dark:bg-gray-700 dark:text-gray-400"
        >
          <tr>
            <th scope="col" class="text-base px-6 py-3">Id</th>
            <th scope="col" class="text-base px-6 py-3">Mata Kuliah</th>
            <th scope="col" class="text-base px-6 py-3">Total SKS</th>
            <th scope="col" class="text-base px-6 py-3">Detail</th>
          </tr>
        </thead>
        <tbody>
          <tr
            class="bg-white dark:bg-gray-800"
            v-for="mk in Matakuliah"
            :key="mk.id"
          >
            <th
              scope="row"
              class="px-6 py-4 font-medium text-gray-900 whitespace-nowrap dark:text-white"
            >
              {{ mk.id }}
            </th>
            <td class="text-base px-6 py-4">{{ mk.matakuliah }}</td>
            <td class="text-base px-6 py-4">{{ mk.sks }}</td>
            <td class="text-base px-6 py-4">
              <button
                type="button"
                class="text-white bg-red-700 hover:bg-red-800 focus:outline-none focus:ring-4 focus:ring-red-300 font-medium rounded-full text-sm px-5 py-2.5 text-center mr-2 mb-2 dark:bg-red-600 dark:hover:bg-red-700 dark:focus:ring-red-900"
              >
                <svg
                  class="w-6 h-6 text-gray-800 dark:text-white"
                  aria-hidden="true"
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 12 20"
                >
                  <path
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M10.335 6.514 6.91 1.464a1.122 1.122 0 0 0-1.818 0l-3.426 5.05a.988.988 0 0 0 .91 1.511h6.851a.988.988 0 0 0 .91-1.511Zm-8.67 6.972 3.426 5.05a1.121 1.121 0 0 0 1.818 0l3.426-5.05a.988.988 0 0 0-.909-1.511H2.574a.987.987 0 0 0-.909 1.511Z"
                  />
                </svg>
              </button>
              <button
                type="button"
                class="text-white bg-yellow-400 hover:bg-yellow-500 focus:outline-none focus:ring-4 focus:ring-yellow-300 font-medium rounded-full text-sm px-5 py-2.5 text-center mr-2 mb-2 dark:focus:ring-yellow-900"
              >
                <NuxtLink :to="`/matakuliah/${mk.id}`"
                  ><svg
                    class="w-6 h-6 text-gray-800 dark:text-white"
                    aria-hidden="true"
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    viewBox="0 0 8 14"
                  >
                    <path
                      stroke="currentColor"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M7 1 1.3 6.326a.91.91 0 0 0 0 1.348L7 13"
                    />
                  </svg>
                </NuxtLink>
              </button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
  <Footer></Footer>
</template>
<script setup>
definePageMeta({
  layout: "matkul",
});
const { data: Matakuliah } = await useFetch(
  "https://64abc8e39edb4181202e87b6.mockapi.io/akademik/v1/matakuliah"
);
</script>
