<script setup lang="ts">
import { RouterView, useRouter } from 'vue-router'

const emit = defineEmits<{
  scrollToSection: []
}>()

const router = useRouter()

// التنقل وإرسال الحدث
const handleNavigation = (): void => {
  emit('scrollToSection') // إرسال الحدث مع الـ ID
  router.replace('/') // الانتقال إلى الصفحة الرئيسية
}
</script>

<template>
  <RouterView />

  <!-- Foooter -->
  <footer class="bg-[#3B82F6] relative bottom-0">
    <div class="px-4 py-12 mx-auto space-y-8 overflow-hidden sm:px-6 lg:px-8">
      <nav
        :dir="$i18n.locale == 'ar' ? 'ltr' : 'rtl'"
        class="flex flex-wrap justify-center -mx-5 -my-2"
      >
        <div class="px-5 py-2" @click="handleNavigation">
          <a href="/#contact" class="text-base leading-6 text-white hover:text-gray-900">
            {{ $t('Nav["contact"]') }}</a
          >
        </div>
        <div class="px-5 py-2">
          <a
            @click="router.replace({ name: 'Advertisements' })"
            class="text-base leading-6 text-white hover:text-gray-900"
          >
            {{ $t('Nav["Advertisements"]') }}
          </a>
        </div>
        <div class="px-5 py-2">
          <a
            @click="router.replace({ name: 'PhotoGallery' })"
            class="text-base leading-6 text-white hover:text-gray-900"
          >
            {{ $t('Nav.PhotoGallery') }}
          </a>
        </div>

        <!-- <div class="px-5 py-2">
          <a
            @click="router.replace({ name: 'GoldenHistory' })"
            class="text-base leading-6 text-white hover:text-gray-900"
          >
            {{ $t('Nav.GoldenHistory') }}
          </a>
        </div> -->
        <div class="px-5 py-2">
          <a
            @click="router.replace({ name: 'ProgramsPage' })"
            class="text-base leading-6 text-white hover:text-gray-900"
          >
            {{ $t('Nav["Programs"]') }}
          </a>
        </div>
        <div class="px-5 py-2">
          <a
            @click="router.replace({ name: 'about' })"
            class="text-base leading-6 text-white hover:text-gray-900"
          >
            {{ $t('Nav.about') }}
          </a>
        </div>
        <div class="px-5 py-2">
          <a
            @click="router.replace({ name: 'home' })"
            class="text-base leading-6 text-white hover:text-gray-900"
          >
            {{ $t('Nav.home') }}
          </a>
        </div>
      </nav>
      <div class="flex justify-center mt-8 space-x-6">
        <a
          href="https://www.facebook.com/LibyanYachtClub"
          target="_blank"
          class="text-gray-400 hover:text-white"
        >
          <span class="sr-only">Facebook</span>
          <svg class="w-6 h-6" aria-hidden="true" fill="currentColor" viewBox="0 0 24 24">
            <path
              fill-rule="evenodd"
              d="M22 12c0-5.523-4.477-10-10-10S2 6.477 2 12c0 4.991 3.657 9.128 8.438 9.878v-6.987h-2.54V12h2.54V9.797c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.243 0-1.63.771-1.63 1.562V12h2.773l-.443 2.89h-2.33v6.988C18.343 21.128 22 16.991 22 12z"
              clip-rule="evenodd"
            ></path>
          </svg>
        </a>
        <a
          href="https://www.instagram.com/libyanyacht"
          target="_blank"
          class="text-gray-400 hover:text-white"
        >
          <span class="sr-only">Instagram</span>
          <svg class="w-6 h-6" aria-hidden="true" fill="currentColor" viewBox="0 0 24 24">
            <path
              fill-rule="evenodd"
              d="M12.315 2c2.43 0 2.784.013 3.808.06 1.064.049 1.791.218 2.427.465a4.902 4.902 0 011.772 1.153 4.902 4.902 0 011.153 1.772c.247.636.416 1.363.465 2.427.048 1.067.06 1.407.06 4.123v.08c0 2.643-.012 2.987-.06 4.043-.049 1.064-.218 1.791-.465 2.427a4.902 4.902 0 01-1.153 1.772 4.902 4.902 0 01-1.772 1.153c-.636.247-1.363.416-2.427.465-1.067.048-1.407.06-4.123.06h-.08c-2.643 0-2.987-.012-4.043-.06-1.064-.049-1.791-.218-2.427-.465a4.902 4.902 0 01-1.772-1.153 4.902 4.902 0 01-1.153-1.772c-.247-.636-.416-1.363-.465-2.427-.047-1.024-.06-1.379-.06-3.808v-.63c0-2.43.013-2.784.06-3.808.049-1.064.218-1.791.465-2.427a4.902 4.902 0 011.153-1.772A4.902 4.902 0 015.45 2.525c.636-.247 1.363-.416 2.427-.465C8.901 2.013 9.256 2 11.685 2h.63zm-.081 1.802h-.468c-2.456 0-2.784.011-3.807.058-.975.045-1.504.207-1.857.344-.467.182-.8.398-1.15.748-.35.35-.566.683-.748 1.15-.137.353-.3.882-.344 1.857-.047 1.023-.058 1.351-.058 3.807v.468c0 2.456.011 2.784.058 3.807.045.975.207 1.504.344 1.857.182.466.399.8.748 1.15.35.35.683.566 1.15.748.353.137.882.3 1.857.344 1.054.048 1.37.058 4.041.058h.08c2.597 0 2.917-.01 3.96-.058.976-.045 1.505-.207 1.858-.344.466-.182.8-.398 1.15-.748.35-.35.566-.683.748-1.15.137-.353.3-.882.344-1.857.048-1.055.058-1.37.058-4.041v-.08c0-2.597-.01-2.917-.058-3.96-.045-.976-.207-1.505-.344-1.858a3.097 3.097 0 00-.748-1.15 3.098 3.098 0 00-1.15-.748c-.353-.137-.882-.3-1.857-.344-1.023-.047-1.351-.058-3.807-.058zM12 6.865a5.135 5.135 0 110 10.27 5.135 5.135 0 010-10.27zm0 1.802a3.333 3.333 0 100 6.666 3.333 3.333 0 000-6.666zm5.338-3.205a1.2 1.2 0 110 2.4 1.2 1.2 0 010-2.4z"
              clip-rule="evenodd"
            ></path>
          </svg>
        </a>

        <a
          href="https://www.youtube.com/@libyanyachtclub"
          target="_blank"
          class="text-gray-400 hover:text-white"
        >
          <!--

          viewBox="0 0 24 24"

          aria-hidden="true"
           -->
          <span class="sr-only">x</span>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="w-6 h-6"
            viewBox="0 0 32 32"
            fill="currentColor"
          >
            <path
              d="M31.331,8.248c-.368-1.386-1.452-2.477-2.829-2.848-2.496-.673-12.502-.673-12.502-.673,0,0-10.007,0-12.502,.673-1.377,.37-2.461,1.462-2.829,2.848-.669,2.512-.669,7.752-.669,7.752,0,0,0,5.241,.669,7.752,.368,1.386,1.452,2.477,2.829,2.847,2.496,.673,12.502,.673,12.502,.673,0,0,10.007,0,12.502-.673,1.377-.37,2.461-1.462,2.829-2.847,.669-2.512,.669-7.752,.669-7.752,0,0,0-5.24-.669-7.752ZM12.727,20.758V11.242l8.364,4.758-8.364,4.758Z"
            ></path>
          </svg>
        </a>
      </div>
      <p class="mt-8 text-sm leading-6 text-center text-white">
        {{ $t('Copyright') }}
      </p>
    </div>
  </footer>
</template>

<style>
.roboto {
  font-family: 'Roboto', sans-serif;
  font-weight: 400;
  font-style: normal;
}
body {
  font-family: 'Cairo', serif;
  font-optical-sizing: auto;
  font-weight: 400;
  font-style: normal;
  font-variation-settings: 'slnt' 0;
}
</style>
