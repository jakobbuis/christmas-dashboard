<template>
    <div id="app">
        <nav class="navbar is-danger">
            <div class="navbar-brand">
                <h1 class="navbar-item">
                    Christmas
                </h1>
            </div>
        </nav>

        <div class="container">
            <div class="tile is-ancestor">
                <div class="tile is-3">
                    <box title="Meeting room lights">
                        <klimaat></klimaat>
                    </box>
                </div>
                <div class="tile is-9">
                    <box title="Sonos public address system">
                        <public-address></public-address>
                    </box>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'app',
}
</script>

<style lang="scss">
@import './node_modules/bulma/bulma.sass';

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
