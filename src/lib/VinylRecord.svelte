<script lang="ts">
    let active = false;
    export let cover: string;
    export let disc: string;
</script>

<div
    class={`vinyl-record ${active ? "vinyl-record--active" : ""}`}
    on:mouseenter={() => {
        active = true;
    }}
>
    <div class="vinyl-record__sleeve" style="background-image: url({cover})" />
    <div class="vinyl-record__disc" style="background-image: url({disc})" />
</div>

<style lang="scss">
    .vinyl-record {
        position: relative;
        width: 512px;
        height: 256px;
        margin: 10px;
        cursor: pointer;

        &__sleeve {
            position: absolute;
            width: 256px;
            height: 256px;
            background-size: contain;
            z-index: 1;
        }
        &__disc {
            position: absolute;
            background-size: contain;
            width: 256px;
            height: 256px;
            left: 0;
            border-radius: 50%;
            z-index: 0;
        }
        &:hover {
            .vinyl-record__disc {
                animation: record-slide-out 0.25s linear forwards;
            }
        }
        &--active {
            &:not(:hover) {
                .vinyl-record__disc {
                    animation: record-slide-in 0.25s linear forwards;
                }
            }
        }
    }

    @keyframes record-slide-out {
        from {
            left: 0;
        }
        to {
            left: 256px;
        }
    }
    @keyframes record-slide-in {
        from {
            left: 256px;
        }
        to {
            left: 0;
        }
    }
</style>
