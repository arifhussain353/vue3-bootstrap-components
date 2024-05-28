## Bootstrap 5 Stand-Alone Components Integrated with Vue 3

This guide covers small Bootstrap components that work with Bootstrap 5.

### Modal

#### Emits

The `/components/modal.vue` file contains the Bootstrap modal code, including basic modal events. Currently, the following `emits` work with this component:

#### `onShow`
- Triggered by the `show.bs.modal` event and can be used to perform any action when the modal is shown.

#### `onHide`
- Triggered by the `hide.bs.modal` event and can be used to perform any action when the modal is hidden.

#### `onLoad *`
- Used when the component loads. It returns the modal `instance`, which can be used to perform modal operations such as `show` and `hide`.

#### Props

#### `modalId *`
- Pass a modal ID to generate a unique instance.

#### `modalClass`
- Pass classes to the modal root element.

### Usage

Currently, the Modal component accepts a `slot` for passing content.

Example usage code:

```vue
<Modal modalId="modalRef" @onLoad="onLoadModal">
    <div class="modal-header">
        <h5 class="modal-title">Hello from Bootstrap 5</h5>
        <button type="button" class="btn-close" @click="hideModal()"></button>
    </div>
    <div class="modal-body">
        Your content here
    </div>
    <div class="modal-footer">
        <button @click="hideModal()" type="button" class="btn btn-secondary">Close</button>
        <button type="button" class="btn btn-primary">
            Confirm
        </button>
    </div>
</Modal>
```

Define `Ref`:

```js
const modalRef = ref(null);
```

Get the modal instance by calling the `onLoad` emit using the `onLoadModal` function:

```js
// Call onLoad and get modal instance 
const onLoadModal = (ref) => {
    modalRef.value = ref;
};
```

Show the modal with a button click:

```vue
<button type="button" @click="showModal()" class="btn btn-primary">
    Show Modal
</button>
```

```js
// Show modal call
const showModal = () => {
    modalRef.value.show();
};
```

### Support

For any additional information, please visit the [**Bootstrap**](https://getbootstrap.com/) and [**Vue**](https://vuejs.org/) documentation. We highly appreciate your participation!