<script setup lang="ts">
const btn = ref('Upload file')
const fileName = ref('')
const uploadShow = ref(true)
const uploading = ref(false)
const drop = ref(false)
const syncActive = ref(false)
const doneActive = ref(false)
const barActive = ref(false)

function onUpload(e: any) {
  fileName.value = e.target.files[0].name
  uploadShow.value = false
}

function startUpload() {
  if (!uploading.value && fileName.value !== '') {
    uploading.value = true
    btn.value = 'Uploading...'
    drop.value = true
    syncActive.value = true
    doneActive.value = true
    barActive.value = true
    setTimeout(() => {
      btn.value = 'Done'
    }, 3200)
  }
}
</script>

<template>
  <div class="frame">
    <div class="center">
      <div class="bar" :class="{ active: barActive }" />
      <div class="title">
        Drop file to upload
      </div>
      <div v-show="!drop" class="dropzone" :class="{ 'fade-drop': drop }">
        <div class="content">
          <img v-show="uploadShow" src="https://100dayscss.com/codepen/upload.svg" alt="upload">
          <span class="filename">
            {{ fileName }}
          </span>
          <input type="file" class="input" @change="onUpload">
        </div>
      </div>
      <img src="https://100dayscss.com/codepen/syncing.svg" :class="{ active: syncActive }" class="syncing" alt="svg">
      <img src="https://100dayscss.com/codepen/checkmark.svg" :class="{ active: doneActive }" class="done" alt="svg">
      <div class="upload-btn" @click="startUpload">
        {{ btn }}
      </div>
    </div>
  </div>
  <TheCd to="014" class="op-5" :bt="35" />
  <TheCd to="016" :bt="10" />
</template>

<style scoped>
@keyframes fade {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

/* 应用动画到元素 */
.fade-drop {
  animation: fade 2s ease-in-out;
}

.frame {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 400px;
  height: 400px;
  margin-top: -200px;
  margin-left: -200px;
  border-radius: 3px;
  box-shadow: 1px 2px 10px 0 rgba(0, 0, 0, 0.3);
  background: linear-gradient(to top right, #3a92af 0%, #5ca05a 100%);
  color: #fff;
  font-family: 'Open Sans', Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.center {
  position: absolute;
  width: 300px;
  height: 260px;
  top: 70px;
  left: 50px;
  background: #fff;
  box-shadow: 8px 10px 15px 0 rgba(0, 0, 0, 0.3);
  border-radius: 3px;
}

.title {
  font-size: 16px;
  color: #676767;
  line-height: 50px;
  height: 50px;
  border-bottom: 1px solid #d8d8d8;
  text-align: center;
}

.dropzone {
  position: absolute;
  z-index: 1;
  box-sizing: border-box;
  display: table;
  table-layout: fixed;
  width: 100px;
  height: 80px;
  top: 86px;
  left: 100px;
  border: 1px dashed #a4a4a4;
  border-radius: 3px;
  text-align: center;
  overflow: hidden;

  &.is-dragover {
    border-color: #666;
    background: #eee;
  }

  .content {
    display: table-cell;
    vertical-align: middle;
  }

  .upload {
    margin: 6px 0 0 2px;
  }

  .filename {
    display: block;
    color: #676767;
    font-size: 16px;
    line-height: 18px;
  }

  .input {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    opacity: 0;
  }
}

.upload-btn {
  position: absolute;
  width: 140px;
  height: 40px;
  left: 80px;
  bottom: 24px;
  background: #6ece3b;
  border-radius: 3px;
  text-align: center;
  line-height: 40px;
  font-size: 14px;
  box-shadow: 0 2px 0 0 #498c25;
  cursor: pointer;
  transition: all 0.2s ease-in-out;

  &:hover {
    box-shadow:
      0 2px 0 0 #498c25,
      0 2px 10px 0 #6ece3b;
  }
}

.bar {
  position: absolute;
  z-index: 1;
  width: 300px;
  height: 3px;
  top: 49px;
  left: 0;
  background: #6ece3b;
  transform: scaleX(0);
  transform-origin: 0 0;

  &.active {
    transform: scaleX(1) translate3d(0, 0, 0);
  }
}

.syncing {
  position: absolute;
  top: 109px;
  left: 134px;
  opacity: 0;

  &.active {
    animation: syncing 3.2s ease-in-out;
  }
}

.done {
  position: absolute;
  top: 112px;
  left: 132px;
  opacity: 0;

  &.active {
    animation: done 0.5s ease-in 3.2s;
    animation-fill-mode: both;
  }
}

@keyframes syncing {
  0% {
    transform: rotate(0deg);
  }

  10% {
    opacity: 1;
  }

  90% {
    opacity: 1;
  }

  100% {
    transform: rotate(360deg);
    opacity: 0;
  }
}

@keyframes done {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}
</style>
