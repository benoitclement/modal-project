<template>
  <div @click.self="closeModal" class="backdrop">
    <div class="modal">
      <div class="modal-header">
        <slot name="header-button"></slot>
      </div>
      <slot></slot>
      <div class="modal-footer">
        <slot name="footer-content">This is default content text for footer</slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    header: {
      type: String
    },
    text: {
      type: String
    }
  },
  methods: {
    closeModal() {
      this.$emit('close')
    } 
  }
}
</script>

<style>
  .modal {
      width: 400px;
      padding: 20px;
      margin: 100px auto;
      background: white;
      border-radius: 10px;
    }
  .modal-header {
    text-align: right;
  }
  .modal-header a {
      cursor: pointer;
    }
  .backdrop {
      top: 0;
      position: fixed;
      background: rgba(0,0,0,0.5);
      width: 100%;
      height: 100%;
    }
</style>
