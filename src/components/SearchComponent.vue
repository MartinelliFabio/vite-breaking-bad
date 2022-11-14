<template>
    <div class="container mb-3">
        <div class="form-floating col-2">
            <select class="form-select p-3">
                <option selected>select category</option>
                <option value="1">Alive</option>
                <option value="2">Dead</option>
                <option value="3">Presumed dead</option>
            </select>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'SearchComponent',
    }
</script>

<style lang="scss" scoped>

</style>