<script></script>

<section id="Hero">
    <div class="container">
        <div class="text-content">
            <h1>Art is the Journey of a Free Soul</h1>
            <div class="content-description">
                <div class="header">
                    <div class="title">
                        <span>RE.ART</span> Greetings
                    </div>
                    <div class="title">
                        <span>-EST</span> 2023
                    </div>
                </div>
                <div class="body">
                    In the prespective of the history of art, artistic works have existed for almost as long as humankind: from early pre-historic art to contemporary art; however, some theorists think that the typical concept of "artistic works".
                </div>
            </div>
        </div>
    </div>
    <div class="hero-banner">
        <img src="/img/banner-1.jpg" alt="banner">
    </div>
</section>

<style lang="scss">
    #Hero {
        position: relative;
        padding-top: 60px;

        .text-content {
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            align-items: center;
            gap: 50px;

            h1 {
                font-size: 64px;
                color: $text-black;
                text-decoration: underline;
                font-weight: 500;
                line-height: 88px;
                width: 100%;
            }

            .content-description {
                display: flex;
                flex-direction: column;
                align-items: center;

                .header {
                    display: flex;
                    flex-direction: row;
                    justify-content: space-between;
                    align-items: center;
                    width: 100%;

                    .title {
                        font-size: 20px;
                        color: $text-black;

                        span {
                            font-size: 20px;
                            color: $text-black;
                            font-weight: 600;
                        }
                    }
                }

                .body {
                    text-align: justify;
                    margin-top: 40px;
                }
            }
        }

        .hero-banner {
            position: absolute;
            right: 0;
            width: 85vw;
            margin-top: 70px;
            
            img {
                width: 100%;
                height: 500px;
                object-fit: cover;
                box-shadow: 0 4px 16px 0 rgba($color: #000000, $alpha: 0.14);
            }
        }
    }
</style>