<template>
  <div>
    <h2 class="text-2xl mb-4">Privacy</h2>
    <form
      class="space-y-4 mx-auto"
      @submit.prevent="
        addNotification('Privacy settings were saved successfully')
      "
    >
      <div class="flex items-center gap-1">
        <input type="checkbox" v-model="privacy.searchEngineIndexing" />
        <label>Search engine indexing</label>
      </div>
      <div>
        <label class="mb-1">Visibility</label>
        <select v-model="privacy.visibility">
          <option value="private">Private</option>
          <option value="public">Public</option>
        </select>
      </div>
      <button type="submit" class="btn-primary">Save</button>
    </form>
  </div>
</template>

<script setup lang="ts">
import { useNotifications } from "@/composables/useNotifications";
import { useSettings } from "@/composables/useSettings";
const { addNotification } = useNotifications();
const { privacy } = useSettings();
</script>
