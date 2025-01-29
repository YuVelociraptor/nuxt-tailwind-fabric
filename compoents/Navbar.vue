<script setup lang="ts">
import { ref } from 'vue';

// メニューの開閉状態を管理する状態を定義
const isMenuOpen = ref(false);

// メニューを開閉する関数
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};
</script>

<template>
  <div class="bg-gray-800 text-white">
    <!-- ナビゲーションバー -->
    <nav class="flex items-center p-4 sm:justify-start">
      <!-- ハンバーガーボタン（左側） -->
      <button
          class="block sm:hidden p-2 mr-4"
          @click="toggleMenu"
          :aria-expanded="isMenuOpen"
      >
        <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
        >
          <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16m-7 6h7"
          />
        </svg>
      </button>

      <!-- ロゴ -->
      <div class="flex-grow sm:flex-grow-0 flex justify-center sm:justify-start">
        <div class="text-xl font-bold">Logo</div>
      </div>

      <!-- メニュー項目（広い画面用） -->
      <ul class="hidden sm:flex space-x-4 ml-8">
        <li><a href="#" class="hover:text-gray-300">Home</a></li>
        <li><a href="#" class="hover:text-gray-300">About</a></li>
        <li><a href="#" class="hover:text-gray-300">Services</a></li>
        <li><a href="#" class="hover:text-gray-300">Contact</a></li>
      </ul>
    </nav>

    <!-- ハンバーガーメニューの展開部分 -->
    <ul
        v-if="isMenuOpen"
        class="flex flex-col space-y-2 p-4 sm:hidden"
    >
      <li><a href="#" class="block hover:text-gray-300">Home</a></li>
      <li><a href="#" class="block hover:text-gray-300">About</a></li>
      <li><a href="#" class="block hover:text-gray-300">Services</a></li>
      <li><a href="#" class="block hover:text-gray-300">Contact</a></li>
    </ul>
  </div>
</template>

<style scoped>

</style>
