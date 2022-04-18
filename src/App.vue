<template>
  <div class="title pcolor">Easy Mark</div>
  <div class="describe pcolor">在线编辑且实时预览MarkDown</div>
  <div class="border container">
    <div class="editor border-r">
      <div class="editor-title pcolor border-b">编辑</div>
      <div class="editor-content">
        <textarea id="editor" class="bg txt" v-model="content"></textarea>
      </div>
    </div>
    <div class="preview">
      <div class="editor-title pcolor border-b">预览</div>
      <div class="preview-content" v-html="preass"></div>
    </div>
  </div>

  <linkAndDark></linkAndDark>
</template>
<script setup>
import linkAndDark from './components/linkAndDark.vue'
import { computed, watchEffect, ref, onUpdated } from 'vue'
import MarkdownIt from 'markdown-it'
import hljs from 'highlight.js'

let md = new MarkdownIt()

let content = ref('# markdown-it rulezz!')

let preass = computed(() => {
  return md.render(content.value)
})

function hl() {
  document.querySelectorAll('pre code').forEach((block) => {
    hljs.highlightBlock(block)
  })
}

onUpdated(() => {
  hl()
})
</script>
<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
.title {
  font-size: 1.8rem;
  font-weight: 500;
  margin: 30px 0 10px;
  font-weight: bold;
  font-style: italic;
}
.describe {
  font-weight: 500;
  font-style: italic;
}
.container {
  max-width: 1220px;
  width: 100%;
  margin: 20px auto;
  box-sizing: border-box;
  display: flex;
  border-radius: 8px;
  border-bottom-right-radius: 0px;
  border-bottom-left-radius: 0px;
  .editor {
    width: 50%;
    text-align: left;
    box-sizing: border-box;
    overflow: hidden;

    textarea {
      opacity: 0.8;
      box-sizing: border-box;
      width: 100%;
      min-height: 60vh;
      height: 100%;
      border: none;
      outline: none;
      resize: none;
      font-size: 1rem;
      font-weight: 500;
      margin-bottom: -10px;
      box-sizing: border-box;
      overflow: visible;
    }
  }
  .editor-title {
    padding: 4px 8px;
    widows: 100%;
    font-weight: 500;
    font-weight: bold;
    font-style: italic;
  }
  .preview {
    width: 50%;
    text-align: left;
  }

  .preview-content {
    opacity: 0.8;
    padding: 4px;
    overflow-y: scroll;
    height: 60vh;
  }
}

@media screen and (max-width: 970px) {
  .container {
    flex-direction: column;
    .editor {
      width: 100%;
    }
    .preview {
      width: 100%;
      border-top: 1px solid #ccc;
    }
  }
}
::-webkit-scrollbar {
  width: 5px;
  height: 2px;
  border-radius: 5px;
}
::-webkit-scrollbar-track {
  border-radius: 1px;
  background-color: transparent;
}
::-webkit-scrollbar-thumb {
  border-radius: 10px;
  background-color: #999;
}
::-webkit-scrollbar-thumb:hover {
  background-color: #666;
}
::-webkit-scrollbar-thumb:active {
  background-color: #666;
}
</style>
