<template>
    <div class="input-group">
        <input type="text" id="btn-inpout" class="form-control input-sm" name="message" v-model="newMessage" @keyup.enter="sendMessage">

        <span class="input-group-btn">
            <button class="btn btn-primary btn-sm" id="btn-chat" @click="sendMessage">Send</button>
        </span>
    </div>
</template>

<script>
    export default {
        props: ['user'],
        data() {
            return {
                newMessage: ''
            }
        },
        methods: {
            sendMessage() {
                this.$emit('message-event', {
                    user: this.user,
                    message: this.newMessage
                }, '213123123');

                this.newMessage = '';
            }
        }
    }
</script>
