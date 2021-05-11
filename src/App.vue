<template>
  <div class="m-8">
    <p class="max-w-lg text-gray-900">
      To reproduce the issue, open the ListboxOptions, click on the disabled option (Simon) and then navigate up or down with the arrow
      keys. The disabled option should now be in focus.
    </p>
    <Listbox v-model="selectedTeamMember">
      <div class="mt-8 w-60 relative">
        <ListboxButton class="border-2 border-gray-200 rounded-lg px-4 py-1 w-full">{{ selectedTeamMember.name }}</ListboxButton>
        <ListboxOptions class="absolute mt-2 py-1 w-full bg-white rounded-lg ring-2 ring-black ring-opacity-10">
          <ListboxOption
            v-for="member in teamMembers"
            :key="member"
            :value="member"
            v-slot="{ active, selected, disabled }"
            :disabled="member.shittyTimezone"
            as="template"
          >
            <li
              :class="[
                'px-4 py-2',
                { 'bg-green-100 text-green-800': active, 'font-medium bg-green-400 text-green-900': selected, 'text-gray-300': disabled },
              ]"
            >
              {{ member.name }}
            </li>
          </ListboxOption>
        </ListboxOptions>
      </div>
    </Listbox>
  </div>
</template>

<script>
import { ref } from "vue";
import { Listbox, ListboxButton, ListboxOptions, ListboxOption } from "@headlessui/vue";

export default {
  components: {
    Listbox,
    ListboxButton,
    ListboxOptions,
    ListboxOption,
  },
  setup() {
    const teamMembers = [
      { name: "Adam" },
      { name: "Steve" },
      { name: "Brad" },
      { name: "Simon", shittyTimezone: true },
      { name: "Robin" },
      { name: "David" },
      { name: "James" },
    ];

    const selectedTeamMember = ref(teamMembers[0]);

    return {
      selectedTeamMember,
      teamMembers,
    };
  },
};
</script>
