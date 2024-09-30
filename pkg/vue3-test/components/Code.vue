<script setup>
import { ref, computed } from 'vue';
import CodeMirror from '@shell/components/CodeMirror';

const code = ref('');

const codeMirrorOptions = computed(() => ({
  mode: 'javascript',
  lineNumbers: true,
  tabSize: 2,
  indentWithTabs: false,
  cursorBlinkRate: 530,
  extraKeys: {
    'Ctrl-Space': 'autocomplete',
    Tab(cm) {
      if (cm.somethingSelected()) {
        cm.indentSelection('add');
      } else {
        cm.execCommand('insertSoftTab');
      }
    },
    'Shift-Tab'(cm) {
      cm.indentSelection('subtract');
    },
  },
}));
</script>

<template>
  <div>
    <CodeMirror v-model="code" :options="codeMirrorOptions" />
  </div>
</template>

<style scoped>
/* Add any necessary styles here */
</style>
