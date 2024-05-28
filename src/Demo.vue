<template>
    <button type="button" @click="showModal()" class="btn btn-primary">
        Show Modal
    </button>

    <div>
        <!-- Modal -->
        <Modal modalId="modalRef" @onLoad="onLoadModal">
            <div class="modal-header">
                <h5 class="modal-title">Hello from Bootstrap 5</h5>
                <button type="button" class="btn-close" @click="hideModal()"></button>
            </div>
            <div class="modal-body">
                Your content
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
import { ref } from 'vue';
import Modal from './components/Modal.vue';

//Define variables block
const modalRef = ref(null)


//Call onload and get modal instance 
const onLoadModal = (ref) => {
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