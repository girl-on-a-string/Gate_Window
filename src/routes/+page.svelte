{#snippet topic(itemNum, topicHeader, topicDesc, topicPageLink)}
    <div id="topic-{itemNum}" class="topic"> <!--id is number that increases with each one-->
        <div class="inner-content">
            <iframe title="topic {itemNum}" src="{topicPageLink}" frameborder="0"></iframe>
        </div> <!--iframe location-->
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
    {@render topic(1, "Wow, look at this!", "Lorem ipsum odor amet, consectetuer adipiscing elit. Natoque volutpat placerat dictum ante ut fames. Suspendisse interdum consectetur nascetur sociosqu tortor nunc enim.", "")}
    {@render topic(2, "This is cool, too.", "Lorem ipsum odor amet, consectetuer adipiscing elit. Montes a lacinia odio nibh class aenean natoque natoque. Pellentesque tortor massa enim at fames in imperdiet neque.", "")}
    {@render topic(3, "And this? Amazing.", "Lorem ipsum odor amet, consectetuer adipiscing elit. Dictum ut suscipit class platea scelerisque adipiscing pretium. Potenti ex odio dictum consequat odio. Luctus leo netus; quis eros nisi condimentum.", "")}
    {@render topic(4, "Don't forget this!", "Lorem ipsum odor amet, consectetuer adipiscing elit. Interdum sodales ultrices dignissim dis nam. Rhoncus condimentum tempus nullam ornare, semper metus nam.", "")}
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
            }

            .outer-content {
                position: relative;
                height: 100%;
                display: flex;
                align-items: flex-end;

                .num {
                    width: 4.688rem;
                    height: 9.688rem;
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


