<template>
  <div>
    <h2>Verano</h2>
    <div class="contenedor">
      <img :src="caja" :width="585" :height="430"/>
    </div>
    <div class="grid-container">
      <div class="forma">
        <div id="1" class="color" @dragover="handleDragOver" @drop="handleDrop(1)"></div>
        <div id="4" class="color" @dragover="handleDragOver" @drop="handleDrop(4)"></div>
        <div id="7" class="color" @dragover="handleDragOver" @drop="handleDrop(7)"></div>
        <div id="10" class="color" @dragover="handleDragOver" @drop="handleDrop(10)"></div>
      </div>
      <div class="forma">
        <div id="2" class="color" @dragover="handleDragOver" @drop="handleDrop(2)"></div>
        <div id="5" class="color" @dragover="handleDragOver" @drop="handleDrop(5)"></div>
        <div id="8" class="color" @dragover="handleDragOver" @drop="handleDrop(8)"></div>
        <div id="11" class="color" @dragover="handleDragOver" @drop="handleDrop(11)"></div>
      </div>
      <div class="forma">
        <div id="3" class="color" @dragover="handleDragOver" @drop="handleDrop(3)"></div>
        <div id="6" class="color" @dragover="handleDragOver" @drop="handleDrop(6)"></div>
        <div id="9" class="color" @dragover="handleDragOver" @drop="handleDrop(9)"></div>
        <div id="12" class="color" @dragover="handleDragOver" @drop="handleDrop(12)"></div>
      </div>
    </div>
    <div class="cuadro-imagenes">
      <img
        v-for="image in images"
        :key="image.id"
        :src="image.pieza"
        :width="210"
        :height="120"
        draggable="true"
        @dragstart="handleDragStart(image.id)"
      />
    </div>
  </div>
  <div class="contenedor-imagen">
    <img :src="imagen" :width="240" :height="170"/>
  </div>
</template>

<script setup>
import { ref } from "vue";

const images = ref([
  { id: 1, pieza: './src/assets/Verano/11.png' },
  { id: 2, pieza: './src/assets/Verano/12.png' },
  { id: 3, pieza: './src/assets/Verano/13.png' },
  { id: 4, pieza: './src/assets/Verano/21.png' },
  { id: 5, pieza: './src/assets/Verano/22.png' },
  { id: 6, pieza: './src/assets/Verano/23.png' },
  { id: 7, pieza: './src/assets/Verano/31.png' },
  { id: 8, pieza: './src/assets/Verano/32.png' },
  { id: 9, pieza: './src/assets/Verano/33.png' },
  { id: 10, pieza: './src/assets/Verano/41.png' },
  { id: 11, pieza: './src/assets/Verano/42.png' },
  { id: 12, pieza: './src/assets/Verano/43.png' },
]);

const caja = './src/assets/Verano/VeranoR.jpg';
const draggedItemId = ref(null);
const imagen='./src/assets/Verano/Verano.jpg';

const handleDragStart = (itemId) => {
  draggedItemId.value = itemId;
};

const handleDragOver = (event) => {
  event.preventDefault();
};

