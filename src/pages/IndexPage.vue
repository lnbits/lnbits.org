<template>
  <q-layout class="bg-gradient">
    <q-header class="bg-dark q-py-md" reveal height-hint="60">
      <q-toolbar class="text-grey-1 q-px-md">
        <div class="q-pr-lg">
          <img class="logo" src="https://lnbits.com/assets/images/logo/logo.svg" />
        </div>

        <q-space />

        <q-btn-toggle v-model="topLinks" flat stretch toggle-color="accent" :options="options" />
      </q-toolbar>
    </q-header>
    <q-page-container>
      <q-page>
        <div class="content-center hero">
          <div class="text-h2 text-center text-white q-mt-md text-weight-bold">
            Accept Bitcoin Payments Instantly
          </div>
          <div class="text-h5 text-center text-grey-4 q-mt-lg">
            Accept Bitcoin and Lightning payments easily—no technical expertise required.
          </div>
          <div>
            <div class="q-mt-lg row flex-center q-gutter-md">
              <q-btn
                class="text-capitalize"
                color="accent"
                label="Get Started"
                href="https://my.lnbits.com"
                target="_blank"
                rel="noopener noreferrer"
                size="lg"
                rounded
                padding="md lg"
                unelevated
              />
              <q-btn
                class="text-capitalize"
                color="grey-4"
                label="See How It Works"
                href="https://docs.lnbits.org/"
                target="_blank"
                rel="noopener noreferrer"
                size="lg"
                rounded
                outline
                padding="md lg"
              />
            </div>
            <div class="text-center text-grey-5 q-py-md">
              Open-source, privacy-first, and trusted by merchants worldwide.
            </div>
          </div>
        </div>
        <div class="full-width bg-grey-1 q-py-xl q-px-md">
          <div style="max-width: 900px; margin: 0 auto">
            <div class="text-center text-h5 q-mb-lg">Get Started in 3 Easy Steps</div>
            <div class="row flex q-col-gutter-lg q-my-lg">
              <div class="col-12 col-md-4 flex">
                <q-card class="q-pa-md bg-white text-center full-width">
                  <div class="text-h3 text-accent q-mb-sm">1</div>
                  <div class="text-h6 text-weight-bold q-mb-xs">Create Your Wallet</div>
                  <div class="text-body1 text-grey-7">
                    Use our SaaS platform, or self-host to instantly generate a Bitcoin/Lightning
                    wallet for your business.
                  </div>
                </q-card>
              </div>
              <div class="col-12 col-md-4 flex">
                <q-card class="q-pa-md bg-white text-center full-width">
                  <div class="text-h3 text-accent q-mb-sm">2</div>
                  <div class="text-h6 text-weight-bold q-mb-xs">Install Extensions</div>
                  <div class="text-body1 text-grey-7">
                    Add PoS, Invoicing, and more. Customize your LNbits experience to fit your
                    business needs.
                  </div>
                </q-card>
              </div>
              <div class="col-12 col-md-4 flex">
                <q-card class="q-pa-md bg-white text-center full-width">
                  <div class="text-h3 text-accent q-mb-sm">3</div>
                  <div class="text-h6 text-weight-bold q-mb-xs">Get Paid Instantly</div>
                  <div class="text-body1 text-grey-7">
                    Receive Bitcoin payments directly, with instant settlement and no middlemen.
                  </div>
                </q-card>
              </div>
            </div>
          </div>
        </div>
        <carousel-element />
        <div class="full-width bg-white q-py-xl q-px-md">
          <div class="text-center text-h5 q-mb-lg">Built for Merchants</div>
          <div class="text-center text-body1 text-grey-7 q-mb-xl">
            LNbits gives you all the tools you need to accept Bitcoin and Lightning payments in your
            store, online or offline. No middlemen, no hidden fees—just fast, secure, and flexible
            payments.
          </div>
          <div class="row flex q-col-gutter-md q-my-lg" style="max-width: 1024px; margin: auto">
            <div class="col-12 col-md-3 flex" v-for="feature in features" :key="feature.title">
              <card-feature
                class="bg-primary text-white"
                :icon="feature.icon"
                :title="feature.title"
                :description="feature.description"
              ></card-feature>
            </div>
          </div>
          <div class="text-center text-h6 q-mt-lg">
            ...and much more! LNbits is modular—add new features anytime. Over 50 extensions
            available, with more on the way.
          </div>
        </div>
        <div class="flex-center q-pa-lg q-py-xl">
          <q-splitter v-model="splitterModel" class="full-height">
            <template v-slot:before>
              <q-tabs v-model="tab" vertical class="text-white">
                <q-tab name="p_1" label="All in One Software" />
                <q-tab name="p_2" label="Easy and Lightweight" />
                <q-tab name="p_3" label="SaaS" />
                <q-tab name="p_4" label="Powerful API" />
              </q-tabs>
            </template>

            <template v-slot:after>
              <q-tab-panels
                v-model="tab"
                animated
                swipeable
                vertical
                transition-prev="jump-up"
                transition-next="jump-up"
                class="bg-transparent text-white text-right"
              >
                <q-tab-panel name="p_1">
                  <div class="text-h4 q-mb-md">All in One Software</div>
                  <div class="text-body1">
                    <p>
                      All in one software for your business. LNbits modular architecture allows you
                      to add new features at any time.
                    </p>
                  </div>
                </q-tab-panel>

                <q-tab-panel name="p_2">
                  <div class="text-h4 q-mb-md">Easy and Light</div>
                  <p>
                    LNbits is easy to use and lightweight. It runs on any device, from a Raspberry
                    Pi to a cloud server. You can get started in minutes.
                  </p>
                </q-tab-panel>

                <q-tab-panel name="p_3">
                  <div class="text-h4 q-mb-md">SaaS</div>
                  <p>
                    Use our SaaS solution to get started quickly. We take care of the
                    infrastructure, so you can focus on your business.
                  </p>
                </q-tab-panel>
                <q-tab-panel name="p_4">
                  <div class="text-h4 q-mb-md">Powerful API</div>
                  <p>
                    Use our powerful API to integrate LNbits with your existing systems. Our API is
                    well-documented and easy to use.
                  </p>
                </q-tab-panel>
              </q-tab-panels>
            </template>
          </q-splitter>
        </div>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'

import CardFeature from 'src/components/CardFeature.vue'
import CarouselElement from 'src/components/CarouselElement.vue'

const topLinks = ref('')
const options = [
  { label: 'Apps', value: 'apps' },
  { label: 'Services', value: 'services' },
]

const features = [
  {
    icon: 'dialpad',
    title: 'PoS',
    description: 'Easy to use Point of Sale system for your business.',
  },
  {
    icon: 'qr_code',
    title: 'Charges',
    description: 'Easily create and manage payment requests.',
  },
  {
    icon: 'receipt',
    title: 'Invoicing',
    description: 'Create and manage invoices with ease.',
  },
  {
    icon: 'inventory',
    title: 'Shared Inventory',
    description: 'Manage your products and stock levels efficiently.',
  },
]

const splitterModel = ref(20)
const tab = ref('p_1')
</script>

<style scoped>
.bg-gradient {
  background-image: linear-gradient(
    111.1deg,
    rgba(0, 128, 128, 1) 2.5%,
    rgba(39, 17, 39, 1) 100.3%
  );
  background-size: cover;
}

.hero {
  min-height: 55vh;
}
.logo {
  width: 98px;
  height: auto;
}
</style>
