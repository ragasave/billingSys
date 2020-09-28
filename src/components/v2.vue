<template>
  <table border="1" cellspacing="0" width="800" class="mx-auto table-v2">
    <thead>
      <tr>
        <th colspan="11" class="px-2 text-center">
          <h4 class="font-weight-bold m-0">TAX INVOICE</h4>
        </th>
      </tr>
      <tr>
        <th class="px-2" rowspan="5" width="50" colspan="5" align="left">
          <h5 class="font-weight-bold m-0">
            <RcTextBox :value="invoiceBy.title" class-name="w-100 d-block" @update="invoiceBy.title = $event"></RcTextBox>
          </h5>
          <p class="m-0">
            <RcTextBox :value="invoiceBy.address_line_1" class-name="w-100 d-block" @update="invoiceBy.address_line_1 = $event"></RcTextBox>
          </p>
          <p class="m-0">
            <RcTextBox :value="invoiceBy.address_line_2" class-name="w-100 d-block" @update="invoiceBy.address_line_2 = $event"></RcTextBox>
          </p>
        </th>
      </tr>
      <tr>
        <th class="px-2" colspan="3" align="left">Invoice No. :</th>
        <th class="px-2 text-center" width="50" colspan="3">
          <RcTextBox :value="invoiceNo" @update="invoiceNo = $event"></RcTextBox>
        </th>
      </tr>
      <tr>
        <th class="px-2" colspan="3" align="left">Invoice Date :</th>
        <th class="px-2 text-center" width="50" colspan="3">
          <RcTextBox :value="invoiceDate" @update="invoiceDate = $event"></RcTextBox>
        </th>
      </tr>
      <tr>
        <th class="px-2" colspan="3" align="left">Work Order no. :</th>
        <th class="px-2" width="50" colspan="3">
            <RcTextBox class-name="w-100 d-block"></RcTextBox>
        </th>
      </tr>
      <tr>
        <th class="px-2" width="50" colspan="3" align="left">
          Work Order Date :
        </th>
        <th class="px-2" width="50" colspan="3">
            <RcTextBox class-name="w-100 d-block"></RcTextBox>
        </th>
      </tr>
      <tr>
        <th class="px-2 text-center" colspan="5">
          <h6 class="m-0 font-weight-bold">Invoice to Party</h6>
        </th>
        <th class="px-2  text-center" colspan="6">
          <h6 class="m-0 font-weight-bold">Invoice by Party</h6>
        </th>
      </tr>
      <tr>
        <th class="px-2" width="50" height="50" colspan="5" align="left">
          <h6 class="font-weight-bold m-0">
            <RcTextBox :value="invoiceTo.title" class-name="w-100 d-block" @update="invoiceTo.title = $event"></RcTextBox>
          </h6>
          <p class="m-0">
            <RcTextBox :value="invoiceTo.address_line_1" class-name="w-100 d-block" @update="invoiceTo.address_line_1 = $event"></RcTextBox>
          </p>
          <p class="m-0">
            <RcTextBox :value="invoiceTo.address_line_2" class-name="w-100 d-block" @update="invoiceTo.address_line_2 = $event"></RcTextBox>
          </p>
        </th>
        <th class="px-2" width="50" height="50" colspan="6" align="left">
          <h6 class="font-weight-bold m-0">
            <RcTextBox :value="invoiceBy.title" class-name="w-100 d-block" @update="invoiceBy.title = $event"></RcTextBox>
          </h6>
          <p class="m-0">
            <RcTextBox :value="invoiceBy.address_line_1" class-name="w-100 d-block" @update="invoiceBy.address_line_1 = $event"></RcTextBox>
          </p>
          <p class="m-0">
            <RcTextBox :value="invoiceBy.address_line_2" class-name="w-100 d-block" @update="invoiceBy.address_line_2 = $event"></RcTextBox>
          </p>
        </th>
      </tr>
      <tr>
        <th class="px-2" width="25" height="25" colspan="5" align="left">
          Contact Person: <span class="px-2"><RcTextBox :value="invoiceTo.contact_number" class-name="d-inline-block " style-attr="min-width:100px" @update="invoiceTo.contact_number = $event"></RcTextBox></span>
        </th>
        <th class="px-2" width="25" height="25" colspan="6" align="left">
          Mobile Number: <span class="px-2"><RcTextBox :value="invoiceBy.contact_number" class-name="d-inline-block " style-attr="min-width:100px" @update="invoiceBy.contact_number = $event"></RcTextBox></span>
        </th>
      </tr>
      <tr>
        <th class="px-2" width="50" height="50" colspan="5" align="left">
          GSTIN/UIN: <span class="px-2"><RcTextBox :value="invoiceTo.gst_in" class-name="d-inline-block " style-attr="min-width:100px" @update="invoiceTo.gst_in = $event"></RcTextBox></span>
        </th>
        <th class="px-2" width="50" height="50" colspan="6" align="left">
          GSTIN/UIN:<span class="px-2"><RcTextBox :value="invoiceBy.gst_in" class-name="d-inline-block " style-attr="min-width:100px" @update="invoiceBy.gst_in = $event"></RcTextBox></span>
        </th>
      </tr>
      <tr>
        <th class="px-2" height="25" width="25" colspan="3" align="left">
          State: <span class="px-2"><RcTextBox :value="invoiceTo.state" class-name="d-inline-block" style-attr="min-width:100px" @update="invoiceTo.state = $event"></RcTextBox></span>
        </th>
        <th class="px-2" colspan="2">
          Code: <span class="px-2"><RcTextBox :value="invoiceTo.code" class-name="d-inline-block " style-attr="min-width:50px" @update="invoiceTo.code = $event"></RcTextBox></span>
        </th>
        <th class="px-2" height="25" width="25" colspan="4" align="left">
          State: <span class="px-2"><RcTextBox :value="invoiceBy.state" class-name="d-inline-block " style-attr="min-width:100px" @update="invoiceBy.state = $event"></RcTextBox></span>
        </th>
        <th class="px-2" colspan="2">
          Code: <span class="px-2"><RcTextBox :value="invoiceBy.code" class-name="d-inline-block " style-attr="min-width:50px" @update="invoiceBy.code = $event"></RcTextBox></span>
        </th>
      </tr>
      <tr align="left">
        <th class="px-2" rowspan="2">Sr no.</th>
        <th class="px-2" rowspan="2">Description</th>
        <th class="px-2" rowspan="2">HSN/SAC</th>
        <th class="px-2" rowspan="2">Rate</th>
        <th class="px-2" rowspan="2">Qty</th>
        <th class="px-2" rowspan="2">Total</th>
        <th class="px-2" colspan="2">CGST</th>
        <th class="px-2" colspan="2">SGST</th>
        <th class="px-2" rowspan="2">Line Total</th>
      </tr>
      <tr align="left">
        <th class="px-2">Rate</th>
        <th class="px-2">Amount</th>
        <th class="px-2">Rate</th>
        <th class="px-2">Amount</th>
      </tr>
    </thead>
    <tr
      align="left"
      v-for="(item, index) in data"
      v-bind:key="index"
      class="table-v2-main-rows"
      :data-index="index"
    >
      <td class="px-2">
        <span v-text="index + 1"></span>
      </td>
      <td class="px-2">
        <RcTextBox className="d-block border p-1" style="width:200px" :value="item.desc" @update="item.desc = $event"></RcTextBox>
      </td>
      <td class="px-2">
        <input
          type="number"
          v-model="item.code"
          style="width: 60px"
          class="border"
        />
      </td>
      <td class="px-2">
        <input
          type="number"
          v-model="item.rate"
          @input="updateCalc(item)"
          class="border"
        />
      </td>
      <td class="px-2">
        <input
          type="number"
          class="border"
          v-model="item.quantity"
          style="width: 60px"
          @input="updateCalc(item)"
        />
      </td>
      <td class="px-2">
        <span
          v-text="item.total"
          class="d-block"
          style="min-width: 80px"
        ></span>
      </td>
      <td class="px-2">
        <input
          type="number"
          style="width: 60px"
          v-model="item.cgst.rate"
          class="border"
          @input="updateCalc(item)"
        />
      </td>
      <td class="px-2">
        <span v-text="item.cgst.amount"></span>
      </td>
      <td class="px-2">
        <input
          type="number"
          style="width: 60px"
          v-model="item.sgst.rate"
          @input="updateCalc(item)"
          class="border"
        />
      </td>
      <td class="px-2">
        <span v-text="item.sgst.amount"></span>
      </td>
      <td class="px-2 position-relative">
        <span
          class="d-block"
          v-text="item.lineTotal"
          style="width: 100px"
        ></span>
        <div class="add-row position-absolute h-100">
          <div class="d-table h-100">
            <div class="d-table-cell align-middle">
              <i class="btn btn-primary d-block" @click="addRowAfter(index)">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  class="feather feather-plus"
                >
                  <line x1="12" y1="5" x2="12" y2="19" />
                  <line x1="5" y1="12" x2="19" y2="12" />
                </svg>
              </i>
            </div>
            <div class="d-table-cell align-middle" v-if="data.length > 1">
              <i class="btn btn-danger d-block" @click="removeRow(index)">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  class="feather feather-plus"
                >
                  <line x1="5" y1="12" x2="19" y2="12" />
                </svg>
              </i>
            </div>
          </div>
        </div>
      </td>
    </tr>
    <tr align="left" class="placeholder" v-if="data.length < 10">
      <td v-for="index in 11" v-bind:key="index" height="200"></td>
    </tr>
    <tr height="25" width="25" align="left">
      <th class="px-2" colspan="9"></th>
      <th class="px-2">Total</th>
      <th class="px-2">
        <span v-text="total" class="px-2  "></span>
      </th>
    </tr>
    <tr align="left">
      <th class="px-2" colspan="6">Total Invoice Amount in words</th>
      <th class="px-2" colspan="4">Total Amount Before tax</th>
      <td class="px-2">
        <span></span>
      </td>
    </tr>
    <tr align="left">
      <th class="px-2 text-center font-weight-bold" colspan="6" rowspan="4">
        <span v-text="amountToWord()"></span> Only
      </th>
      <th class="px-2" colspan="4">ADD-CGST</th>
      <th class="px-2">
        <span v-text="cgst"></span>
      </th>
    </tr>
    <tr align="left">
      <th class="px-2" colspan="4">ADD-SGST</th>
      <th class="px-2">
        <span v-text="sgst"></span>
      </th>
    </tr>
    <tr align="left">
      <th class="px-2" colspan="4">Total Tax Amount</th>
      <th class="px-2">
        <span v-text="cgst+sgst"></span>
      </th>
    </tr>
    <tr align="left">
      <th class="px-2" colspan="4">Total Amount After Tax</th>
      <th class="px-2">
        <span v-text="total"></span>
      </th>
    </tr>
    <tr align="left">
      <th class="px-2 text-center" colspan="3">
        <h5 class="font-weight-bold m-0">Bank Details</h5>
      </th>
      <th class="px-2 text-center align-bottom" colspan="3" rowspan="6">
        Common seal
      </th>
      <th class="px-2" colspan="4">GST Revers Charge</th>
      <th class="px-2"></th>
    </tr>
    <tr align="left">
      <th class="px-2" colspan="3" width="25">
        <RcTextBox value="Bank Name" class-name="d-inline-block w-100" style-attr="min-width:100px"></RcTextBox>
      </th>
      <th class="px-2" colspan="5" rowspan="2"></th>
    </tr>
    <tr align="left">
      <th class="px-2" colspan="3">ACCOUNT NO.
        <span>
          <RcTextBox value="" class-name="d-inline-block " style-attr="min-width:100px"></RcTextBox>
        </span>
      </th>
    </tr>
    <tr align="left">
      <th class="px-2" colspan="3">IFSC Code:
        <span>
          <RcTextBox value="" class-name="d-inline-block " style-attr="min-width:100px"></RcTextBox>
        </span>
      </th>
      <th class="px-2" colspan="5" rowspan="2">
        For <span v-text="invoiceBy.title">

        </span>
      </th>
    </tr>
    <tr align="left">
      <th class="px-2" height="30" width="40" colspan="3">Declaration:
        <span>
          <RcTextBox value="" class-name="d-inline-block " style-attr="min-width:100px"></RcTextBox>
        </span>
      </th>
    </tr>
    <tr align="left">
      <th class="px-2" colspan="3">Note:</th>
      <th class="px-2 text-right align-bottom" colspan="5" height="100" width="30">
        Authorized Signatory
      </th>
    </tr>
  </table>
