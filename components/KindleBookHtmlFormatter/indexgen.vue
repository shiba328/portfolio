<template lang="pug">
  v-card
    v-container
      v-layout(
        wrap
      )
        v-flex(xs4)
          v-select(
            :items="listTypes"
            v-model="listTypeSelect"
            label="list type style"
          )
        v-flex(xs4)
          v-checkbox(
            color="white"
            label="prefix"
            v-model="check"
          )
        v-flex(xs4)
          v-select(
            :items="separatTypes"
            v-model="separatTypeSelect"
            label="separat"
          )
        v-flex(
          xs6
          class="textarea"
        )
          textarea(
            ref="markdownTextarea"
            v-model="textVal"
            @keydown.tab="insertTab"
            placeholder="ex. 1. chapter 1"
          )
          pre {{ textVal }}
        v-flex(
          xs6
          class="formatted"
          :class="[listTypeSelect, separatTypeSelect, {'prefix': check}]"
        )
          div(
            v-html="markedVal"
          )
</template>

<script>
import marked from 'marked'
export default {
  data() {
    return {
      check: false,
      listTypeSelect: 'decimal',
      separatTypeSelect: 'dot',
      textVal: '',
      indent: '\t',
      listTypes: [
        'decimal',
        'cjk-decimal',
        'decimal-leading-zero',
        'lower-roman',
        'upper-roman',
        'lower-greek',
        'lower-latin',
        'upper-latin',
        'hiragana',
        'hiragana-iroha',
        'katakana',
        'katakana-iroha',
      ],
      separatTypes: [
        'dot',
        'hyphen',
        'underbar',
        'no'
      ]

    }
  },
  computed: {
    markedVal() {
      return marked(this.textVal)
    }
  },
  methods: {
    insertTab(e) {
      e.preventDefault();

      const self = this;
      let target = this.$refs.markdownTextarea

      let start = target.selectionStart,
          end = target.selectionEnd,
          cursorPos = start

      this.textVal = target.value.substring(0, start)
                   + this.indent
                   + target.value.substring(end, target.value.length)

      setTimeout(() => {
        cursorPos += this.indent.length;
        target.selectionStart = target.selectionEnd = cursorPos;
      }, 10);

    }
  }
}
</script>

<style lang="scss">
.textarea {
  position: relative;
  textarea {
    resize: none;
    position: absolute;
    height: 100%;
    min-height: 200px;
    width: 100%;
    padding: 0;
    letter-spacing: 0.5px;
    word-break: break-all;
    line-height: 1.5;
  }
  pre {
    // color: transparent;
    min-height: 1.2em;
    min-height: 200px;
  }
}
.formatted {
  word-break: break-word;
}
.decimal ol { list-style-type: decimal }
.cjk-decimal ol { list-style-type: cjk-decimal }
.decimal-leading-zero ol { list-style-type: decimal-leading-zero }
.lower-roman ol { list-style-type: lower-roman }
.upper-roman ol { list-style-type: upper-roman }
.lower-greek ol { list-style-type: lower-greek }
.lower-latin ol { list-style-type: lower-latin }
.upper-latin ol { list-style-type: upper-latin }
.hiragana ol { list-style-type: hiragana }
.hiragana-iroha ol { list-style-type: hiragana-iroha }
.katakana ol { list-style-type: katakana }
.katakana-iroha ol { list-style-type: katakana-iroha }

.prefix ol {
  counter-reset: section;
  list-style-type: none;
}
.prefix li:before { counter-increment: section; }
.prefix.dot li:before { content: counters(section, ".") ".";}
.prefix.hyphen li:before { content: counters(section, "-") "-";}
.prefix.underbar li:before { content: counters(section, "_") "_";}
.prefix.no li:before { content: counters(section, "の") "の";}
</style>
