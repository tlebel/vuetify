<template>
  <settings-header
    title="communication"
    text="communication-message"
  />

  <AppSettingsBannerOption />

  <AppSettingsNotificationsOption />

  <br>

  <div class="d-flex justify-end">
    <v-btn
      :disabled="isDisabled"
      :text="t('reset-all')"
      color="error"
      size="small"
      variant="outlined"
      @click="onResetAllNotifications"
    />
  </div>

  <v-divider class="my-3" />

  <AppSettingsSettingsHeader
    title="dashboard.advanced-options.danger-zone"
    text="dashboard.advanced-options.danger-zone-message"
  />

  <AppSettingsDeveloperMode />

  <br>

  <div class="d-flex justify-end">
    <v-btn
      :text="t('reset-all-settings')"
      color="error"
      prepend-icon="mdi-alert-circle-outline"
      size="small"
      variant="flat"
      @click="onResetAllSettings"
    />
  </div>
</template>

<script setup>
  const { t } = useI18n()
  const user = useUserStore()

  const isDisabled = computed(() => (
    user.notifications.last.banner.length === 0 &&
    user.notifications.read.length === 0
  ))

  function onResetAllNotifications () {
    user.banner = true
    user.notifications.read = []
    user.notifications.show = true
    user.notifications.last.banner = []
  }

  function onResetAllSettings () {
    user.reset()
  }
</script>
