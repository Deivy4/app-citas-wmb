<template>
  <main class="contenedor-principal">
    <div class="test">
      <!-- Renderiza TODOS los iframes pero solo muestra el activo -->
      <iframe 
        v-for="(url, key) in fileUrls" 
        :key="key"
        :src="url"
        width="100%" 
        height="450px" 
        frameborder="0"
        v-show="currentFile === key"
      ></iframe>
    </div>

    <!-- botones -->
    <section class="main-buttons">
      <button 
        v-for="btn in buttons" 
        :key="btn.key"
        @click="setFile(btn.key)" 
        class="btn-doc"
        :class="{ active: currentFile === btn.key }"
      >
        <span class="span-color-pages">{{`${btn.labelPages} `}}</span>

        <span class="span-color">{{ btn.label }}</span>
      </button>
    </section>

    <LinksWMB/>
    <LibrosPrincipales/>
  </main>
</template>

<script setup>
import { ref } from 'vue'
import LinksWMB from './components/Links.vue';
import LibrosPrincipales from './components/LibrosPrincipales.vue';

// URLs de Google Docs
const fileUrls = {
  file1: "https://docs.google.com/document/d/1MIORzN3JcvAZREjGvhVtZBhl1iXEYSl1ikSRGyL7gDI/edit?tab=t.0",
  file2: "https://docs.google.com/document/d/1t8mSWbnENVb7hBlhEXeUvHJCW9S2jYGdiLG9BvyBTDc/edit?tab=t.0",
  file3: "https://docs.google.com/document/d/1NLPRKz2ULfBI9IPLS0_QBrNzhVOrgmOnC0CUA2HIPT4/edit?tab=t.0",
  file4: "https://docs.google.com/document/d/1Fqn7tMK-ciC8y7NUiBDc3PQ-8ffttn_37nogCLzoSsk/edit?tab=t.0",
  file5: "https://docs.google.com/document/d/18TetVPyHggXU-WJp3aN6QKIAGkv7I65fWYl6Zby89Lg/edit?tab=t.0",
  file6: "https://docs.google.com/document/d/1SQIXaMT8UY18LAZb4wBZcZLzsW0PP13BqG4gY4ylJi8/edit?tab=t.0",
  file7: "https://docs.google.com/document/d/1kE2lOfCeAPx5-9Me7cMcucU9lVFoAHGUqeWRmOf19SY/edit?tab=t.0",
  file8: "https://docs.google.com/document/d/1EvgLnyf0aLnJT9cNgDcCs17zIB2QNOPz2g4JAQpLJnY/edit?tab=t.0"
}

// Definimos los botones con su key y label (nombre que quieres mostrar)
const buttons = [
  { key: 'file1', labelPages: "Pags: 1-26 (...)", label: '001-218' },
  { key: 'file2', labelPages: "Pags: 26-53 (...)", label: '219-462' },
  { key: 'file3', labelPages: "Pags: 54-84 (...)", label: '463-717' },
  { key: 'file4', labelPages: "Pags: 54-112 (...)", label: '718-987' },
  { key: 'file5', labelPages: "Pags: 113-141 (...)", label: '988-1260' },
  { key: 'file6', labelPages: "Pags: 141-171 (...)", label: '1261-1539' },
  { key: 'file7', labelPages: "", label: '1A-a-12A_p116' },
  { key: 'file8', labelPages: "", label: '12A_p117-a-10B' }
]

// Documento activo
const currentFile = ref("file1")

function setFile(fileKey) {
  currentFile.value = fileKey
}
</script>

<style scoped>
.span-color-pages{
  color: #9a4de3;
  font-weight: bold;
}
.span-color{
  color: #9a4de3;
}

.test{
  display: flex;
  flex-direction: column;
  gap: 0;
}

.contenedor-principal{
  display:flex;
  flex-direction: column;
  gap: 40px;
}

.main-buttons {
  width: 100%;
  flex-wrap: wrap; 
  display: flex;
  gap: 16px;
  justify-content: center;
  align-items: center;
}

.btn-doc{
  width: fit-content;
  max-height: 45px;
  white-space: nowrap;
}

/* botón activo */
.btn-doc.active {
  background-color: #007bff;
  color: white !important;
  border: 1px solid #0056b3;
}
.btn-doc.active .span-color, .btn-doc.active .span-color-pages{
  color: white;
}
</style>
