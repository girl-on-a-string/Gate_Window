{#snippet topic(itemNum, topicPageLink)}
    <div id="topic-{itemNum}" class="topic"> <!--id is number that increases with each one-->
        <div class="inner-content">
            <iframe title="topic {itemNum}" src="{topicPageLink}" frameborder="0"></iframe>
        </div> <!--iframe location-->
        <div class="outer-content"> <!--content scene while minimized-->
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
            padding: .625rem;

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

                .num {
                    margin-right: .625rem;
                    font-size: 9.375rem;
                    font-family: "num";
                }

                .content-box {
                    .topic-head {
                        font-family: "topic-head";
                        font-size: 45px;
                    }

                    .topic-desc {
                        font-family: Arial, Helvetica, sans-serif;
                        font-size: 20px;
                    }
                }
            }

            border-right: 3px solid var(--secondary);

            :last-child {
                border: none;
            }
        }
    }
</style>


