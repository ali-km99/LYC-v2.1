<template>
  <div class="hidden lg:block bg-blue-500">
    <NavBar />
  </div>
  <div class="relative bg-blue-500"><SmallNavbar /></div>
  <div class="bg-gray-100 min-h-screen p-6" dir="rtl">
    <!-- Page Header -->
    <h1 class="text-4xl font-bold text-primary text-center mb-12">{{ $t('Advertisements') }}</h1>

    <!-- Announcements Section -->
    <div class="mt-6 space-y-6" v-if="races">
      <div v-for="race in races" :key="race.id" class="bg-white shadow-md rounded-md p-6">
        <!-- Race Header -->
        <div class="border-b pb-4 mb-4">
          <h2 class="text-xl font-semibold">{{ 'عنوان البطولة : ' + race.title }}</h2>
          <p class="text-gray-500">{{ race.location }}</p>
        </div>

        <!-- Race Details -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
          <div class="bg-slate-100 p-2 rounded-lg">
            <h3 class="font-semibold">معلومات البطولة</h3>
            <p class="text-gray-500">{{ race.info }}</p>
          </div>
          <div class="bg-slate-100 p-2 rounded-lg">
            <h3 class="font-semibold">قواعد و معدات</h3>
            <p class="text-gray-500">{{ race.rules }}</p>
          </div>
          <div class="bg-slate-100 p-2 rounded-lg">
            <h3 class="font-semibold">الإقامة و الإعاشة</h3>
            <p class="text-gray-500">{{ race.accommodation }}</p>
          </div>
        </div>

        <!-- Race Schedule -->
        <section class="grid lg:grid-cols-3 gap-4">
          <div class="mt-4 bg-slate-100 p-2 rounded-lg">
            <h3 class="font-semibold">البرنامج الزمني</h3>
            <ul class="list-disc mr-6">
              <li v-for="schedule in race.schedule" :key="schedule.time">
                <span>{{ schedule.event }}</span> - <span>{{ schedule.time }}</span
                >: <span>{{ schedule.date }}</span>
              </li>
            </ul>
          </div>
          <div class="mt-4 bg-slate-100 p-2 rounded-lg">
            <h3 class="font-semibold py-4">مسار السباق</h3>
            <img src="../assets/imeges/map1.jpg" alt="" class="w-[300px] mx-auto" />
          </div>
        </section>

        <!-- Registration Details -->
        <div class="mt-4">
          <h3 class="font-semibold">التسجيل</h3>
          <p><strong>الموعد النهائي:</strong> {{ race.registration.deadline }}</p>
          <p><strong>الرسوم:</strong> {{ race.registration.fee }}</p>
          <p><strong>طريقة التسجيل:</strong> {{ race.registration.process }}</p>
        </div>

        <!-- Buttons -->
        <div class="mt-6 flex gap-3">
          <button
            class="bg-blue-600 text-white py-2 px-4 rounded-md hover:bg-blue-700"
            @click="downloadAnnouncement(race.id)"
          >
            تحميل إعلان السباق
          </button>
          <a
            :href="race.registration.link"
            class="bg-green-600 text-white py-2 px-4 rounded-md hover:bg-green-700"
            target="_blank"
          >
            التسجيل في السباق
          </a>
        </div>
      </div>
    </div>

    <!-- No Races Message -->
    <div v-else class="text-center text-gray-500 mt-12">
      <p>لا توجد إعلانات في الوقت الحالي.</p>
    </div>
  </div>
</template>

<script setup lang="ts">
import NavBar from '@/components/NavBar.vue'
import SmallNavbar from '@/components/SmallNavbar.vue'
import { ref } from 'vue'

const races = ref()

const downloadAnnouncement = (raceId: number) => {
  alert(`تحميل إعلان السباق رقم ${raceId}`)
}
</script>
