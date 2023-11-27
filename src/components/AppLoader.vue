<script>
export default {

}
</script>

<template>

    <div class="loader-container">
        <div class="loader"></div>
    </div>

    

</template>

<style lang="scss" scoped>



.loader-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.loader {
  border: 8px solid #f3f3f3; 
  border-top: 8px solid #3498db; 
  border-radius: 50%;
  width: 50px;
  height: 50px;
  animation: spin 1s linear infinite;
}

</style>