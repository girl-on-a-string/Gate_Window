{#snippet topic(itemNum, topicPageLink)}
    <div id="topic-{itemNum}" class="topic"> <!--id is number that increases with each one-->
        <div class="inner-content">
            <iframe title="topic {itemNum}" src="{topicPageLink}" frameborder="0"></iframe>
        </div> <!--iframe location-->
        <div class="outer-content" on:mouseenter={() => {hoverAnim(itemNum)}} role="navigation"> <!--content scene while minimized-->
            <div class="num">Topic {itemNum}</div> <!--num should increase with each one-->
        </div>
    </div>
{/snippet}

<div id="container">
    {@render topic(1, "")}
    {@render topic(2, "")}
    {@render topic(3, "")}
    {@render topic(4, "")}
</div>

<script>
    function hoverAnim (item) {
        let target = document.getElementById(`topic-${item}`);
        console.log(target);
    }
</script>

<style lang="scss">
    @font-face {
        font-family: "num";
        src: url("/InstrumentSerif-Regular.ttf");
    }

    @font-face {
        font-family: "topic-head";
        src: url("/Dangrek-Regular.ttf");
    }

    :root {
        --secondary: #5F6F52;
        --main-bg: #F8F2DE;
    }

    :global(body) {
        margin: 0;
        overflow: hidden;
    }

    #container {
        width: 100vw;
        height: 100vh;
        display: grid;
        grid-template-columns: repeat(4, 1fr);

        color: var(--secondary);

        .topic {
            background-color: var(--main-bg);

            .inner-content {
                position: absolute;
                width: calc(100vw / 4);
                height: 100%;

                iframe {
                    width: 100%;
                    height: 100%;
                }
            }

            .outer-content {
                position: relative;
                height: 100%;
                display: flex;
                align-items: flex-end;
                animation-name: hover;
                animation-duration: 500ms;
                animation-play-state: paused;

                .num {
                    margin-left: .625rem;
                    font-size: 9.375rem;
                    font-family: "num";
                }
            }

            border-right: 3px solid var(--secondary);

            :last-child {
                border: none;
            }
        }

        @keyframes hover {
            from {
                height: 100%;
            }

            to {
                height: 0%;
            }
        }
    }
</style>


