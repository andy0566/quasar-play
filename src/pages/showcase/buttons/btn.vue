<template>
  <q-page padding class="docs-btn row justify-center">
    <div style="width: 500px; max-width: 90vw;">
      <p class="caption">Standard Button</p>
      <q-btn color="white" text-color="black" label="Standard" />
      <q-btn color="primary" label="Primary" />
      <q-btn color="secondary" label="Secondary" />
      <q-btn color="amber" label="Amber" />
      <q-btn color="brown-5" label="Brown 5" />
      <q-btn color="deep-orange" label="Deep Orange" />
      <q-btn color="purple" label="Purple" />
      <q-btn color="black" label="Black" />

      <p class="caption">Custom Color Examples</p>
      <q-btn style="background: #FF0080; color: white" label="Fuchsia" />
      <q-btn flat style="color: #FF0080" label="Fuchsia Flat" />
      <q-btn style="background: goldenrod; color: white" label="Goldenrod" />
      <q-btn outline style="color: goldenrod;" label="Goldenrod" />

      <p class="caption">Button with icons</p>
      <q-btn color="primary" icon="mail" label="On Left" />
      <q-btn color="secondary" icon-right="mail" label="On Right" />
      <q-btn color="red" icon="mail" icon-right="send" label="On Left and Right" />

      <p class="caption">Button with custom text color</p>
      <q-btn color="amber" text-color="purple" icon="camera_enhance" label="Purple text" />

      <p class="caption">Round Button</p>
      <q-btn round color="primary" icon="shopping_cart" />
      <q-btn round color="secondary" icon="navigation" />
      <q-btn round color="amber" text-color="black" icon="layers_clear" />
      <q-btn round color="brown-5" icon="directions" />
      <q-btn round color="deep-orange" icon="edit_location" />
      <q-btn round color="purple" icon="local_grocery_store" />
      <q-btn round color="black" icon="my_location" />

      <p class="caption">Button sizes ({{ sizes.join(', ') }})</p>
      <q-btn
        v-for="size in sizes" :key="`btn_size_sq_${size}`"
        color="primary"
        :size="size"
        :label="`Size ${size}`"
      />
      <br>
      <q-btn
        v-for="size in sizes" :key="`btn_size_rd_${size}`"
        rounded
        color="primary"
        :size="size"
        :label="`Size ${size}`"
      />
      <br>
      <q-btn
        v-for="(size, i) in sizes" :key="`btn_size_round_${size}`"
        round
        color="primary"
        :size="size"
        :icon="icons[i]"
      />

      <p class="caption">Dense button sizes ({{ sizes.join(', ') }})</p>
      <q-btn
        v-for="size in sizes" :key="`btn_size_dense_sq_${size}`"
        dense
        color="primary"
        :size="size"
        :label="`Size ${size}`"
      />
      <br>
      <q-btn
        v-for="size in sizes" :key="`btn_size_dense_rd_${size}`"
        rounded
        dense
        color="primary"
        :size="size"
        :label="`Size ${size}`"
      />
      <br>
      <q-btn
        v-for="(size, i) in sizes" :key="`btn_size_dense_round_${size}`"
        round
        dense
        color="primary"
        :size="size"
        :icon="icons[i]"
      />

      <p class="caption">Custom button size</p>
      <q-btn
        size="10px"
        color="primary"
        label="Text height: 10px"
      />
      <q-btn
        size="25px"
        round
        color="secondary"
        icon="map"
      />

      <p class="caption">Flat button</p>
      <q-btn flat color="primary" label="Flat" />
      <q-btn flat rounded color="primary" label="Flat Rounded" />
      <q-btn flat round color="primary" icon="card_giftcard" />

      <p class="caption">Outline buttons</p>
      <q-btn outline color="primary" label="Outline" />
      <q-btn outline rounded color="primary" label="Outline Rounded" />
      <q-btn outline round color="primary" icon="card_giftcard" />

      <p class="caption">Push button</p>
      <q-btn push color="primary" label="Push" />
      <q-btn push rounded color="primary" label="Push Rounded" />
      <q-btn push round color="primary" icon="card_giftcard" />

      <p class="caption">Glossy button</p>
      <q-btn glossy color="primary" label="Glossy" />
      <q-btn glossy color="secondary" label="Glossy" />
      <q-btn glossy color="deep-orange" label="Glossy" />
      <br>
      <q-btn glossy rounded color="primary" label="Glossy Rounded" />
      <q-btn glossy rounded color="secondary" label="Glossy Rounded" />
      <q-btn glossy rounded color="deep-orange" label="Glossy Rounded" />
      <br>
      <q-btn glossy round color="primary" icon="card_giftcard" />
      <q-btn glossy round color="secondary" icon="local_florist" />
      <q-btn glossy round color="deep-orange" icon="local_activity" />

      <p class="caption">Content alignment</p>
      <q-btn align="left" class="btn-fixed-width" color="primary" label="Align to left" />
      <q-btn align="right" class="btn-fixed-width" color="secondary" label="Align to right" />
      <q-btn align="between" class="btn-fixed-width" color="tertiary" label="Align between" icon="flight_takeoff" />
      <q-btn align="around" class="btn-fixed-width" color="brown-5" label="Align around" icon="lightbulb_outline" />

      <p class="caption">Disabled button</p>
      <q-btn color="primary" disable label="Disabled" />
      <q-btn round color="primary" disable icon="card_giftcard" />
      <q-btn flat color="primary" disable label="Disabled" />
      <q-btn flat round color="primary" disable icon="card_giftcard" />
      <q-btn outline color="primary" disable label="Disabled" />
      <q-btn outline round color="primary" disable icon="card_giftcard" />
      <q-btn push color="primary" disable label="Disabled" />
      <q-btn push round color="primary" disable icon="card_giftcard" />
      <q-btn glossy color="primary" disable label="Disabled" />
      <q-btn glossy round color="primary" disable icon="card_giftcard" />

      <p class="caption">Block button</p>
      <q-btn color="primary" class="block" icon="alarm" label="Block" />
      <q-btn color="secondary" class="block" label="Block" />

      <p class="caption">Full width button (or use flex classes on parent)</p>
      <q-btn color="primary" class="full-width" label="Full-width" />
      <q-btn color="secondary" class="full-width" label="Full-width" />

      <div class="mat" style="margin-top: 20px">
        <p class="caption">Button with no auto-caps (Material Theme only)</p>
        <q-btn color="primary" no-caps label="No caps" />

        <p class="caption">No ripple effect (Material Theme only)</p>
        <q-btn color="primary" no-ripple label="No Ripple Effect" />

        <p class="caption">Wait for ripple then trigger (Material Theme only)</p>
        <q-btn color="primary" wait-for-ripple label="Click me" @click="alert" />
      </div>

      <p class="caption">Button with timeout (keep pressing more than one second)</p>
      <q-btn
        :label="`Count ${count}`"
        @click="count++"
        :repeat-timeout="1000"
        color="primary"
      />

      <p class="caption">Button with progress</p>
      <q-btn :loading="loading1" color="secondary" @click="simulateProgress(1)" label="Button" />
      <q-btn :loading="loading2" color="red" @click="simulateProgress(2)">
        Button
        <span slot="loading">Loading...</span>
      </q-btn>
      <q-btn :loading="loading3" color="purple" @click="simulateProgress(3)">
        Button
        <q-spinner-radio slot="loading" />
      </q-btn>
      <q-btn :loading="loading4" color="primary" @click="simulateProgress(4)">
        Button
        <span slot="loading">
          <q-spinner-hourglass class="on-left" />
          Loading...
        </span>
      </q-btn>
      <br>
      <q-btn round :loading="loading5" color="brown" @click="simulateProgress(5)" icon="camera_front">
        <q-spinner-facebook slot="loading" />
      </q-btn>
      <q-btn round :loading="loading6" color="black" @click="simulateProgress(6)" icon="camera_rear">
        <q-spinner-gears slot="loading" />
      </q-btn>
      <br>
      <q-btn :loading="progress" color="primary" @click="progress = true">
        Controlled from outside
        <span slot="loading">
          <q-spinner-radio class="on-left" />
          Click "Stop" Button
        </span>
      </q-btn>
      <q-btn :disable="!progress" color="negative" @click="progress = false" label="Stop" />

      <p class="caption">Button with deterministic progress</p>
      <q-btn :loading="loading7" :percentage="percentage1" color="primary" @click="startComputing(1, 7)">
        Compute PI
        <span slot="loading">
          <q-spinner-gears class="on-left" />
          Computing...
        </span>
      </q-btn>

      <q-btn
        :loading="loading8"
        :percentage="percentage2"
        round
        color="secondary"
        @click="startComputing(2, 8)"
        icon="cloud_upload"
      />
    </div>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      count: 0,
      loading1: false,
      loading2: false,
      loading3: false,
      loading4: false,
      loading5: false,
      loading6: false,
      loading7: false,
      loading8: false,
      progress: false,
      percentage1: 0,
      percentage2: 0,
      sizes: ['xs', 'sm', 'md', 'lg', 'xl'],
      icons: [
        'navigation',
        'add_a_photo',
        'camera',
        'camera_front',
        'my_location'
      ]
    }
  },
  methods: {
    simulateProgress (number) {
      // we set loading state
      this[`loading${number}`] = true

      // simulate a delay
      setTimeout(() => {
        // we're done, we reset loading state
        this[`loading${number}`] = false
      }, 3000)
    },
    startComputing (percentageId, modelId) {
      this[`loading${modelId}`] = true
      this[`percentage${percentageId}`] = 0
      const interval = setInterval(() => {
        this[`percentage${percentageId}`] += Math.floor(Math.random() * 8 + 10)
        if (this[`percentage${percentageId}`] >= 100) {
          clearInterval(interval)
          this[`loading${modelId}`] = false
        }
      }, 700)
    },
    alert () {
      this.$q.dialog({
        title: 'Good job!'
      })
    }
  },
  beforeDestroy () {
    clearInterval(this.interval1)
    clearInterval(this.interval2)
  }
}
</script>

<style lang="stylus">
.docs-btn
  .q-btn
    margin 5px
  .btn-fixed-width
    width 200px
</style>
