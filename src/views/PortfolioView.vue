<script>
export default {
  data() {
    return {
      activeTab: 1,
      items: [
        {
          id: 1,
          name: 'Photo 1',
          imageUrl: '1',
          status: 'My personal website, I created this website to display my profile, skills and projects. As well as my place to try new technology.',
          tech: 'VueJS 3, Tailwind',
          github: 'https://github.com/rakha-elctrnx/Portofolio-v2',
          demo: 'https://bagasrakha.netlify.app/'
        },
        {
          id: 2,
          name: 'Photo 2',
          imageUrl: '2',
          status: 'A website that has a responsive display to make it easier for Muslims to read the Quran from anywhere.',
          tech: 'VueJS 3, Tailwind',
          github: 'https://github.com/rakha-elctrnx/muslim-companion',
          demo: 'https://sahabat-muslim.netlify.app/'
        },
        {
          id: 3,
          name: 'Photo 3',
          imageUrl: '3',
          status: 'Sistem Informasi dan Teknologi Desa, a web application to assist village government work in administration, population data management, community services, etc.',
          tech: 'Laravel 9, Bootstrap',
          github: 'null',
          demo: 'null'
        },
        {
          id: 4,
          name: 'Photo 4',
          imageUrl: '4',
          status: 'a web application used by village-owned enterprises at the sub-district level to make it easier for them in terms of accounting that is equipped with a microfinance balance.',
          tech: 'Laravel 8, Bootstrap',
          github: 'null',
          demo: 'null'
        },
        {
          id: 5,
          name: 'Photo 5',
          imageUrl: '5',
          status: 'Sistem Percepatan Pelayanan Surat Elektronik, A web application to manage letters in the village.',
          tech: 'Codeigniter 3, Bootstrap',
          github: 'null',
          demo: 'null'
        },
        {
          id: 6,
          name: 'Photo 6',
          imageUrl: '6',
          status: 'My personal website, I created this website to display my profile, skills and projects. As well as my place to try new technology.',
          tech: 'VueJS 3, Tailwind',
          github: 'https://github.com/rakha-elctrnx/Portofolio-v2',
          demo: 'https://bagasrakha.netlify.app/'
        },
        {
          id: 7,
          name: 'Photo 7',
          imageUrl: '7',
          status: 'A website that has a responsive display to make it easier for Muslims to read the Quran from anywhere.',
          tech: 'VueJS 3, Tailwind',
          github: 'https://github.com/rakha-elctrnx/muslim-companion',
          demo: 'https://sahabat-muslim.netlify.app/'
        },
        {
          id: 8,
          name: 'Photo 8',
          imageUrl: '8',
          status: 'Sistem Informasi dan Teknologi Desa, a web application to assist village government work in administration, population data management, community services, etc.',
          tech: 'Laravel 9, Bootstrap',
          github: 'null',
          demo: 'null'
        },
        {
          id: 9,
          name: 'Photo 9',
          imageUrl: '9',
          status: 'a web application used by village-owned enterprises at the sub-district level to make it easier for them in terms of accounting that is equipped with a microfinance balance.',
          tech: 'Laravel 8, Bootstrap',
          github: 'null',
          demo: 'null'
        },
        {
          id: 10,
          name: 'Photo 10 ',
          imageUrl: '10',

        },

        {
          id: 12,
          name: 'Photo 11 ',
          imageUrl: '12',

        },
        {
          id: 13,
          name: 'Photo 12 ',
          imageUrl: '13',

        }

      ],
      showModal: false,
      isLoading: false,
      selectedImageUrl: null,
    };

  },
  
  methods: {
    openModal(imageUrl) {
      this.isLoading = true; // Aktifkan loading
      this.selectedImageUrl = imageUrl;
      this.showModal = true;
    },
    imageLoaded() {
      this.isLoading = false; // Nonaktifkan loading setelah gambar dimuat
    }
  }
}
</script>
<template>
  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-amber-50 mx-3">
    <div v-if="showModal" class="modal" @click="showModal = false">
    <div class="modal-content" @click.stop>
      <span class="close" @click="showModal = false">&times;</span>
      <!-- Tampilkan loading saat isLoading true -->
      <div v-if="isLoading" class="loading-overlay">
    <div class="loading-spinner">Loading...</div>
  </div>
      <!-- Gunakan event @load pada img untuk memanggil imageLoaded -->
      <img :src="selectedImageUrl" alt="Selected Image" class="modal-image" @load="imageLoaded">
    </div>
  </div>
    <article data-page="about">
      <header>
        <div
          class="text-2xl font-bold text-white mb-10 fadein-bot title-section flex items-center justify-center flex-col">
          <!-- <div class="h-[1px] w-10 bg-amber-200 md:w-20 aos-init aos-animate"></div> -->
          <h4>RESULT MY PHOTO</h4>
          <h4 class="text-base font-normal text-transparent bg-clip-text bg-gradient-to-r from-slate-100 to-blue-500">
            Explore the result Photo I've worked on so far</h4>
        </div>
      </header>
      <section>
        <div>
          
          <div
            class="grid grid-cols-1 gap-4 pb-32 md:grid-cols-3 md:gap-3 xl:grid-cols-3 xl:gap-3 2xl:gap-5 fade-zoom-in">
            <div v-for="item in items" :key="item.id">
              <div
                class="item-card flex flex-col items-center gap-2 rounded bg-[#1e1e1f] hover:bg-[#282828] border border-[#383838] text-amber-50 md:gap-3 px-5 py-5 lg:px-5 ">
                <div class="flex items-center justify-center p-0 h-full w-full lg:p-0 zoom-in">
                  <img alt="HTML" loading="lazy" decoding="async" data-nimg="1" class="drop-shadow-xl rounded-xl"
                    :src="'/img/' + item.imageUrl + '.jpg'" @click="openModal('/img/' + item.imageUrl + '.jpg')">
                </div>

                <div class="w-full flex flex-col gap-2 items-center text-sm md:text-base lg:text-lg">
                  <div class="title-text font-medium text-secondary">{{ item.name }}
                  </div>

                  <div class="w-full flex justify-end">

                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </article>
  </div>
</template>

<style>
.item-card:hover {
  transition: transform 0.3s ease;
  transform: translateY(-8px);
}

.modal {
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgba(0, 0, 0, 0.5);
}

.modal-content {
  background-color: #fefefe;
  margin: 15% auto;
  padding: 20px;
  border: 1px solid #888;
  width: 80%;
  position: relative;
}

.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}

.modal-image {
  max-width: 100%;
  height: auto;
}
.loading {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%; /* Sesuaikan dengan kebutuhan */
}

svg:hover {
  stroke: #ffdb70;
}

@keyframes fadeZoomIn {
  0% {
    opacity: 0;
    transform: scale(0.5);
  }

  100% {
    opacity: 1;
    transform: scale(1);
  }
}
.loading-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 9999;
  display: flex;
  justify-content: center;
  align-items: center;
}

.loading-spinner {
  /* Sesuaikan dengan kebutuhan */
  color: white;
  font-size: 20px;
}
img:hover {
  cursor: pointer;
}
/* Menggunakan animasi pada elemen yang diinginkan */
.fade-zoom-in {
  animation: fadeZoomIn 1s ease-in-out;
}</style>