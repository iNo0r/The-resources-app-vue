<template>
  <li>
    <div>
      <header>
        <base-button class="delete-button" mode='flat'>delete</base-button>
        <h2> {{res.title}} </h2>
      </header>
    </div>
    <p> {{res.description}}</p>
    <nav>
        <a :href="res.link">view resources</a>
    </nav>
  </li>
</template>

<script>
export default {
  props: ["res"],
};
</script>

<style>
.delete-button{
    float: right;

}
li {
    list-style: none;
}

a {
    color: orange;
}
</style>
