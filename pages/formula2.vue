<template>
  <div v-html="$md.render(markdown)"></div>
</template>

<script>

export default {
  name: 'FormulaMathjax',
  data() {
    return {
      markdown: `
# h1 Heading
## h2 Heading
### h3 Heading
#### h4 Heading
##### h5 Heading
###### h6 Heading

## Emphasis

**This is bold text**

__This is bold text__

*This is italic text*

_This is italic text_

~~Strikethrough~~

## Blockquotes


> Blockquotes can also be nested...
>> ...by using additional greater-than signs right next to each other...
> > > ...or with spaces between arrows.

## Lists

Unordered

+ Create a list by starting a line with '+', '-', or '*'
+ Sub-lists are made by indenting 2 spaces:
  - Marker character change forces new list start:
    * Ac tristique libero volutpat at
    + Facilisis in pretium nisl aliquet
    - Nulla volutpat aliquam velit
+ Very easy!

Ordered

1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa


1. You can use sequential numbers...
1. ...or keep all the numbers as '1.'

Start numbering with offset:

57. foo
1. bar

$a$
$$
\\dd{x}
$$
$$
(\\bm{j}_Q)_i=\\dfrac{\\sqrt{2m^\\ast}e^2\\tau}{\\pi^2\\hbar^3}\\dfrac{\\pi^2}{3}(k_\\mathrm{B}T)^2E_i\\
$$
\\begin{align}
a\\label{eq:a}
\\end{align}
\\eqref{eq:a}
 `
    }
  }
}

</script>
