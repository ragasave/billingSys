<template>
  <div class="w-100">
    <h5 class="mb-4 px-3 no-print">Create invoice</h5>
    <div class="d-flex justify-content-between">
      <div class="col-6 left-pan no-print" style="max-width:700px">
        <div class="card p-4">
          <div class="mt-3 text-center"></div>

          <div class="row">
            <div class="col-6">
              <div class="form-row mt-3">
                <label for="cn">Customer Name</label>
                <input
                  spellcheck="false"
                  type="text"
                  name
                  id="cn"
                  placeholder="Customer Name"
                  class="form-control"
                  v-model="formData.customerName"
                />
              </div>
            </div>
            <div class="col-6">
              <div class="form-row mt-3">
                <label for="mobile">Customer Phone Number</label>
                <input
                  spellcheck="false"
                  type="number"
                  placeholder="Customer Phone Number"
                  id="mobile"
                  min="10"
                  class="form-control"
                  v-model="formData.phoneNumber"
                />
              </div>
            </div>
          </div>
        </div>
        <hr />
        <div v-for="(item, index) in formData.items" v-bind:key="index" class="card mt-4 p-4">
          <div v-if="formData.items.length > 1">
            <a
              href="#"
              class="position-absolute text-danger"
              @click="removeItem(index)"
              style="right: 10px;top: 10px;z-index:99"
            >
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
                class="feather feather-x"
              >
                <line x1="18" y1="6" x2="6" y2="18" />
                <line x1="6" y1="6" x2="18" y2="18" />
              </svg>
            </a>
          </div>
          <div class="row">
            <div class="col-12">
              <div class="form-row mt-3">
                <label for="item-name">Item Name</label>
                <textarea
                  type="text"
                  id="item-name"
                  v-model="item.itemName"
                  class="form-control"
                  spellcheck="false"
                  placeholder="Item name..."
                ></textarea>
              </div>
            </div>
          </div>
          <div class="row">
            <div class="col-3">
              <div class="form-row mt-3">
                <label for="item-amount">Amount</label>
                <input
                  spellcheck="false"
                  type="number"
                  min="0"
                  v-model="item.amount"
                  name
                  id="item-amount"
                  class="form-control"
                />
              </div>
            </div>
            <div class="col-3">
              <div class="form-row mt-3">
                <label for="item-quantity">Quantity</label>
                <input
                  spellcheck="false"
                  type="number"
                  min="0"
                  v-model="item.quantity"
                  name
                  id="item-quantity"
                  class="form-control"
                />
              </div>
            </div>
            <div class="col-3">
              <div class="form-row mt-3">
                <label for="item-amount">GST</label>
                <input
                  spellcheck="false"
                  type="number"
                  min="0"
                  v-model="item.gst"
                  name
                  id="item-gst"
                  class="form-control"
                />
              </div>
            </div>
            <div class="col-3">
              <div class="form-row mt-5 pt-1">
                <span>=</span>
                <span class="px-3" v-text="calculateSubTotal(item)"></span>
              </div>
            </div>
          </div>
        </div>

        <button
          @click="addItem()"
          class="btn-amber btn rounded-circle p-0 text-center position-fixed"
          style="right: 15px;bottom: 15px;width: 60px;height: 60px;z-index: 999;"
        >
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
        </button>
      </div>

      <div class="col-6 invoice-container">
        <div class="card p-4">
          <div class="invoice" id="invoice">
            <div class="text-center">
              <h2 class>Shop Name</h2>
              <p>In need of a button, but not the hefty background colors they bring? Replace the default modifier classes.</p>
            </div>
            <div class="invoice-customer-data  border-bottom py-4">
                <div>   
                    <table>
                        <tr>
                            <th>Customer Name</th>
                            <th class="px-2">:</th>
                            <td><span v-text="formData.customerName"></span></td>
                        </tr>
                        <tr>
                            <th>Customer Phone Number</th>
                            <th class="px-2">:</th>
                            <td><span v-text="formData.phoneNumber"></span></td>
                        </tr>
                        <tr>
                            <th>Invoice Date</th>
                            <th class="px-2">:</th>
                            <td><span v-text="date"></span></td>
                        </tr>
                    </table>
                </div>
            </div>
            <div class="">
              <table class="w-100 invoice-table">
                <thead>
                  <tr>
                    <th>Service Name</th>
                    <th>Amount</th>
                    <th>Quantity</th>
                    <th>GST</th>
                    <th>Total</th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="(item, index) in formData.items" v-bind:key="index" class="bill-row">
                    <td>
                      <span v-text="item.itemName" contenteditable="true"></span>
                    </td>
                    <td>
                      <span v-text="item.amount"></span>
                    </td>
                    <td>
                      <span v-text="item.quantity"></span>
                    </td>
                    <td>
                      <span v-text="item.gst"></span>
                    </td>
                    <td>
                      <span v-text="item.subTotal"></span>
                    </td>
                  </tr>
                </tbody>
                <tfoot>
                    <tr class="grand-total">
                        <th class="border-top" colspan="4">Grand Total</th>
                        <td class="border-top">
                            <span v-text="grandTotal()"></span>
                        </td>
                    </tr>
                </tfoot>
              </table>
            </div>
            <div class="invoice-btn-list no-print">
              <table>
                <tr>
                  <td>
                    <button @click="printPage()" class="btn py-2 btn-primary">
                      <i class="fas fa-magic ml-1"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-printer"><polyline points="6 9 6 2 18 2 18 9"></polyline><path d="M6 18H4a2 2 0 0 1-2-2v-5a2 2 0 0 1 2-2h16a2 2 0 0 1 2 2v5a2 2 0 0 1-2 2h-2"></path><rect x="6" y="14" width="12" height="8"></rect></svg></i>
                    </button>
                  </td>
                  <td>
                    <button @click="exportCsv()" class="btn py-2 btn-primary">
                      <i class="fas fa-magic ml-1"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-download"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path><polyline points="7 10 12 15 17 10"></polyline><line x1="12" y1="15" x2="12" y2="3"></line></svg></i>
                    </button>
                  </td>
                </tr>
              </table>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
