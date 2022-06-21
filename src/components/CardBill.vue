<template>
    <div class="card mb-4">
        <div class="card-body">
            <div class="row">
                <div class="ccol-sm-7 col-md-7 col-lg-8 text-left">
                    <h5 style="font-wigth:300" class="pt-1">{{ name }}</h5>
                </div>
                <div v-if="typeBill == 'Revenue'" class="ccol-sm-3 col-md-3 col-lg-3">
                    <h5  class="text-green text-semibold pt-1">$ {{ value.toFixed(2) }}</h5>
                </div>
                <div v-else class="ccol-sm-3 col-md-3 col-lg-3">
                    <h5 class="text-red text-semibold pr-3 pt-1">$ {{ value.toFixed(2) }}</h5>
                </div>

                <div v-if="typeBill == 'Revenue'" class="col-sm-2 col-md-2 col-lg-1">
                    <button class="btn btn-red btn-block" @click="this.$parent.removeBill(index)">
                        <span class="fas fa-trash text-white"></span>
                    </button>
                </div>
                <div v-else class="col-sm-2 col-md-2 col-lg-1">
                    <button class="btn btn-red btn-block" @click="this.$parent.removeBill(index)">
                        <span class="fas fa-trash text-white"></span>
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: "CardBill",
    data() {
        return {
        }
    },
    props: ["name","value","typeBill","index"],
}
</script>