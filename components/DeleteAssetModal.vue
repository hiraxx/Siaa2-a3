<template>
   <div>    
    <b-modal id="deleteAssetModal" title="Delete Asset" ok-title="Delete Asset" @ok="onDelete">
      Are you sure you want to continue? <br>
      {{asset.name}} {{asset.description}}
    </b-modal>  
  </div>
</template>

<script>
export default {
  props: {
    asset: {}
  },
  methods: {
    async onDelete(){
      this.$axios.delete('/api/assets/' + this.asset.id)
      .then((res)=>{
        if(res.status==202){
          alert("Asset Succesfully Deleted")
          this.$emit('onDeleteEntry')
        }
      })
    }
  }
}
</script>

<style>

</style>
