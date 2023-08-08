<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal">
            <h1>{{ title }}</h1>
            <p>{{ content }}</p>
            <div class="form">
                <div class="form-inputs">
                    <input type="text" placeholder="name">
                    <input type="text" placeholder="type">
                    <input type="text" placeholder="description">
                </div>

                <div><button> SAVE </button></div>
            </div>
            <button @click="closeModal" class="closeModal"> close</button>
        </div>

    </div>
</template>
  
<style >
.modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
}

.backdrop {
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
}

.modal h1 {
    color: red;
}

.modal p {
    color: gray;
}
.modal .form{
    display: flex;
    flex-direction: column;
    padding: 10px;
}
.modal .form-inputs {
    display: flex;
    flex-direction: column;
    gap: 15px;
    border-radius: 20px;
}
</style>
  
<script>
export default {
    props: [
        'content',
        'title'
    ],
    data() {
        return {

        }
    },
    methods: {
        closeModal() {
            this.$emit('close')
        }
    }


}
</script>
  
  
  
  
  