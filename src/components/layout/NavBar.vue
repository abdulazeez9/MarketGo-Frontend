<script setup lang="ts">
import { ref } from 'vue'

const menuOpen = ref(false)
</script>

<template>
  <nav class="bg-background border-b border-border sticky top-0 z-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <!-- Logo -->
        <RouterLink to="/" class="text-xl font-bold text-primary tracking-tight">
          MarketGo
        </RouterLink>

        <!-- Desktop Links -->
        <div class="hidden md:flex items-center gap-6">
          <RouterLink
            to="/products"
            class="text-text-muted hover:text-heading transition-colors text-sm"
            active-class="text-heading font-medium"
          >
            Products
          </RouterLink>

          <RouterLink
            to="/seller/dashboard"
            class="text-text-muted hover:text-heading transition-colors text-sm"
            active-class="text-heading font-medium"
          >
            Dashboard
          </RouterLink>

          <RouterLink
            to="/admin"
            class="text-text-muted hover:text-heading transition-colors text-sm"
            active-class="text-heading font-medium"
          >
            Admin
          </RouterLink>
        </div>

        <!-- CTA / Auth -->
        <div class="hidden md:flex items-center gap-3">
          <template>
            <!-- <span class="text-sm text-text-muted">{{ auth.user?.email }}</span> -->
            <button
              class="text-sm px-4 py-2 rounded-md border border-border hover:border-border-hover text-heading transition-colors"
            >
              Logout
            </button>
          </template>

          <template>
            <RouterLink
              to="/login"
              class="text-sm text-text-muted hover:text-heading transition-colors"
            >
              Login
            </RouterLink>
            <RouterLink
              to="/register"
              class="text-sm px-4 py-2 rounded-md bg-primary hover:bg-primary-hover text-white transition-colors"
            >
              Get Started
            </RouterLink>
          </template>
        </div>

        <!-- Mobile Hamburger -->
        <button
          class="md:hidden text-heading"
          @click="menuOpen = !menuOpen"
          aria-label="Toggle menu"
        >
          <svg
            v-if="!menuOpen"
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
          </svg>
          <svg v-else class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </button>
      </div>
    </div>

    <!-- Mobile Menu -->
    <div
      v-if="menuOpen"
      class="md:hidden border-t border-border bg-background-soft px-4 py-3 flex flex-col gap-3"
    >
      <RouterLink
        to="/products"
        class="text-sm text-text-muted hover:text-heading"
        @click="menuOpen = false"
      >
        Products
      </RouterLink>
      <RouterLink
        to="/seller/dashboard"
        class="text-sm text-text-muted hover:text-heading"
        @click="menuOpen = false"
      >
        Dashboard
      </RouterLink>
      <RouterLink
        to="/admin"
        class="text-sm text-text-muted hover:text-heading"
        @click="menuOpen = false"
      >
        Admin
      </RouterLink>

      <div class="pt-2 border-t border-border flex flex-col gap-2">
        <template>
          <button class="text-sm text-left text-heading">Logout</button>
        </template>
        <template>
          <RouterLink
            to="/login"
            class="text-sm text-text-muted hover:text-heading"
            @click="menuOpen = false"
            >Login</RouterLink
          >
          <RouterLink
            to="/register"
            class="text-sm px-4 py-2 rounded-md bg-primary text-white text-center"
            @click="menuOpen = false"
          >
            Get Started
          </RouterLink>
        </template>
      </div>
    </div>
  </nav>
</template>
