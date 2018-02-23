<template>
  <div class="hello">
    <button @click="createPdf()">click</button>
    <button @click="printPDF()">canvas</button>
    <div id="pdf">
      <h1 style="text-align: center;">hello world</h1>
      <h2 style="color: red;">Can I type in my long words hogehogehgoeghoegheogehogegheoghoehgoehogheogheohgoehgoe</h2>
    </div>
  </div>
</template>

<script>
import JsPDF from 'jspdf'
import 'jspdf-autotable'
// import html2canvas from 'html2canvas'

export default {
  data () {
    return {
      canvasData: null
    }
  },
  methods: {
    createPdf () {
      var columns = ['ID', 'Name', 'Country']
      var rows = [
        [1, 'Shaw', 'Tanzania'],
        [2, 'Nelson', 'Kazakhstan'],
        [3, 'Garcia', 'Madagascar']
      ]
      let pdfName = 'test'
      var doc = new JsPDF()
      var fontSize = 30
      doc.setFontSize(fontSize)
      var text = 'hogehogeoghoehogheohgoehogheohgoehogheohgoehgoheohgoehgoeh'
      var xOffset = (doc.internal.pageSize.width / 2) - (doc.getStringUnitWidth(text) * fontSize / 2)
      doc.text(text, xOffset, 60)
      doc.setFontSize(10)
      doc.autoTable(columns, rows, {
        margin: {top: 100}
      })
      doc.save(pdfName + '.pdf')
    },
    printPDF () {
      var pdfName = 'test'
      var printDoc = new JsPDF()
      var width = 105
      var source = window.document.getElementById('pdf')
      printDoc.fromHTML(source, 0, 0, {'width': width})
      printDoc.save(pdfName + '.pdf')
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