function obj() {
  return {
    itemName: null,
    amount: 0,
    gst: 12,
    quantity: 1,
    subTotal: 0,
  };
}

export default {
  props: {
    invoices: Array,
  },
  created(){
      this.date = window.moment().format('DD-MM-YYYY h:m A');
      window.setInterval(() => {
        this.date = window.moment().format('DD-MM-YYYY h:m A');
      }, 60)
      
  },
  data() {
    return {
      formData: {
        total: 0,
        customerName: null,
        phoneNumber: null,
        items: [obj()],
      },
      date : null
    };
  },
  methods: {
    calculateSubTotal(item) {
      let amount =
        ((Number(item.amount) * Number(item.gst)) / 100 + Number(item.amount)) *
        item.quantity;
      item.subTotal = Number((Math.round(amount * 100) / 100).toFixed(2));
      return item.subTotal;
    },

    removeItem(index) {
      if (
        this.formData.items[index] == null ||
        this.formData.items.length < 2
      ) {
        return;
      }
      this.formData.items.splice(1, 1);
    },
    addItem() {
      this.formData.items.push(obj());
    },
    grandTotal(){
        if(this.formData.items.length == 1){return this.formData.items[0].subTotal}
        let totalAmount = 0;
        this.formData.items.forEach(element => {
            totalAmount = element.subTotal + totalAmount;
        });
        console.log(totalAmount);
        return Number((Math.round(totalAmount * 100) / 100).toFixed(2));
    },
    exportCsv(){
      let data = [];
      data.push(Object.keys(obj()));
      this.formData.items.forEach((item) => {
        data.push(Object.values(item));
      })
      window.exportToCsv(`${(new Date()).getTime()}-invoice.csv`, data);
    },
    printPage(){
      window.print();
    }

  },
};
</script>