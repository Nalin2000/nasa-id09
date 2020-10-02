<template>
  <transition name="modal">
    <div class="modal-mask content">
      <div class="modal-wrapper">
        <div class="modal-container">
          <div class="modal-header">
            <slot name="header">
              <h3>ERROR!!</h3>
            </slot>
          </div>
          <div class="modal-body">
            <slot name="body"></slot>
            <slot name="footer"></slot>
          </div>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: 'modal',
  props: {
    lable: String,
  },
}
</script>

<style scoped>
.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(255, 255, 255, 0.315);
  display: table;
  transition: opacity 0.3s ease;
}

.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}

.modal-container {
  width: 80%;
  height: 80%;
  margin: 0px auto;
  padding: 20px 30px;
  background-color: rgba(47, 47, 48, 0.959);
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(255, 255, 255, 0.33);
  transition: all 0.3s ease;
}

.modal-header h3 {
  margin-top: 0;
  color: #ffffff;
}

.modal-body {
  margin: 190px 0;
}

.modal-header {
  color: #ffffff;
}

.modal-enter {
  opacity: 0;
}

.modal-leave-active {
  opacity: 0;
}

.modal-enter .modal-container,
.modal-leave-active .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
</style>
