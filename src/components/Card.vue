<template>
<div class="card">
  <div class="card-content">
    <h5 class="card-title">{{ name }}</h5>
      <div class="card-body" style="text-align:left">
        {{ content }}
      </div>
    </div>
</div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    name: String,
    content: String
  }
}
</script>


