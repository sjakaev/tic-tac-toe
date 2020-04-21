<template>
    <div class="tic-tac-toe">
        <ul class="tic-tac-toe__cell-list">
            <li
                v-for="i in 9"
                :key="i"
                class="tic-tac-toe__cell"
            >
                <button
                    class="tic-tac-toe__button"
                    :class="getCrossOrZero()"
                    @click="makeMove()"
                >
                </button>
            </li>
        </ul>
    </div>
</template>
<script>


export default {

    data : () => ( {
        isCross : true,
    } ),
    computed : {

    },
    methods : {
        makeMove() {
        },
        getCrossOrZero() {
        },
    },
};
</script>

<style lang="scss">
.tic-tac-toe {
    margin-top: 50px;

    &__cell-list {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        box-sizing: border-box;
        width: 600px;
        height: 600px;
        padding: 0;
        margin: 0 auto;
        list-style: none;
    }

    &__cell {
        display: block;
        width: 200px;
        height: 200px;
    }

    &__button {
        position: relative;
        box-sizing: content-box;
        width: 100%;
        height: 100%;
        border: none;
        background-color: white;
        border: 2px solid black;
        cursor: pointer;

        &:hover {
            background-color: #EFF8F3;
        }

        &:active {
            background-color: #E9F2ED;
        }

        &_type {
            &_zero {
                &:after {
                    position: absolute;
                    content: '';
                    top: 30%;
                    left: 29%;
                    width: 60px;
                    height: 60px;
                    background-color: transparent;
                    border-radius: 50%;
                    border: 10px solid green;
                }
            }

            &_cross {
                &:before {
                    position: absolute;
                    content: '';
                    top: 32%;
                    left: 45%;
                    width: 10px;
                    height: 60px;
                    background-color: green;
                }

                &:after {
                    position: absolute;
                    content: '';
                    top: 45%;
                    left: 33%;
                    width: 60px;
                    height: 10px;
                    background-color: green;
                }
            }
        }
    }
}
</style>
