<template>
  <div class="hello">
    <input type="text" />

    <div>
        <ul>
            <li>
                <input type='checkbox'>
                <label> hobby </label>
            </li>
            <li>
                <input type='checkbox'>
                <label> praca </label>
            </li>
            <li>
                <input type='checkbox'>
                <label> sport </label>
            </li>
            <li>
                <input type='checkbox'>
                <label> obowiązki </label>
            </li>
            <li>
                <input type='checkbox'>
                <label> inne </label>
            </li>
        </ul>
    </div>

    <div>
        <input type='checkbox' />
        <label> ważne </label>
    </div>

    <button>
        dodaj zadanie
    </button>

    <ul>
        <li> trening siłowy </li>
        <li> nauka Vue.JS </li>
    </ul>

  </div>
</template>

<script>
export default {
  name: 'todoContainer'
}
</script>

<style>

</style>