<script setup>
// Recibe la orden de apertura desde el padre
defineProps(['isOpen'])

// Declara el aviso de cierre para el padre
defineEmits(['close'])
</script>

<template>
  <teleport to="body">
    <!-- Si isOpen es true, el modal aparece -->
    <div class="modal" v-if="isOpen">
      <div class="modal-content">
          
          <h1>Modal</h1>
          <p>Este es un modal de ejemplo.</p>

          <!-- Avisa al padre que el usuario quiere cerrar -->
          <button @click="$emit('close')">Cerrar</button>
      </div>
    </div>
  </teleport>
</template>

<style scoped>
.modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
}

.modal-content {
    background-color: #fff;
    padding: 20px;
    border-radius: 5px;
    text-align: center;
}
</style>
