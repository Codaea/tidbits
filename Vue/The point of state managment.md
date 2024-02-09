
state management is pretty much a way so we don't have to pass objects up and around in order to do things, 

### Ex. 1 (without state managment)
> Create a parent component that has 2 child components that one will need to send info to the other.

```vue
<!-- ParentComponent.vue -->
<script setup>
import { ref } from 'vue';
import ChildA from './ChildA.vue';
import ChildB from './ChildB.vue';
  
const parentData = ref('');

function updateParentData(newData) {
	parentData.value = newData 
}
</script>

<template>
  <div>
    <h2>Parent Component</h2>
    <ChildA @child-updated="updateParentData" />
    <ChildB :data="parentData"/>
  </div>
</template>
```

```vue
<!-- ChildA.vue -->
<script setup>
import { ref, watch, onMounted, emit } from 'vue';

const emitUpdate = defineEmits['child-update'];

const localData = ref('')

function emitUpdate() {
emit('child-update', localData)
}
</script>



<template>
  <div>
    <h3>Child A Component</h3>
	    <input type="text" v-model="localData" @input="emitUpdate" placeholder="Enter text">
  </div>
</template>

```

#TODO finish this example

```vue
<!-- ChildB.vue -->
<script setup>
import { ref }

const data = ref('')


</script>


<template>
	<h1>{{ data }}</h1>
</template>
```


this example is big and clunky, and we need the parent component to orchestrate the two receiving information. this is what state management is for. **State management is for orchestrating connections between multiple components that need the same info/data.**

### Using State Management: Pinia

pinia uses individual files for each store, for more modual based code 


state management is for making things that multiple components use to set and get from easy for everything to reach