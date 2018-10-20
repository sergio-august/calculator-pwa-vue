<template>
    <div class="wrapper">
        <div class="calculator">
            <div class="display">{{display}}</div>
            <div class="keypad">
                <div class="key">C</div>
                <div class="key pencil">⌫</div>
                <div class="key">+/-</div>
                <div class="key operator">/</div>
                <div class="key">7</div>
                <div class="key">8</div>
                <div class="key">9</div>
                <div class="key operator">x</div>
                <div class="key">4</div>
                <div class="key">5</div>
                <div class="key">6</div>
                <div class="key operator">-</div>
                <div class="key">1</div>
                <div class="key">2</div>
                <div class="key">3</div>
                <div class="key operator">+</div>
                <div class="key double_column last_row">0</div>
                <div class="key last_row">.</div>
                <div class="key operator last_row">=</div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Calculator',
  data() {
    return {
      display: 0
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    width: 100vw;
}

.calculator {
    display: flex;
    flex-direction: column;
}

.display {
    flex-grow: 1;
    overflow: hidden;
    display: flex;
    flex-direction: column-reverse;
    text-align: right;
    background-color: rgb(53, 53, 53);
    color: white;
    font-size: 8vmin;
    padding: 0 3vmin;
    border-top: 1px solid black;
    border-left: 1px solid black;
    border-right: 1px solid black;
}

.keypad {
    display: grid;
    grid-template: repeat(5, 10vmin) / repeat(4, 10vmin);
    font-size: 5vmin;
}

.key {
    text-align: center;
    vertical-align: center;
    line-height: 10vmin;
    /* background-color: lightgrey; */
    background: padding-box radial-gradient(rgb(194, 194, 194), lightgrey);
    color: black;
    border-top: 1px solid black;
    border-left: 1px solid black;
}

.operator {
    /* background-color: #f98930; */
    background: padding-box radial-gradient(#fd790d, #f19447);
    color: white;
    border-right: 1px solid black;
}

.last_row {
    border-bottom: 1px solid black;
}

.double_column {
    grid-column: span 2;
}

.pencil {
    font-size: 0.7em;
}

@media (min-width: 640px) {
    .calculator {
        width: 40vmin;
        height: 80vmin;
    }
}

@media (max-width: 640px) and (orientation: portrait) {
    body {
        background-color: black;
    }

    .wrapper {
        align-items: flex-end;
    }

    .calculator {
        width: 100vw;
        height: 100vh;
    }

    .display {
        font-size: 15vmin;
        overflow: scroll;
    }

    .keypad {
        grid-template: repeat(5, 25vmin) / repeat(4, 25vmin);
        font-size: 10vmin;
    }

    .key {
        line-height: 25vmin;
    }
}

@media (max-width: 640px) and (orientation: landscape) {
    body {
        background-color: black;
    }

    .calculator {
        flex-direction: row;
        width: 100vw;
        height: 100vh;
    }

    .display {
        font-size: 19vmin;
        overflow: scroll;
    }

    .keypad {
        grid-template: repeat(5, 20vmin) / repeat(4, 20vmin);
        font-size: 10vmin;
    }

    .key {
        line-height: 20vmin;
    }
}
</style>