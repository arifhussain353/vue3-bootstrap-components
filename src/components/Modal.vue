<template>
    <div :class="'modal fade ' + modalClass" :id="modalId" tabindex="-1" role="dialog">
        <div class="modal-dialog" role="document">
            <div class="modal-content">
                <slot></slot>
            </div>
        </div>
    </div>
</template>

<script setup>


//All imports/labs define
import { Modal } from 'bootstrap'
import { onBeforeUnmount, onMounted, ref } from 'vue';


//Props and Emits define
const emit = defineEmits(['onShow', 'onHide', 'onLoad'])
const props = defineProps(['modalId', 'modalClass'])


//Define all veriables
const modalId = props.modalId
const modalClass = props.modalClass || ''
const modalRef = ref(null)
const element = ref(null)


//Lifecylce hook
onMounted(() => {
    modalRef.value = new Modal(`#${modalId}`, {})
    element.value = modalRef.value._element
    emit('onLoad', modalRef.value)
    element.value.addEventListener('show.bs.modal', onShow)
    element.value.addEventListener('hide.bs.modal', onHide)
})


//on show modal call/emit
const onShow = () => {
    emit('onShow')
}


//on hide modal call/emit
const onHide = () => {
    emit('onHide')
}


//Destory hook call
onBeforeUnmount(() => {
    if (element.value) {
        element.value.removeEventListener('show.bs.modal', onShow)
        element.value.removeEventListener('hide.bs.modal', onHide)
    }
})
</script>