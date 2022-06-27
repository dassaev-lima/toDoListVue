<template>
    <div class="container mb-5">
        <h2 class="text-center mb-5">Controle de despesas</h2>
        <div class="row">
            <div class="col-sm-12 col-md-6 col-lg-6 mb-3">
                <div class="card-shadow p-5 text-center">
                    <h5>Revenues</h5>
                    <h3 class="text-green text-bold">$ {{ amountRevenue.toFixed(2) }} </h3>
                </div>
            </div>
            <div class="col-sm-12 col-md-6 col-lg-6 mb-3">
                <div class="card-shadow p-5 text-center">
                    <h5>Expenses</h5>
                    <h3 class=" text-red text-bold">$ {{ amountExpense.toFixed(2) }}</h3>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: "DashboardMain",
    data() {
        return {}
    },
    props: ["amountRevenue","amountExpense"],
}
</script>