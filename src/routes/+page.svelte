{#snippet topic(itemNum, topicHeader)}
    <div id="topic-{itemNum}" class="topic"> <!--id is number that increases with each one-->
        <div class="outer-content"> <!--content scene while minimized-->
            <div class="num">{itemNum}</div> <!--num should increase with each one-->
            <div class="content-box">
                <div class="topic-head">{topicHeader}</div>
                <div class="topic-desc">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Deserunt qui perferendis magni libero quidem repudiandae illum odit cumque eum nesciunt, iusto minus, at aspernatur, laboriosam esse facere. Delectus, error voluptate?
                </div>
            </div>
        </div>
    </div>
{/snippet}

<div id="container">
    {@render topic(1, "Wow, look at this!")}
    {@render topic(2, "This is cool, too.")}
    {@render topic(3, "And this? Amazing.")}
    {@render topic(4, "Don't forget this!")}
</div>

<style lang="scss">
    @font-face {
        font-family: "num";
        src: url("/InstrumentSerif-Regular.ttf");
    }

    :root {
        --border: ;
    }

    :global(body) {
        margin: 0;
    }

    #container {
        width: 100vw;
        height: 100vh;
        display: flex;

        .topic {
            padding: .625rem;

            .outer-content {
                height: 100%;
                display: flex;
                align-items: flex-end;

                .num {
                    width: 50%;
                    font-size: 150px;
                    font-family: "num";
                }
            }

            border-right: 3px solid var(--border);

            :last-child {
                border: none;
            }
        }
    }
</style>


