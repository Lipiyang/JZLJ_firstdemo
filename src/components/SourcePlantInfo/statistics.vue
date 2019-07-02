<template>
    <div>
        <bar></bar>
        <lineare></lineare>
        <pie></pie>
        <stbar></stbar>
    </div>
</template>

<script type="text/javascript">
import bar from './bar'
import pie from './pie'
import stbar from './stackedbar'
import lineare from './line'

export default{
    components: {
        bar,
        pie,
        stbar,
        lineare
  }

}
</script>

<style>

</style>
