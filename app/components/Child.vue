<template>
  <StackLayout>
    <Label class="message" :text="greeting" />
  </StackLayout>
</template>

<script lang="ts">
import Vue from 'nativescript-vue';
import { ThisTypedComponentOptionsWithRecordProps } from 'vue/types/options';

interface MyProps {
  placeName: string;
}
interface MyComputed {
  greeting: string;
}
interface MyMethods {}
interface MyData {}

const opts: ThisTypedComponentOptionsWithRecordProps<
  Vue,
  MyData,
  MyMethods,
  MyComputed,
  MyProps
> = {
  props: {
    placeName: String
  },
  computed: {
    greeting() {
      return 'hello ' + this.placeName;
    }
  }
};

export default Vue.extend<MyData, MyMethods, MyComputed, MyProps>(opts);
</script>

<style scoped>
ActionBar {
  background-color: #53ba82;
  color: #ffffff;
}

.message {
  vertical-align: center;
  text-align: center;
  font-size: 20;
  color: #333333;
}
</style>
