

<template>
  <main class="main">
    <h2>Links WMB</h2>
    <section class="main-buttons">
      <button @click="openInNewTab('link1')" class="btn-doc oficial">Traducción oficial WMB</button>
      <button @click="openInNewTab('link2')" class="btn-doc">The message WMB</button>
      <button @click="openInNewTab('link3')" class="btn-doc">DOVE</button>
    </section>
  </main>
</template>

<script setup>

const links = {
  link1: "https://table.branham.org/#/es/main",
  link2: "https://themessage.com/es/sermonsdownload",
  link3: "https://tabernaculozoe.org/dove/"
}

function openInNewTab(fileKey){
  const urlButton = links[fileKey];  
  window.open(urlButton,"_blank")
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
.oficial{
    color: #d94917;
}
</style>
