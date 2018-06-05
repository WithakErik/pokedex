<template>
  <div>
    <form>
      <fieldset>
        <legend>Sort by</legend>
        <select v-model="sortPreferences.selectedSort">
          <option v-for="oneOption in sortPreferences.sortOptions"
            v-bind:key="oneOption" 
            v-bind:value="oneOption">
            {{ oneOption }}
          </option>
        </select>
        <select v-model="sortPreferences.selectedDirection">
          <option v-for="oneOption in sortPreferences.directionOptions"
            v-bind:key="oneOption" 
            v-bind:value="oneOption">
            {{ oneOption }}
          </option>
        </select>
      </fieldset>
    </form> 
  </div>
</template>

<script>
export default {
  props: ['sortPreferences']
};
</script>

<style>

</style>