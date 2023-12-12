<template>
  <div :class="{ 'mb-3': !inside }">
    <div class="custom-collapse box m-0">
      <button
        class="button button-transparent inverted white-html p-0"
        @click="open()"
      >
        <i
          class="fa-solid"
          :class="{ 'fa-chevron-up': isOpened, 'fa-chevron-down': !isOpened }"
        ></i>
      </button>
      <p class="white-html">{{ example.question.pt_BR }}</p>
    </div>
    <div v-if="isOpened && example.items.length">
      <div v-for="item in example.items" :key="item.id" class="mb-1">
        <div v-if="item.items.length">
          <Collapse :example="item" :inside="true" />
        </div>
        <div v-else class="box m-0">
          {{ item.question.pt_BR }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Collapse",
  components: {},
  props: {
    example: {},
    inside: Boolean,
  },
  methods: {
    open() {
      this.isOpened = !this.isOpened;
    },
  },
  data: () => {
    return {
      isOpened: false,
    };
  },
};
</script>

<style>
.custom-collapse {
  display: flex;
  align-items: center;
  gap: 1rem;
}
button:hover {
  background-color: var(--transparent);
  border-color: var(--transparent);
}
</style>
