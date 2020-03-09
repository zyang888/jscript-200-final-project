<template>
<client-only>
<Game></Game>
</client-only>
</template>

<script>
import Game from '~/components/game'
export default {
  name: 'game',
  components: {
    Game
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Teko:700');

    canvas{
        border: 1px solid #000;
        display: block;
        margin: 0 auto;
    }
</style>
