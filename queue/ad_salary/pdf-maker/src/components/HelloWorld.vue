<template>
  <div class="hello">
    <button @click="createPdf()">click</button>
  </div>
</template>

<script>
import JsPDF from 'jspdf'
import 'jspdf-autotable'

export default {
  methods: {
    createPdf () {
      var columns = ['ID', 'Name', 'Country']
      var rows = [
        [1, 'Shaw', 'Tanzania'],
        [2, 'Nelson', 'Kazakhstan'],
        [3, 'Garcia', 'Madagascar']
      ]
      let pdfName = 'test'
      var doc = new JsPDF('p', 'pt')
      var fontSize = 30
      doc.setFontSize(fontSize)
      var xOffset = (doc.internal.pageSize.width / 2) - (doc.getStringUnitWidth('Hello World') * fontSize / 2)
      doc.text('Hello World', xOffset, 30)
      doc.setFontSize(10)
      doc.autoTable(columns, rows)
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