</template>


<script>
import RcTextBox from "./RcTextBox";
const numberToText = require('number-to-text')
require('number-to-text/converters/en-us');
function smapleData() {
  return {
    desc: null,
    code: null,
    rate: 0,
    quantity: 1,
    total: 0,
    cgst: {
      rate: 0,
      amount: 0,
    },
    sgst: {
      rate: 0,
      amount: 0,
    },
    lineTotal: 0,
  };
}
export default {
  created() {
    this.data.push(smapleData());
    window.$("body").on("click", ".print-btn", () => {
      this.printPage();
    });
    window.$("body").on("click", ".download-btn", () => {
      this.exportCsv();
    });
    // window.$('body').on('keydown', (e) => {

    //   let keyCode = e.keyCode || e.which;
    //   let elem = window.$(document.activeElement);
    //   let row = elem.parents('.table-v2-main-rows');
    //   let index, td, field;
    //   if(row.length == 0 || !elem.is(":focus")
    //   || elem.is('[type=number]')
    //   ){return}
    //   index = Number(row.attr('data-index'));
    //   td = elem.parents('td');
    //   console.log(td.index(), index+1);
    //   switch (keyCode) {
    //     case 38:
    //       field = window.$('.table-v2-main-rows').eq(index-1).find('td').eq(td.index()).find('input, span[contenteditable]');
    //       if(field&& field[0]){field[0].focus()}
    //       break;
    //     case 40:
    //       field = window.$('.table-v2-main-rows').eq(index-1).find('td').eq(td.index()).find('input, span[contenteditable]');
    //       if(field&& field[0]){field[0].focus()}
    //       break;
    //     default:
    //       break;
    //   }
    // })

    this.date = window.moment().format('DD-MM-YYYY h:m A');
    window.setInterval(() => {
      this.date = window.moment().format('DD-MM-YYYY h:m A');
    }, 60);
    this.invoiceDate = this.date;
  },
  data() {
    return {
      data: [],
      total: 0,
      cgst : 0,
      sgst : 0,
      totalWithoutTax : 0,
      totalWithTax : 0,
      totalTax : 0,
      invoiceDate :  null,
      invoiceNo: `${window.moment.now()}`,
      invoiceBy : {
        title : "STAR REFRIGERATION SALES AND SERVICE",
        address_line_1 : "C-05, Behind Hanuman Mandir, Azad Nagar,",
        address_line_2 : "Chitalsar Manpada, Thane 400607",
        contact_number : "+91 9322742211",
        gst_in : "27AQZPK2988C1Z6",
        state : "MAHARASHTRA"
      },
      invoiceTo : {
        title : "Customer Name",
        address_line_1 : "",
        address_line_2 : "",
        contact_number : "",
        gst_in : "",
        state : "MAHARASHTRA"
      },
    };
  },
  methods: {
    amountToWord(){
      return numberToText.convertToText(this.total);
    },
    updateCalc(item) {
      item.total = Number((item.rate * item.quantity).toFixed(2));
      item.cgst.amount = Number(
        ((item.total * item.cgst.rate) / 100).toFixed(2)
      );
      item.sgst.amount = Number(
        ((item.total * item.sgst.rate) / 100).toFixed(2)
      );
      item.lineTotal = Number(
        (item.cgst.amount + item.cgst.amount + item.total).toFixed(2)
      );
      this.total = 0; 
      this.cgst = 0; 
      this.sgst = 0; 
      this.data.forEach(element => {
      this.sgst += element.sgst.amount; 
      this.cgst += element.cgst.amount; 
        this.total += element.lineTotal;
      });
      return item;
    },
    addRowAfter(index) {
      this.data.splice(index + 1, 0, smapleData());
    },
    removeRow(index) {
      this.data.splice(index, 1);
    },
    grandTotal() {
      if (this.formData.items.length == 1) {
        return this.formData.items[0].subTotal;
      }
      let totalAmount = 0;
      this.formData.items.forEach((element) => {
        totalAmount = element.subTotal + totalAmount;
      });
      return Number((Math.round(totalAmount * 100) / 100).toFixed(2));
    },
    exportCsv() {
      let data = [];
      data.push([
        "sr.no",
        "desc",
        "code",
        "rate",
        "quantity",
        "total",
        "cgst rate",
        "cgst amount",
        "sgst rate",
        "sgst amount",
        "line total",
      ]);
      this.data.forEach((item, index) => {
        data.push(this.csvRow(Object.values(item), index));
      });
      window.exportToCsv(`${new Date().getTime()}-invoice.csv`, data);
    },
    csvRow(data, index) {
      var row = [];
      row.push(index);
      for (const key in data) {
        const element = data[key];
        if (element instanceof Object) {
          for (const key2 in element) {
            const element2 = element[key2];
            row.push(element2);
          }
        } else {
          row.push(element);
        }
      }
      console.log(row);
      return row;
    },
    printPage() {
      window.print();
    },
  },
  components: {
    RcTextBox: RcTextBox,
  },
};
</script>