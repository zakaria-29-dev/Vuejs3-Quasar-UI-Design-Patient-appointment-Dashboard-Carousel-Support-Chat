<template>
  <q-drawer show-if-above side="right" bordered :width="300">
    <q-toolbar class="q-mt-lg">
        <q-space></q-space>
        <q-btn round icon="notifications">
            <q-badge floating color="green" rounded />
        </q-btn>
    </q-toolbar>
    <div class="flex flex-center column">
        <q-avatar size="100px">
            <img src="https://cdn.quasar.dev/img/avatar6.jpg" />
        </q-avatar>
        <q-item-label caption class="q-my-md">Your Activity Today</q-item-label>
        <div class="text-h5"><strong>86%</strong></div>
    </div>
    <q-card class="q-mx-md" flat bordered>
        <q-toolbar class="">
            <div class="text-overline">All activity</div>
            <q-space></q-space>
            <q-btn round icon="fas fa-chevron-right" size="10px" color="green"></q-btn>
        </q-toolbar>
    </q-card>
    <q-card class="q-mx-md q-mt-lg" bordered>
        <q-toolbar>
            <div class="text-overline text-weight-bolder">Support Chat</div>
            <q-space></q-space>
            <q-avatar size="25px">
                <img src="https://cdn.quasar.dev/img/avatar1.jpg" />
            </q-avatar>
            <div class="text-overline q-ml-sm">Joseph</div>
        </q-toolbar>
        <q-separator />
        <div class="q-pa-md row justify-center">
            <div style="width:100%; max-width: 400px">
            <q-chat-message name="me" avatar="https://cdn.quasar.dev/img/avatar4.jpg" :text="['hey, how are you?']"
            sent stamp="7 minutes ago">

            </q-chat-message>
            <q-chat-message name="JAne" avatar="https://cdn.quasar.dev/img/avatar3.jpg" :text="['doing fine, how r you?']"
             stamp="4 minutes ago">

            </q-chat-message>
        </div>
        </div>
        <q-input bottom-slots v-model="text" label="Your message.." class="q-mx-sm">
        <template v-slot:after>
                <q-btn round dense flat icon="fas fa-paper-plane" color="green" size="10px" class="q-mt-md" />
        </template>
    </q-input>
    </q-card>
  </q-drawer>
</template>

<script>
export default {

}
</script>

<style>
.q-item__section--main.none {
  flex: none !important;
}
.top {
  margin-top: -10px;
}
</style>