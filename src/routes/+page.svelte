{#snippet topic(itemNum, topicHeader, topicDesc)}
    <div id="topic-{itemNum}" class="topic"> <!--id is number that increases with each one-->
        <div class="outer-content"> <!--content scene while minimized-->
            <div class="num">{itemNum}</div> <!--num should increase with each one-->
            <div class="content-box">
                <div class="topic-head">{topicHeader}</div>
                <div class="topic-desc">
                    {topicDesc}
                </div>
            </div>
        </div>
    </div>
{/snippet}

<div id="container">
    {@render topic(1, "Wow, look at this!", "This is silly filler text, I don't know what to write here. What'd you have for dinner?")}
    {@render topic(2, "This is cool, too.", "More filler text. I had ribs. They were yummy. More filler text, blah blah blah!")}
    {@render topic(3, "And this? Amazing.", "This website is really awesome, really cool. \'Lorem Ipsum\' or whatever. Yada yada.")}
    {@render topic(4, "Don't forget this!", "Last box. Check out what's inside? Spoiler alert: nothing special.")}
</div>

<style lang="scss">
    @font-face {
        font-family: "num";
        src: url("/InstrumentSerif-Regular.ttf");
    }

    :root {
        --border: ;
        --main-bg: #ECDCBF;
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

        .topic {
            background-color: var(--main-bg);
            padding: .625rem;

            .outer-content {
                height: 100%;
                display: flex;
                align-items: flex-end;

                .num {
                    width: 30%;
                    height: 9.688rem;
                    margin-right: .625rem;
                    font-size: 9.375rem;
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


