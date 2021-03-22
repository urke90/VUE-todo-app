<template>
    <teleport to="body">
        <div class="backdrop" @click="$emit('close')"></div>
        <div class="modal">
            <header>
                <slot name="header">
                    <h3>Error</h3>
                </slot>
            </header>
            <main>
                <slot>
                    <p>Ooops something went wrong</p>
                </slot>
            </main>
            <footer>
                <slot name="actions">
                    <base-button
                        @click="$emit('close')"
                        class="btn btn--secondary"
                    >
                        OK
                    </base-button>
                </slot>
            </footer>
        </div>
    </teleport>
</template>

<script>
export default {
    emits: ['close']
};
</script>

<style scoped>
header {
    text-align: center;
    color: #264653;
    text-transform: uppercase;
    margin-bottom: 10px;
}
main {
    margin-bottom: 20px;
}
footer {
    text-align: center;
}

/*
colors: 
1. datk blue #264653
2. light blue #2a9d8f
3. light yellow #e9c46a 
4. light oragne #f4a261
5. dark orange #e76f51
*/

.backdrop {
    background: rgba(0, 0, 0, 0.5);
    min-width: 100vw;
    min-height: 100vh;
    position: fixed;
    top: 0;
    right: 0;
    z-index: 100;
}
.modal-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
}
.modal {
    margin: auto;
    position: fixed;
    padding: 20px;
    border-radius: 5px;
    top: 50%;
    left: 50%;
    background-color: #ffffff;
    z-index: 150;
    transform: translate(-50%, -50%);
}
.modal.opened {
    top: 50%;
}
</style>
