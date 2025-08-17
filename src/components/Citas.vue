

<template>
  <main class="main">
    <h2>Citas WMB</h2>
    <section class="main-buttons">
      <button @click="openInNewTab('file1')" class="btn-doc">001-218</button>
      <button @click="openInNewTab('file2')" class="btn-doc">219-462</button>
      <button @click="openInNewTab('file3')" class="btn-doc">463-717</button>
      <button @click="openInNewTab('file4')" class="btn-doc">718-987</button>
      <button @click="openInNewTab('file5')" class="btn-doc">988-1260</button>
      <button @click="openInNewTab('file6')" class="btn-doc">1261-1539</button>
      <button @click="openInNewTab('file7')" class="btn-doc">1A-a-12A_p116</button>
      <button @click="openInNewTab('file8')" class="btn-doc">12A_p117-a-10B</button>
    </section>
  </main>
</template>

<script setup>

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

function openInNewTab(fileKey){
  const urlDrive = fileUrls[fileKey];
  console.log(urlDrive);
  
  window.open(urlDrive,"_blank")
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
