<template>
  <div class="wrapper">
    <div class="item">
      <i class="iconfont pcolor icon-github-fill"></i>
    </div>
    <div class="item" @click="changeTheme">
      <i class="iconfont pcolor" :class="dark ? 'icon-sun' : 'icon-Moon'"></i>
    </div>
  </div>
</template>

<script>
export default {
  name: 'linkAndDark',
}
</script>

<script setup>
import { ref, watch } from 'vue'

const dark = ref(false)

function changeTheme() {
  if (dark.value) {
    document.body.classList.toggle('dark')
    document.body.classList.remove('light')
  } else {
    document.body.classList.toggle('light')
    document.body.classList.remove('dark')
  }
  dark.value = !dark.value
}

changeTheme()
</script>

<style lang="less" scoped>
.wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 100%;
  width: 80px;
  margin: 28px auto 0;
}
</style>
<style lang="less">
@dark-primay-color: #1abb9c;
@dark-text-color: #fefefe;
@dark-bg-color: #161616;

@light-primay-color: #2c3e50;
@light-text-color: #333;
@light-bg-color: #fff;

.dark {
  color: @dark-text-color;
  background: @dark-bg-color;
  transition: all 0.3s;
  .pcolor {
    color: @dark-primay-color;
  }
  .border {
    border: 1px solid #484848;
  }
  .border-b {
    border-bottom: 1px solid #484848;
  }
  .border-r {
    border-right: 1px solid #484848;
  }
  .bg {
    background: @dark-bg-color;
  }
  .txt {
    color: @dark-text-color;
  }
  code {
    background-color: @dark-primay-color;
    color: @dark-text-color;
    padding: 2px 4px;
    border-radius: 2px;
  }
  pre code.hljs {
    display: block;
    overflow-x: auto;
    padding: 1em;
  }
  code.hljs {
    padding: 3px 5px;
  }
  .hljs {
    color: #ccc;
    background: #2d2d2d;
  }
  .hljs ::selection,
  .hljs::selection {
    background-color: #515151;
    color: #ccc;
  }
  .hljs-comment {
    color: #999;
  }
  .hljs-tag {
    color: #b4b7b4;
  }
  .hljs-operator,
  .hljs-punctuation,
  .hljs-subst {
    color: #ccc;
  }
  .hljs-operator {
    opacity: 0.7;
  }
  .hljs-bullet,
  .hljs-deletion,
  .hljs-name,
  .hljs-selector-tag,
  .hljs-template-variable,
  .hljs-variable {
    color: #f2777a;
  }
  .hljs-attr,
  .hljs-link,
  .hljs-literal,
  .hljs-number,
  .hljs-symbol,
  .hljs-variable.constant_ {
    color: #f99157;
  }
  .hljs-class .hljs-title,
  .hljs-title,
  .hljs-title.class_ {
    color: #fc6;
  }
  .hljs-strong {
    font-weight: 700;
    color: #fc6;
  }
  .hljs-addition,
  .hljs-code,
  .hljs-string,
  .hljs-title.class_.inherited__ {
    color: #9c9;
  }
  .hljs-built_in,
  .hljs-doctag,
  .hljs-keyword.hljs-atrule,
  .hljs-quote,
  .hljs-regexp {
    color: #6cc;
  }
  .hljs-attribute,
  .hljs-function .hljs-title,
  .hljs-section,
  .hljs-title.function_,
  .ruby .hljs-property {
    color: #69c;
  }
  .diff .hljs-meta,
  .hljs-keyword,
  .hljs-template-tag,
  .hljs-type {
    color: #c9c;
  }
  .hljs-emphasis {
    color: #c9c;
    font-style: italic;
  }
  .hljs-meta,
  .hljs-meta .hljs-keyword,
  .hljs-meta .hljs-string {
    color: #a3685a;
  }
  .hljs-meta .hljs-keyword,
  .hljs-meta-keyword {
    font-weight: 700;
  }
  a {
    color: @dark-primay-color;
  }
}
.light {
  color: @light-text-color;
  background: @light-bg-color;
  transition: all 0.3s;
  .pcolor {
    color: @light-primay-color;
  }
  a {
    color: @light-primay-color;
  }
  .border {
    border: 1px solid #ccc;
  }
  .border-b {
    border-bottom: 1px solid #ccc;
  }
  .border-r {
    border-right: 1px solid #ccc;
  }
  .bg {
    background-color: @light-bg-color;
  }
  .txt {
    color: @light-text-color;
  }
  code {
    background-color: @light-primay-color;
    color: @light-bg-color;
    padding: 2px 4px;
    border-radius: 2px;
  }
  pre code.hljs {
    display: block;
    overflow-x: auto;
    padding: 1em;
    border: 1px solid #ccc;
  }
  code.hljs {
    padding: 3px 5px;
  }
  .hljs {
    color: #4d4d4c;
    background: #fff;
  }
  .hljs ::selection,
  .hljs::selection {
    background-color: #d6d6d6;
    color: #4d4d4c;
  }
  .hljs-comment {
    color: #8e908c;
  }
  .hljs-tag {
    color: #969896;
  }
  .hljs-operator,
  .hljs-punctuation,
  .hljs-subst {
    color: #4d4d4c;
  }
  .hljs-operator {
    opacity: 0.7;
  }
  .hljs-bullet,
  .hljs-deletion,
  .hljs-name,
  .hljs-selector-tag,
  .hljs-template-variable,
  .hljs-variable {
    color: #c82829;
  }
  .hljs-attr,
  .hljs-link,
  .hljs-literal,
  .hljs-number,
  .hljs-symbol,
  .hljs-variable.constant_ {
    color: #f5871f;
  }
  .hljs-class .hljs-title,
  .hljs-title,
  .hljs-title.class_ {
    color: #eab700;
  }
  .hljs-strong {
    font-weight: 700;
    color: #eab700;
  }
  .hljs-addition,
  .hljs-code,
  .hljs-string,
  .hljs-title.class_.inherited__ {
    color: #718c00;
  }
  .hljs-built_in,
  .hljs-doctag,
  .hljs-keyword.hljs-atrule,
  .hljs-quote,
  .hljs-regexp {
    color: #3e999f;
  }
  .hljs-attribute,
  .hljs-function .hljs-title,
  .hljs-section,
  .hljs-title.function_,
  .ruby .hljs-property {
    color: #4271ae;
  }
  .diff .hljs-meta,
  .hljs-keyword,
  .hljs-template-tag,
  .hljs-type {
    color: #8959a8;
  }
  .hljs-emphasis {
    color: #8959a8;
    font-style: italic;
  }
  .hljs-meta,
  .hljs-meta .hljs-keyword,
  .hljs-meta .hljs-string {
    color: #a3685a;
  }
  .hljs-meta .hljs-keyword,
  .hljs-meta-keyword {
    font-weight: 700;
  }
}

.iconfont {
  font-size: 21px;
  vertical-align: -0.15em;
  fill: currentColor;
  overflow: hidden;
  cursor: pointer;
}
.icon-github-fill {
  font-size: 24px;
}
</style>
