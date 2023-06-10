<template>
  <div><HeaderComponent /></div>
</template>

<script>
  // @ is an alias to /src
  import HeaderComponent from "@/components/HeaderComponent";

  export default {
    name: "HomePage",
    components: {
      HeaderComponent,
    },
  };
</script>
