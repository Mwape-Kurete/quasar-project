<template>
  <div class="q-pa-md">
    <q-stepper v-model="step" vertical color="primary" animated>
      <q-step :name="1" title="Select campaign settings" icon="settings" :done="step > 1">
        For each ad campaign that you create, you can control how much you're willing to spend on
        clicks and conversions, which networks and geographical locations you want your ads to show
        on, and more.

        <q-stepper-navigation>
          <q-btn @click="step = 2" color="primary" label="Continue" />
        </q-stepper-navigation>
      </q-step>

      <q-step
        :name="2"
        title="Create an ad group"
        caption="Optional"
        icon="create_new_folder"
        :done="step > 2"
      >
        An ad group contains one or more ads which target a shared set of keywords.

        <q-stepper-navigation>
          <q-btn @click="step = 4" color="primary" label="Continue" />
          <q-btn flat @click="step = 1" color="primary" label="Back" class="q-ml-sm" />
        </q-stepper-navigation>
      </q-step>

      <q-step :name="4" title="Create an ad" icon="add_comment">
        Try out different ad text to see what brings in the most customers, and learn how to enhance
        your ads using features like ad extensions. If you run into any problems with your ads, find
        out how to tell if they're running and how to resolve approval issues.

        <q-stepper-navigation>
          <q-btn color="primary" label="Finish" />
          <q-btn flat @click="step = 2" color="primary" label="Back" class="q-ml-sm" />
        </q-stepper-navigation>
      </q-step>
    </q-stepper>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    return {
      step: ref(1),
    }
  },
}
</script>

<style>
.q-stepper {
  background: #21212140;
  box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
  border-radius: 10px;
  color: white;
}

.q-stepper__dot {
  background-color: #ffdd33;
}

.q-stepper--vertical .q-stepper__dot:after {
  color: white !important;
}

.q-stepper__title,
.q-stepper__step-inner {
  color: white;
  font-family: 'Josefin-Sans', sans-serif !important;
  font-weight: 300;
}

.q-icon {
  color: #212121;
}

.q-btn {
  border-radius: 50px;
  background-color: #ffdd33 !important;
  color: #212121 !important;
}

.q-stepper__caption {
  color: tomato;
}

.q-step .title {
  color: white;
}

.q-stepper-navigation {
  color: #ffdd33;
}
</style>
