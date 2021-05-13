<template>
  <li>
    <div>
      <header>
        <h3>{{ title }}</h3>
        <button>Eliminar</button>
      </header>
    </div>
    <p>{{ description }}</p>
    <nav>
      <a :href="link">Ir al recurso</a>
    </nav>
  </li>
</template>

<script>
export default {
  props: ['title', 'description', 'link']
}
</script>