const handleDrop = (targetId) => {
  if (draggedItemId.value) {
    const draggedImage = images.value.find((image) => image.id === parseInt(draggedItemId.value));
    if (draggedImage) {
      if (draggedImage.id === 1 && targetId === 1) {
        const index = images.value.findIndex((image) => image.id === draggedImage.id);
        if (index !== -1) {
          images.value.splice(index, 1);
        }

        const dropDiv = document.getElementById(targetId.toString());
        if (dropDiv) {
          const imgElement = document.createElement("img");
          imgElement.src = draggedImage.pieza;
          imgElement.style.position="relative";
          imgElement.style.width="223px";
          imgElement.style.height="113px";
          imgElement.style.left="3px";
          imgElement.style.top="-1px"
          imgElement.draggable = false;
          draggedItemId.value = null;
          dropDiv.innerHTML = "";
          dropDiv.appendChild(imgElement);
        }
      }
    
      if (draggedImage.id === 2 && targetId === 2) {
        const index = images.value.findIndex((image) => image.id === draggedImage.id);
        if (index !== -1) {
          images.value.splice(index, 1);
        }

        const dropDiv = document.getElementById(targetId.toString());
        if (dropDiv) {
          const imgElement = document.createElement("img");
          imgElement.src = draggedImage.pieza;
          imgElement.style.position="relative";
          imgElement.style.width="231px";
          imgElement.style.height="113px";
          imgElement.style.right="9px";
          imgElement.style.top="-2px";
          imgElement.draggable = false;
          draggedItemId.value = null;
          dropDiv.innerHTML = "";
          dropDiv.appendChild(imgElement);
        }
      }

      if (draggedImage.id === 3 && targetId === 3) {
        const index = images.value.findIndex((image) => image.id === draggedImage.id);
        if (index !== -1) {
          images.value.splice(index, 1);
        }

        const dropDiv = document.getElementById(targetId.toString());
        if (dropDiv) {
          const imgElement = document.createElement("img");
          imgElement.src = draggedImage.pieza;
          imgElement.style.position="relative";
          imgElement.style.width="207px";
          imgElement.style.height="132px";
          imgElement.style.right="13px";
          imgElement.style.top="-3px";
          imgElement.draggable = false;
          draggedItemId.value = null;
          dropDiv.innerHTML = "";
          dropDiv.appendChild(imgElement);
        }
      }

      if (draggedImage.id === 4 && targetId === 4) {
        const index = images.value.findIndex((image) => image.id === draggedImage.id);
        if (index !== -1) {
          images.value.splice(index, 1);
        }

        const dropDiv = document.getElementById(targetId.toString());
        if (dropDiv) {
          const imgElement = document.createElement("img");
          imgElement.src = draggedImage.pieza;
          imgElement.style.position="relative";
          imgElement.style.width="209px";
          imgElement.style.height="154px";
          imgElement.style.top="-26px"
          imgElement.style.left="2px"
          imgElement.draggable = false;
          draggedItemId.value = null;
          dropDiv.innerHTML = "";
          dropDiv.appendChild(imgElement);
        }
      }

      if (draggedImage.id === 5 && targetId === 5) {
        const index = images.value.findIndex((image) => image.id === draggedImage.id);
        if (index !== -1) {
          images.value.splice(index, 1);
        }

        const dropDiv = document.getElementById(targetId.toString());
        if (dropDiv) {
          const imgElement = document.createElement("img");
          imgElement.src = draggedImage.pieza;
          imgElement.style.position="relative";
          imgElement.style.width="252px";
          imgElement.style.height="142px";
          imgElement.style.top="-27px";
          imgElement.style.right="27px";
          imgElement.draggable = false;
          draggedItemId.value = null;
          dropDiv.innerHTML = "";
          dropDiv.appendChild(imgElement);
        }
      }

      if (draggedImage.id === 6 && targetId === 6) {
        const index = images.value.findIndex((image) => image.id === draggedImage.id);
        if (index !== -1) {
          images.value.splice(index, 1);
        }

        const dropDiv = document.getElementById(targetId.toString());
        if (dropDiv) {
          const imgElement = document.createElement("img");
          imgElement.src = draggedImage.pieza;
          imgElement.style.position="relative";
          imgElement.style.width="205px";
          imgElement.style.height="138px";
          imgElement.style.top="-11px";
          imgElement.style.right="12px";
          imgElement.draggable = false;
          draggedItemId.value = null;
          dropDiv.innerHTML = "";
          dropDiv.appendChild(imgElement);
        }
      }

      if (draggedImage.id === 7 && targetId === 7) {
        const index = images.value.findIndex((image) => image.id === draggedImage.id);
        if (index !== -1) {
          images.value.splice(index, 1);
        }

        const dropDiv = document.getElementById(targetId.toString());
        if (dropDiv) {
          const imgElement = document.createElement("img");
          imgElement.src = draggedImage.pieza;
          imgElement.style.position="relative";
          imgElement.style.width="222px";
          imgElement.style.height="118px";
          imgElement.style.top="-9px";
          imgElement.style.left="5px";
          imgElement.draggable = false;
          draggedItemId.value = null;
          dropDiv.innerHTML = "";
          dropDiv.appendChild(imgElement);
        }
      }


      if (draggedImage.id === 8 && targetId === 8) {
        const index = images.value.findIndex((image) => image.id === draggedImage.id);
        if (index !== -1) {
          images.value.splice(index, 1);
        }

        const dropDiv = document.getElementById(targetId.toString());
        if (dropDiv) {
          const imgElement = document.createElement("img");
          imgElement.src = draggedImage.pieza;
          imgElement.style.position="relative";
          imgElement.style.width="236px";
          imgElement.style.height="132px";
          imgElement.style.top="-22px";
          imgElement.style.right="9px";
          imgElement.draggable = false;
          draggedItemId.value = null;
          dropDiv.innerHTML = "";
          dropDiv.appendChild(imgElement);
        }
      }
      if (draggedImage.id === 9 && targetId === 9) {
        const index = images.value.findIndex((image) => image.id === draggedImage.id);
        if (index !== -1) {
          images.value.splice(index, 1);
        }

        const dropDiv = document.getElementById(targetId.toString());
        if (dropDiv) {
          const imgElement = document.createElement("img");
          imgElement.src = draggedImage.pieza;
          imgElement.style.position="relative";
          imgElement.style.width="201px";
          imgElement.style.height="120px";
          imgElement.style.top="-11px";
          imgElement.style.right="9px";
          imgElement.draggable = false;
          draggedItemId.value = null;
          dropDiv.innerHTML = "";
          dropDiv.appendChild(imgElement);
        }
      }


      if (draggedImage.id === 10 && targetId === 10) {
        const index = images.value.findIndex((image) => image.id === draggedImage.id);
        if (index !== -1) {
          images.value.splice(index, 1);
        }

        const dropDiv = document.getElementById(targetId.toString());
        if (dropDiv) {
          const imgElement = document.createElement("img");
          imgElement.src = draggedImage.pieza;
          imgElement.style.position="relative";
          imgElement.style.width="226px";
          imgElement.style.height="128px";
          imgElement.style.top="-27px";
          imgElement.style.left="4px";
          imgElement.draggable = false;
          draggedItemId.value = null;
          dropDiv.innerHTML = "";
          dropDiv.appendChild(imgElement);
        }
      }

      if (draggedImage.id === 11 && targetId === 11) {
        const index = images.value.findIndex((image) => image.id === draggedImage.id);
        if (index !== -1) {
          images.value.splice(index, 1);
        }

        const dropDiv = document.getElementById(targetId.toString());
        if (dropDiv) {
          const imgElement = document.createElement("img");
          imgElement.src = draggedImage.pieza;
          imgElement.style.position="relative";
          imgElement.style.width="212px";
          imgElement.style.height="127px";
          imgElement.style.top="-27px";
          imgElement.style.right="7px";
          imgElement.draggable = false;
          draggedItemId.value = null;
          dropDiv.innerHTML = "";
          dropDiv.appendChild(imgElement);
        }
      }
      if (draggedImage.id === 12 && targetId === 12) {
        const index = images.value.findIndex((image) => image.id === draggedImage.id);
        if (index !== -1) {
          images.value.splice(index, 1);
        }

        const dropDiv = document.getElementById(targetId.toString());
        if (dropDiv) {
          const imgElement = document.createElement("img");
          imgElement.src = draggedImage.pieza;
          imgElement.style.position="relative";
          imgElement.style.width="222px";
          imgElement.style.height="127px";
          imgElement.style.top="-27px";
          imgElement.style.right="30px";
          imgElement.draggable = false;
          draggedItemId.value = null;
          dropDiv.innerHTML = "";
          dropDiv.appendChild(imgElement);
        }
      }
    }
    draggedItemId.value = null;
  }
};
</script>
<style scoped>
.grid-container {
    display: flex;
    gap: 0;
    flex-wrap: wrap;
    position: absolute;
    top: 166px;
    left: 386px;
    z-index: 1;
  }

.color {
  border: 1px solid #ffffff00;
  background-color: rgba(0, 0, 0, 0);
  height: 105px;
  width: 192px;
  margin: 0;
}

.forma {
  display: inline-block;
}

.contenedor{
  position: relative;
  top: 0;
  left: 5px;
}

.cuadro-imagenes {
    position: relative; 
    left: 650px;
    top: -425px;
    width: 250px;
    height: 430px;
    overflow: auto;
    border: 1px solid #ccc;
    z-index: 0;
}

.contenedor-imagen {
  padding: 10px;
  margin-bottom: 20px;
  position: relative;
  top: -878px;
  right: 500px;
}
</style>
