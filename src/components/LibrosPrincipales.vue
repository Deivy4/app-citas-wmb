

<template>
  <main class="main">
    <h2>Libros principales</h2>
    <section class="main-buttons">
      <button @click="openInNewTab('file1')" class="btn-doc">Edades Editado</button>
      <button @click="openInNewTab('file5')" class="btn-doc">Edades sin editar</button>
      <button @click="openInNewTab('file2')" class="btn-doc">Libro de Citas</button>
      <button @click="openInNewTab('file3')" class="btn-doc">Libro de Los Sellos</button>
      <button @click="openInNewTab('file4')" class="btn-doc">Setenta Semanas de Daniel</button>
    </section>
  </main>
</template>

<script setup>

const fileUrls = {
  file1: "/pdfs/Edades-editado.pdf",
  file2: "/pdfs/Libro-de-Citas.pdf",
  file3: "/pdfs/Sellos.pdf",
  file4: "/pdfs/Setenta-Semanas-de-Daniel.pdf",
  file5: "/pdfs/Edades-sin-editar.pdf",
}

function openInNewTab(fileKey){
  const urlPdf = fileUrls[fileKey];  
  window.open(urlPdf,"_blank")
}
</script>

<style scoped>
.main{
  height: 150px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.main-buttons {
  width: 700px;
  flex-wrap: wrap; 
  display: flex;
  gap: 16px;
  justify-content: center;
  align-items: center;
}
.btn-doc{
  width: fit-content;
  max-height: 45px;
  max-width: 100%;
  white-space: nowrap;
}
</style>
