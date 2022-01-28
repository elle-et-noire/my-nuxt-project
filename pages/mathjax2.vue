<template>
<div>
<textarea v-model="formula" cols="30" rows="10"></textarea>
  <vue-mathjax :formula="formula"></vue-mathjax>
</div>
</template>

<script>
import { VueMathjax } from 'vue-mathjax'
export default {
  name: 'HelloWorld',
  components: {
    'vue-mathjax': VueMathjax
  },
  data () {
    return {
      formula: '$$x = {-b \\pm \\sqrt{b^2-4ac} \\over 2a}.\\tag{1}$$\\begin{align}y=f(x)\\tag{関数}\\label{eq:f}\\end{align}\\eqref{eq:f}は\\(x=a\\)において$0$になる。',
      msg: 'Welcome to Your Vue.js App'
    }
  },
   head: {
    script: [
      { src: 'https://cdnjs.cloudflare.com/ajax/libs/mathjax/3.2.0/es5/tex-chtml.min.js?config=TeX-AMS_HTML' }
    ]
  },
  mounted() {
    this.renderMathJax()
  },
  methods: {
    renderMathJax() {
      if (window.MathJax) {
        window.MathJax.Hub.Config({
          loader: {load: ['[tex]/physics', '[tex]/mathtools', '[tex]/color', '[tex]/upgreek', '[tex]/centernot']},
          tex: {
            inlineMath: [['$', '$'], ['\\(', '\\)']],
            packages: { '[+]': ['physics', 'mathtools', 'color', 'upgreek', 'centernot'] },
            color: {
              padding: '5px',
              borderWidth: '2px',
            },
            macros: {
              parn: ["\\biggl(#1\\biggr)", 1],
              sqbr: ["\\biggl[#1\\biggr]", 1],
              pfrac: ["\\biggl(\\dfrac{#1}{#2}\\biggr)", 2],
              ds: "\\displaystyle",
              C: '{\\mathbb C}',
              R: '{\\mathbb R}',
              Q: '{\\mathbb Q}',
              Z: '{\\mathbb Z}',
              ssqrt: ['\\sqrt{\\smash[b]{\\mathstrut #1}}', 1],
              tcdegree: ['\\unicode{xb0}'],
              tccelsius: ['\\unicode{x2103}'],
              tcperthousand: ['\\unicode{x2030}'],
              tcmu: ['\\unicode{x3bc}'],
              tcohm: ['\\unicode{x3a9}'],
              bm: ['\\boldsymbol{#1}', 1],
              ol: ['\\overline{#1}', 1],
              ul: ['\\underline{#1}', 1],
              ub: ['\\underbrace{#1}', 1],
              ubt: ['\\underbrace{#1}_{\\text{#2}}', 2],
              i: '{\\mathrm{i}}',
              e: '{\\mathrm{e}}',
              ve: '{\\varepsilon}',
              slashed: ['{{#1\\!\\!\\!/}}', 1],
            },
            physics: {
              italicdiff: true,
              arrowdel: false,
            },
            tags: 'ams',
            tagSide: 'right',
            tagIndent: '0.8em',
            processRefs: true,
          },
          svg: {
            fontCache: 'global'
          },
          chtml: {
            displayAlign: 'left',
            displayIndent: '2em',
            mtextInheritFont: true,
          }
        })
        window.MathJax.Hub.Queue(['Typeset', window.MathJax.Hub])
      }
    }
  }
}
</script>