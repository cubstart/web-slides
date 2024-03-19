<template>
  <div class="slidev-layout cover" :style="style">
    <div class="my-auto w-full">
      <div class="flex items-center">
        <img class="w-20 ml-12 mr-12 mb-4" src="../images/cubstart-logo.png" alt="cubstart logo" />
        <div>
          <slot />
        </div>
      </div>
    </div>
  </div>
</template>
