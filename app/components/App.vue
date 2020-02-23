<template>
  <Page>
    <ActionBar title="Welcome to NativeScript-Vue!" />
    <StackLayout>
      <Child :placeName="'World 2'" />
      <Button text="TAP" @tap="tapMe" />
      <Label class="message" :text="counter" />
    </StackLayout>
  </Page>
</template>

<script lang="ts">
import Vue from 'nativescript-vue';
import Child from '~/components/Child.vue';

interface MyProps {}
interface MyComputed {}
interface MyMethods {
  tapMe: () => void;
  addToCounter: (v: number) => number;
}
interface MyData {
  counter: number;
}

export default Vue.extend<MyData, MyMethods, MyComputed, MyProps>({
  components: { Child },
  data: () => {
    return {
      counter: 42
    };
  },
  methods: {
    tapMe() {
      this.counter = this.addToCounter(5);
    },
    addToCounter(v: number): number {
      return this.counter + v;
    }
  }
});
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
