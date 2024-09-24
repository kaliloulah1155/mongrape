<template>
  <div class="editor-container">
    <!-- Zone des blocs, positionnée à gauche -->
    <div id="blocks">
      <!-- Contenu des blocs GrapesJS apparaîtra ici -->
    </div>

    <!-- Zone principale de l'éditeur GrapesJS -->
    <div id="gjs">
      <h1>Hello World Component!</h1>
    </div>
  </div>
</template>
<script setup>
import "grapesjs/dist/css/grapes.min.css";
import grapesjs from "grapesjs";

let editor = ref({});

onMounted(() => {
  editor.value = grapesjs.init(grapesInit);
});
</script>
<style scoped>
/* Conteneur principal avec Flexbox */
.editor-container {
  display: flex; /* Activer Flexbox */
  height: 100vh; /* Hauteur pleine page */
}

/* Style pour la zone des blocs */
#blocks {
  width: 300px; /* Largeur fixe pour la barre des blocs */
  background-color: #f7f7f7; /* Couleur de fond */
  border-right: 1px solid #ddd; /* Bordure de séparation */
  padding: 10px; /* Espacement interne */
  overflow-y: auto; /* Permettre le défilement vertical */
}

/* Style pour la zone de l'éditeur */
#gjs {
  flex-grow: 1; /* Occupe tout l'espace restant */
  border: 3px solid #444; /* Bordure de l'éditeur */
}
</style>
