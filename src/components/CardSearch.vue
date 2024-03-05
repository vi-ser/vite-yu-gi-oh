<script>
import { store } from '../store';

export default {
    name: 'CardSearch',
}


</script>

<template>
<div class="dropdown">
  <button class="btn btn-secondary dropdown-toggle rounded-0" type="button" data-bs-toggle="dropdown" aria-expanded="false">
    Seleziona Archetipo
  </button>
  <ul class="dropdown-menu rounded-0">
    <li><a class="dropdown-item rounded-0" href="#">Action</a></li>
  </ul>
</div>
</template>

<style lang="scss">
@use '../styles/general' as *;
@use '../styles/variables' as *;

.btn {
    margin-bottom:calc(2 * $cardsGap );
    background-color: #242424;
    border: 1px solid #242424;

    &:hover {
      background-color: #595959;
    }
}
</style>