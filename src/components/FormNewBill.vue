<template>
    <div class="container text-left">
        <form class="form-group">
            <div class="row">
                <div class="col-sm-12 col-md-6 col-lg-3 mb-3">
                    <label for="nameOfBill">Name Of Bill</label>
                    <input id="nameOfBill" type="text" v-model="form.name" class="form-control w-100" required="required">
                </div>
                <div class="col-sm-12 col-md-6 col-lg-4 mb-3">
                    <label for="valueOfBill">Value Of Bill</label>
                    <input id="valueOfBill" type="number" v-model="form.value" class="form-control w-100" required="required">
                </div>
                <div class="col-sm-6 col-md-6 col-lg-3 mt-4 mb-3">
                    <div class="form-check">
                        <input class="form-check-input" type="radio" id="radioExpense" value="Expense" checked v-model="form.typeBill">
                        <label class="form-check-label" for="radioExpense">
                            Expense
                        </label>
                    </div>
                    <div class="form-check">
                        <input class="form-check-input" type="radio" id="radioRevenue" value="Revenue" v-model="form.typeBill">
                        <label class="form-check-label" for="radioRevenue">
                            Revenue
                        </label>
                    </div>
                </div>
                <div class="col-sm-6 col-md-6 col-lg-2 mt-4 pt-1">
                    <button type="submit" class="btn btn-green btn-lg form-control text-center" @click="this.$parent.addBill">
                        Add <span class="fas fa-plus ml-2"></span>
                    </button>
                </div>
            </div>
        </form>
    </div>
</template>
<script>
export default {
    name: "FormNewBill",
    data() {
        return {
        }
    },
    props: ["form"]
}
</script>