<!-- bugSolution.vue -->
<template>
  <div :class="['bg-gray-200', {'text-red-500': isError, 'text-green-500': isSuccess}]">
    {{ message }}
  </div>
</template>

<script>
  export default {
    data() {
      return {
        isError: false,
        isSuccess: false,
        message: 'This is the initial message'
      };
    },
    mounted() {
      setTimeout(() => {
        this.isError = true;
        this.message = 'This message has an error';
      }, 2000);
      setTimeout(() => {
        this.isError = false;
        this.isSuccess = true;
        this.message = 'Success!';
      }, 4000);
    }
  };
</script>