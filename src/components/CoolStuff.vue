<script setup>

</script>

<template>
    <section class="max-w-[1248px] mx-auto flex flex-col lg:flex-row gap-6 px-4 lg:px-0">
        <div class="promo-container">
            <div class="promo-card">
                <h2 class="title">Place your <br> order in seconds</h2>

                <div class="promo-section">
                    <div class="left-block">


                        <div class="buttons">
                            <a href="#" class="store-button"> <img src="../assets/images/image (23).svg"
                                    alt="Google Play Logo"> Download on Google Play</a>
                            <a href="#" class="store-button"><img src="../assets/images/balck apple.png" alt="">
                                Download on
                                App
                                Store</a>

                        </div>

                        <div class="price-tag">
                            <img src="../assets/images/Group 13255.svg" alt="Promo">
                        </div>

                        <div class="promo-code">CDNWEB</div>

                        <p class="promo-text">
                            Get <span class="yellow-text">₦300 off</span> your first order when you use this promo code!
                        </p>
                    </div>

                    <div class="right-block">
                        <img src="../assets/images/drink.svg" class="drink-image" alt="Drink">
                    </div>
                </div>
            </div>


            <div class="promo-card promo-photo">

            </div>
        </div>
    </section>

    <div class="cool-stuff">
        <div class="subscription-motto">

            <div class="text-block">
                <span class="main-text"> <img src="../assets/images/subs-star.png" alt="">Cool stuff only</span>
                <span class="sub-text">Subscribe to our newsletter</span>
            </div>
        </div>
        <div class="subs-package">
            <img src="../assets/images/package.png" alt="">
        </div>

    </div>

</template>


<style scoped>
.liner {
    border: 1px solid white;
}

.promo-code {
    width: 166px;
    height: 58px;
    background-color: #ffc107;

    border: 2px solid black;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
    font-weight: bold;
    font-family: sans-serif;
    color: black;
    font-size: 16px;
}

.promo-code::before {
    content: "";
    display: inline-block;
    width: 18px;
    height: 18px;
    background-color: #0C513F;
    border: 3px solid black;
    border-radius: 50%;
}

.promo-card {
    width: 612px;
    height: 800px;
    background-color: #0C513F;
    padding: 40px 4px 10px 40px;
    border-radius: 20px;
    color: white;
}

.promo-section {
    display: flex;

    align-items: flex-start;
    justify-content: space-between;

}


.left-block {
    max-width: 60%;
    display: flex;
    flex-direction: column;
}


.title {
    font-size: 53px;
    font-weight: bold;
    margin-bottom: 24px;
}

.buttons {
    display: flex;
    flex-direction: column;
    gap: 16px;
    margin-bottom: 32px;
}

.store-button {
    background: white;
    color: black;
    text-decoration: none;
    padding: 12px 20px;
    border-radius: 8px;
    font-weight: 600;
    text-align: center;

}

.store-button img {
    height: 20px;
    max-height: 20px;
    width: auto;
    /* display: block; */
}


.price-tag img {
    height: 145px;
    margin: 60% 0 16px 0;
}

.promo-code {
    width: 166px;
    height: 58px;
    background-color: #ffc107;
    border: 2px solid black;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
    font-weight: bold;
    font-family: sans-serif;
    color: black;
    font-size: 16px;
    margin-bottom: 12px;
}

.promo-code::before {
    content: "";
    display: inline-block;
    width: 18px;
    height: 18px;
    background-color: #0C513F;
    border: 3px solid black;
    border-radius: 50%;
}

.promo-text {
    color: white;
    font-size: 14px;
    max-width: 280px;
}

.yellow-text {
    color: #ffc107;
    font-weight: bold;
}

.right-block .drink-image {

    width: 210px;
    object-fit: contain;
    margin-top: 60%
}


.promo-photo {
    background-image: url(../assets/images/image-promo.png);
    width: 612px;

}

.promo-container {
    max-width: 1248px;
    display: flex;
    justify-content: space-between;
    gap: 24px;
}

.cool-stuff {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: black;
    padding: 24px 32px;
    border-bottom: 1px solid #222;
    color: white;
    font-family: sans-serif;
}


.subscription-motto img {
    height: 30px;
}

.text-block {
    display: flex;
    align-items: baseline;
    /* ✅ aligns texts properly on the same line */
    gap: 8px;
}

.main-text {
    font-size: 48px;
    font-weight: bold;
    color: white;
}

.sub-text {
    font-size: 16px;
    color: #FFEDB3;
}
</style>
