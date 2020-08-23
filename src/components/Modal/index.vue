<template>
  <div @click="close" class="modal__container">
    <div class="modal">
      <button class="danger">Denunciar conteúdo inadequado</button>
      <button class="danger">Deixar de seguir</button>
      <button>Ir para a publicação</button>
      <button>Compartilhar</button>
      <button>Copiar link</button>
      <button>Incorporar</button>
      <button @click="$emit('close-modal')">Cancelar</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'modal',
  methods: {
    close(e) {
      const className = e.target.className;
      if (className === 'modal__container') {
        this.$emit('close-modal');
      }
    }
  }
};
</script>

<style lang="scss" scoped>
.modal {
  background: #fff;
  width: 40rem;
  border-radius: 1.2rem;

  display: flex;
  flex-direction: column;
  overflow: hidden;

  button {
    background-color: transparent;
    border: 0;
    outline: 0;
    min-height: 4.8rem;
    padding: 0.4rem 0.8rem;
    cursor: pointer;

    &:hover {
      background-color: var(--color-background);
    }

    &.danger {
      color: #ed4956;
      font-weight: bold;
    }

    &:not(:first-child) {
      border-top: 1px solid var(--color-light);
    }
  }

  &__container {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 20;
    background-color: rgba(0, 0, 0, 0.4);
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
</style>
