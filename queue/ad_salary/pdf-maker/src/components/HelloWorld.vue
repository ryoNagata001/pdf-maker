<template>
  <div class="hello">
    <button @click="createPDF()">click</button>
    <div id="pdf">
      <div style="min-height: 100vh; max-width: 1000px; padding: 20px;">  <!-- ここにA4のwidth指定すればいい感じになるかも -->
        <!-- ここにHTML要素 -->
        <div>
          <div style="padding: 50px 0 260px; ::after{content: ''; display: block; clear: both;}">
            <div style="float: left; width: 50%;">
              <div style="height: 48px;">
                <p style="margin: 0 0; font-weight: bold; font-size: 14px;">BILL TO:</p>
                <p style="margin: 0 0; font-size: 18px; font-weight: bold;">Kilton(相手先の名前)</p>
              </div>
              <p style="font-weight: bold; letter-spacing: 4px; margin: 40px 0 0 30px;">ADDRESS:</p>
              <p style="text-align: center; font-weight: bold; margin: 10px 0 0; min-height: 75px;">相手先の住所</p>
              <div class="">
                <p style="float: left; width: 30%; text-align: right; font-weight: bold; margin: 0;">PHONE：</p>
                <p style="float: right; width: 70%; text-align: left; font-weight: bold; margin: 0;">相手先の電話番号</p>
              </div>
              <div class="">
                <p style="float: left; width: 30%; text-align: right; font-weight: bold; margin: 0;">FAX：</p>
                <p style="float: right; width: 70%; text-align: left; font-weight: bold; margin: 0;">相手先のFAX</p>
              </div>
            </div>
            <div style="float: right; width: 50%;">
              <p style="margin: 0; height: 48px; line-height: 48px; text-align: center; color: #1F497C; font-size: 20px; font-weight: bold; letter-spacing: 5px;">INVOICE</p>
              <p style="text-align: center; font-weight: bold; margin: 15px 0;">MPC(Admin側の会社名)</p>
              <p style="text-align: center; font-weight: bold; margin: 30px 0;">Admin側のオフィスの住所</p>
              <div class="">
                <p style="float: left; width: 50%; margin: 0; font-weight: bold;">TEL:Admin側の電話番号</p>
                <p style="float: right; width: 50%; margin: 0; font-weight: bold;">FAX:Admin側のFAX</p>
              </div>
              <table style="border-collapse: collapse; width: 100%;">
                <tr>
                  <td style="border: solid 2px; padding: 1px 2px; width: 50%; font-weight: bold;">INVOICE #</td>
                  <td style="border: solid 2px; padding: 1px; width: 50%; font-weight: bold;">DATE</td>
                </tr>
                <tr>
                  <td style="border: solid 2px; padding: 1px; width: 50%; font-weight: bold;"></td>
                  <td style="border: solid 2px; padding: 1px; width: 50%; font-weight: bold; text-align: center;">日付</td>
                </tr>
              </table>
            </div>
          </div>
        </div>
        <div style="padding: 10px 0;">
          <table style="border-collapse: collapse; width: 100%;">
            <tr style="background-color: #DCE6F1;">
              <td colspan="8" style="font-weight: bold; text-align: center; border: solid 3px; border-right: solid 2px; padding: 0.5em;">SERVICE DESCRIPTION</td>
              <td colspan="4" style="font-weight: bold; text-align: center; border: solid 3px; border-left: solid 2px; padding: 0.5em;">AMOUNT(PHP)</td>
            </tr>
            <tr>
              <td colspan="1" style="border: solid 2px; border-left: solid 3px; text-align: center; padding: 0.5em; width: 5%; font-weight: bold;">1</td>
              <td colspan="7" style="border: solid 2px; text-align: center; padding: 0.5em; width: 65%; font-weight: bold;">Prepayment fee</td>
              <td colspan="4" style="border: solid 2px; border-right: solid 3px; padding: 0.5em; text-align: right; width: 30%; font-weight: bold;">20,000</td>
            </tr>
            <tr style="background-color: #DCE6F1;">
              <td colspan="1" style="border: solid 2px; border-left: solid 3px; text-align: center; padding: 0.5em; width: 5%; font-weight: bold;">2</td>
              <td colspan="7" style="border: solid 2px; text-align: center; padding: 0.5em; width: 65%;"></td>
              <td colspan="4" style="border: solid 2px; border-right: solid 3px; padding: 0.5em; text-align: right; width: 30%;"></td>
            </tr>
            <tr>
              <td colspan="1" style="border: solid 2px; border-left: solid 3px; text-align: center; padding: 0.5em; width: 5%; font-weight: bold;">3</td>
              <td colspan="7" style="border: solid 2px; text-align: center; padding: 0.5em; width: 65%;"></td>
              <td colspan="4" style="border: solid 2px; border-right: solid 3px; padding: 0.5em; text-align: right; width: 30%;"></td>
            </tr>
            <tr style="background-color: #DCE6F1;">
              <td colspan="1" style="border: solid 2px; border-left: solid 3px; text-align: center; padding: 0.5em; width: 5%; font-weight: bold;">4</td>
              <td colspan="7" style="border: solid 2px; text-align: center; padding: 0.5em; width: 65%;"></td>
              <td colspan="4" style="border: solid 2px; border-right: solid 3px; padding: 0.5em; text-align: right; width: 30%;"></td>
            </tr>
            <tr>
              <td rowspan="3" colspan="5" style="border: solid 2px; border-left: solid 3px; border-right: solid 3px; border-bottom: solid 3px; padding: 0.5em; width: 50%; font-weight: bold;">NOTE</td>
              <td rowspan="1" colspan="3" style="border: solid 2px; text-align: center; padding: 0.5em; width: 20%; font-weight: bold;">SUB TOTAL(PHP)</td>
              <td rowspan="1" colspan="4" style="border: solid 2px; border-right: solid 3px; padding: 0.5em; text-align: right; width: 30%; font-weight: bold;">20,000</td>
            </tr>
            <tr>
              <td rowspan="1" colspan="3" style="border: solid 2px; text-align: center; padding: 0.5em; width: 20%; font-weight: bold;">TAX(PHP)</td>
              <td rowspan="1" colspan="4" style="border: solid 2px; border-right: solid 3px; padding: 0.5em; text-align: right; width: 30%; font-weight: bold;">2,400</td>
            </tr>
            <tr>
              <td rowspan="1" colspan="3" style="border: solid 2px; border-bottom: solid 3px; text-align: center; padding: 0.5em; width: 20%; font-weight: bold;">TOTAL AMOUNT(PHP)</td>
              <td rowspan="1" colspan="4" style="border: solid 2px; border-bottom: solid 3px; border-right: solid 3px; padding: 0.5em; text-align: right; width: 30%; font-weight: bold;">22,400</td>
            </tr>
          </table>
        </div>
        <div>
          <p style="font-weight: bold; text-align: center; margin: 10px 0 5px;">REMITTANCE INFORMATION</p>
          <div class="">
            <p style="float: left; width: 30%; text-align: right; margin: 0 0 2px; font-weight: bold;">BANK NAME:</p>
            <p style="float: right; width: 70%; text-align: center; margin: 0 0 2px; font-weight: bold;">銀行名</p>
          </div>
          <div>
            <p style="float: left; width: 30%; text-align: right; margin: 0 0 2px; font-weight: bold;">SWIFT CODE:</p>
            <p style="float: right; width: 70%; text-align: center; margin: 0 0 2px; font-weight: bold;">スウィフトコード</p>
          </div>
          <div>
            <p style="float: left; width: 30%; text-align: right; margin: 0 0 2px; font-weight: bold;">ACCOUNT NO.</p>
            <p style="float: right; width: 70%; text-align: center; margin: 14px 0 2px; font-weight: bold;">口座番号</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import JsPDF from 'jspdf'
import html2canvas from 'html2canvas'

export default {
  methods: {
    createPDF () {
      console.log('hoge')
      html2canvas(document.getElementById('pdf'))
        .then(
          function (canvas) {
            var divHeight = document.getElementById('pdf').clientHeight
            var divWidth = document.getElementById('pdf').clientWidth
            var ratio = divHeight / divWidth
            var dataURI = canvas.toDataURL('image/jpeg')
            var pdf = new JsPDF()
            var width = pdf.internal.pageSize.width - 20
            var height = ratio * width
            pdf.addImage(dataURI, 'JPEG', 10, 10, width, height)
            pdf.save('test.pdf')
          }
        )
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
