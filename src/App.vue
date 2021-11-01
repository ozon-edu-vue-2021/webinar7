<template>
  <div id="app">
    <CreateElement v-if="false"/>

    <DomProps v-if="false" />

    <Listener v-if="false" />

    <Other v-if="false" />

    <JSX v-if="true" />
  </div>
</template>

<script>
import CreateElement from '@/components/create-element/create-element';
import DomProps from '@/components/dom-props/dom-props';
import Listener from '@/components/listeners/listener';
import Other from '@/components/other/other';
import JSX from '@/components/jsx/jsx';

export default {
  name: 'App',
  components: {
    JSX,
    Other,
    Listener,
    DomProps,
    CreateElement,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
