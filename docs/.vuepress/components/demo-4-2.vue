<template>
  <div style="padding-top: 16px;">
    <vue-skeleton :paragraph="{rows: 4}"/>
  </div>
</template>

<script>
import vueSkeleton from "../../../src/components/Skeleton";

export default {
  components: { vueSkeleton },
};
</script>

