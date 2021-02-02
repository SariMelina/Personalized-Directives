<template>
  <div class="container">
    <div class="jumbotron">
      <span v-decorar:chico.italico.negrilla="{familia: 'helvetica', color: 'red'}">
        Aprende VueJS fácilmente
      </span>
      <hr>
      <span v-decorar-local:grande.italico.negrilla="{familia: 'times new roman', color: 'purple'}">
        Directiva Local
      </span>
    </div>
  </div>
</template>

<script>
export default {
  directives: {
    'decorar-local': {
      bind(el, binding, vnode){
        el.style.fontFamily = binding.value.familia
        el.style.color = binding.value.color

        if(binding.arg === 'grande'){
          el.style.fontSize = '50px'
        }
        if(binding.arg === 'chico'){
          el.style.fontSize = '10px'
        }

        if(binding.modifiers['negrilla']){
          el.style.fontWeight = 'bold'
        } 
        if (binding.modifiers['italico']){
          el.style.fontStyle = 'italic'
        }
      }
    }
  }
}
</script>

<style>

</style>
