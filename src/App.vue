<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <div>
    <!-- Modal -->
    <Modal modalId="modalRef" @onLoad="onLoadRemoveModal">
      <div class="modal-header">
        <h5 class="modal-title">Hello from Bootstrap 5</h5>
        <button type="button" class="btn-close" @click="hideModal()"></button>
      </div>
      <div class="modal-body">

        ho

      </div>
      <div class="modal-footer">
        <button @click="hideModal()" type="button" class="btn btn-secondary">Close</button>

        <button type="button" class="btn btn-primary">
          Confirm
        </button>
      </div>

    </Modal>
  </div>
</template>



<script setup>

//Import files/labs block
import { onMounted, watch, ref } from 'vue';
import Modal from './components/Modal.vue';

//Define variables block
const modalRef = ref(null)


//Load remove instance call
const onLoadEvent = (ref) => {
  modalRef.value = ref
}

//Show remove modal call
const showModal = (item) => {
  modalRef.value.show()
}

//Hide remove modal call
const hideModal = () => {
  modalRef.value.hide()
}

</script>