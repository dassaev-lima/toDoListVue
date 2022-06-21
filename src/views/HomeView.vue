<template>
  <div class="home">
    <NavBar />
    <DashboardMain :amountRevenue="this.amountRevenue" :amountExpense="this.amountExpense"/>
    <FormNewBill :form="form"/>
    <div class="container">
      <h3 class="text-left">Transactions</h3>
      <hr style="height:1px;width:100%;opacity: 0.3;" class="bg-green" >
      <div v-for="(bill, index) in bills" :key="index">
        <CardBill  :name="bill.name" :value="bill.value" :typeBill="bill.typeBill" :index="index" />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import DashboardMain from "@/components/DashboardMain.vue";
import FormNewBill from "@/components/FormNewBill.vue";
import CardBill from "@/components/CardBill.vue";
import NavBar from "@/components/NavBar.vue";
import Swal from 'sweetalert2'

export default {
  name: 'HomeView',
  
  data() {
    return {
      bills: [],
      form: {
        name: "",
        value: "",
        typeBill: "Expense",
      },
      amountRevenue: 0,
      amountExpense: 0
    }
  },
  components: {
    DashboardMain,
    FormNewBill,
    CardBill,
    NavBar
  },

  mounted() {
    if (localStorage.getItem('bills')) {
        try {
            this.bills = JSON.parse(localStorage.getItem('bills'));
        } catch(e) {
            localStorage.removeItem('bills');
        }
    }
    this.calculateRevenuesAndExpenses();
  },

  methods: {

    addBill() {   
      /* Garantido que o formulário esteja preenchido */  
      for (const [key, value] of Object.entries(this.form)) {
        if(value == ""){
          return;
        }
      }
      this.bills.push(this.form);
      this.saveBills();
      Swal.fire({
        position: 'top-center',
        icon: 'success',
        text: 'O item foi adicionado com sucesso!',
        showConfirmButton: true,
        timer: 3000
      })
    },

    removeBill(index) {
      this.bills.splice(index, 1);
      this.saveBills();
      Swal.fire({
        position: 'top-center',
        icon: 'success',
        text: 'O item foi removido com sucesso!',
        showConfirmButton: true,
        timer: 3000
      })
    },

    saveBills() {
      /*Essa linha abaixo salva no localStorage de fato antes só estava salvando no array*/
      const parsed = JSON.stringify(this.bills);
      localStorage.setItem("bills", parsed);
      this.calculateRevenuesAndExpenses()
    },

    calculateRevenuesAndExpenses() {
      this.amountRevenue = 0
      this.amountExpense = 0
      console.log('Oi')
      if (this.bills != []) {
        for (let i = 0; i < this.bills.length; i++ ) {
          if (this.bills[i].typeBill === "Revenue") {
            this.amountRevenue += parseFloat(this.bills[i].value);
          } else {
            this.amountExpense += parseFloat(this.bills[i].value);
          }
        }
      }    
    },    
  },
}
</script>