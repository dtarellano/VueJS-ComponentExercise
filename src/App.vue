<template>
   <div class="container">
      <div class="row">
         <div class="col-xs-12">
            <br>
            <button class="btn btn-primary" @click="viewComponent('Blue')">Load Blue Template</button>
            <button class="btn btn-success" @click="viewComponent('Green')">Load Green Template</button>
            <button class="btn btn-danger" @click="viewComponent('Red')">Load Red Template</button>
            <hr>
            <component :is="currentComponent">
               <p>You are in the "{{ text }}" Component</p>
            </component>
         </div>
      </div>
   </div>
</template>

<script>
import Blue from "./components/Blue.vue";
import Green from "./components/Green.vue";
import Red from "./components/Red.vue";

export default {
   data() {
      return {
         currentComponent: "appBlue",
         currentText: "Blue"
      };
   },
   components: {
      appBlue: Blue,
      appGreen: Green,
      appRed: Red
   },
   methods: {
      viewComponent(view) {
         this.currentComponent = `app${view}`;
         this.currentText = view;
      }
   }
};
</script>

<style>
</style>
