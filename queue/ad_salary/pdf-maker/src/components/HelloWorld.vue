<template>
  <div class="hello">
    <button @click="createPdf()">click</button>
  </div>
</template>

<script>
import JsPDF from 'jspdf'

export default {
  methods: {
    createPdf () {
      let pdfName = 'test'
      var doc = new JsPDF()
      doc.setFontSize(30)
      var xOffset = (doc.internal.pageSize.width / 2) - (doc.getStringUnitWidth('Hello World') * 30 / 2)
      console.log(xOffset)
      doc.text('Hello World', xOffset, 20)
      var text = 'Hi How are you'
      xOffset = (doc.internal.pageSize.width / 2) - (doc.getStringUnitWidth(text) * doc.internal.getFontSize() / 2)
      doc.text(text, xOffset, 250)
      doc.save(pdfName + '.pdf')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
