<template>
  <div class="flash-sale section nacelle">
    <div class="container">
      <slot name="header" :title="title">
        <component :is="titleTag" class="title has-text-centered">
          {{ title }}
        </component>
      </slot>
      <slot name="products" :products="products">
        <flash-sale :products="products" />
      </slot>
      <slot name="cta" v-bind="{ callToActionUrl, callToActionText, ctaHandler }">
            <p v-if="callToActionText.length > 0">
              <cta-button :to="callToActionUrl" @clicked="ctaHandler">{{
                ctaText
              }}</cta-button>
                 </p>
          </slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: ''
    },
    products: {
      type: Array,
      default: () => []
    },
    callToActionText: {
      type: String,
      default: ''
    },
    callToActionUrl: {
      type: String,
      default: ''
    },
    saleCountdown: {
        type: String,
        default: ''
    }
  }
}
</script>

<style></style>