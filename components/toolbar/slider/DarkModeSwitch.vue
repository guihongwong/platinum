<script lang="ts" setup>
import type { Themes } from '~/composables/darkmode'
import { themePreference } from '~/composables/darkmode'

const { t } = useI18n()

function changeTheme(theme: Themes) {
  themePreference.value = theme
}
</script>

<template>
  <div class="flex flex-row space-x-1 text-xl">
    <div
      class="i-uil:desktop cursor-pointer"
      :class="{ 'text-gray-400 dark:text-gray-600': themePreference !== 'system' }"
      :title="t('darkmode.system')"
      @click="changeTheme('system')"
    />
    <div
      class="i-uil:sun cursor-pointer"
      :class="{ 'text-gray-400 dark:text-gray-600': themePreference !== 'light' }"
      :title="t('darkmode.light')"
      @click="changeTheme('light')"
    />
    <div
      class="i-uil:moon cursor-pointer"
      :class="{ 'text-gray-400 dark:text-gray-600': themePreference !== 'dark' }"
      :title="t('darkmode.dark')"
      @click="changeTheme('dark')"
    />
  </div>
</template>
