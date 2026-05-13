<script setup>
import { ref } from 'vue'
import PhysicsScene from './components/PhysicsScene.vue'
import ControlPanel from './components/ControlPanel.vue'

const gravity = ref(1.0)
const mass = ref(5)

const handleReset = () => {
  window.location.reload()
}

const teamMembers = [
  { name: "Improatus Soliha", nim: "20251337006" },
  { name: "Fairuz Abdillah Idrus", nim: "20251337014" },
  { name: "Moh. Faiz Haikal", nim: "20251337015" },
  { name: "Abi Ibryan Naisa Putra", nim: "202513337025" },
  { name: "Wfaa Abdelalem Omer Abdelalem", nim: "20251337031" },
  { name: "Abidzar Dzakwan Sahudi", nim: "20251337037" },
]
</script>

<template>
  <main class="min-h-screen bg-[#020617] text-slate-100 flex flex-col">

    <header class="p-8 text-center space-y-4">
      <h1 class="text-2xl md:text-5xl font-black text-transparent bg-clip-text bg-gradient-to-r from-sky-400 via-emerald-400 to-sky-400">
        PhysicGame: Bird Engine
      </h1>
    </header>

    <div class="flex-grow max-w-7xl mx-auto w-full px-4 grid grid-cols-1 xl:grid-cols-4 gap-8 pb-12">
      <div class="xl:col-span-3">
        <div class="relative group">
          <div class="absolute -inset-1 bg-gradient-to-r from-sky-500 to-emerald-500 rounded-3xl blur opacity-20 transition duration-1000 group-hover:opacity-40"></div>
          <div class="relative bg-slate-900/80 border border-white/10 backdrop-blur-xl rounded-2xl overflow-hidden shadow-2xl">
            <PhysicsScene :gravity="gravity" :mass="mass" />
          </div>
        </div>
      </div>

      <div class="xl:col-span-1">
        <ControlPanel v-model:gravity="gravity" v-model:mass="mass" @reset="handleReset" />
      </div>
    </div>

    <footer class="mt-auto border-t border-white/5 bg-slate-900/50 backdrop-blur-md p-10">
      <div class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-12 text-sm">
        <div class="space-y-6">
          <div class="space-y-2">
            <h4 class="text-sky-400 font-bold uppercase tracking-widest text-xs flex items-center gap-2">
              Kelompok 1 - Teknik Informatika
            </h4>
            <p class="text-slate-500 text-[11px] font-mono tracking-tighter uppercase">
              Physics Informatics Simulation Project © 2026
            </p>
          </div>

          <ul class="grid grid-cols-1 sm:grid-cols-2 gap-x-8 gap-y-4 text-slate-400">
            <li v-for="member in teamMembers" :key="member.nim" class="group border-l border-white/5 pl-4 hover:border-sky-500/50 transition-colors">
            <span class="font-semibold block text-slate-200 group-hover:text-sky-300 transition-colors">
              {{ member.name }}
            </span>
              <span class="text-xs opacity-50 font-mono">{{ member.nim }}</span>
            </li>
          </ul>
        </div>

        <div class="flex flex-col justify-between items-start md:items-end text-left md:text-right space-y-6">
          <div class="space-y-2">
            <h4 class="text-emerald-400 font-bold uppercase tracking-widest text-xs">Mata Kuliah</h4>
            <p class="text-slate-200 font-bold text-lg leading-tight">Fisika Informatika</p>
            <p class="text-slate-500 text-xs">Universitas Muhammadiyah Surabaya</p>
          </div>
        </div>

      </div>
    </footer>
  </main>
</template>