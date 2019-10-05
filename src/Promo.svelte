
<script>
    import Title from "./Title.svelte";
    import Text from "./Text.svelte";
    import Button from "./Button.svelte";
    import Image from "./Image.svelte";

    export let title = "";
    export let text = "";
    export let buttonTitle;
    export let buttonHref;
    export let backgroundImageSrc;
    export let backgroundColor;

</script>

<style>
    .promo {
        position: relative;
        overflow: hidden;
    }

    .background {
        position: absolute;
    }

    .left {
        top: 0;
        left: 0;
    }

    .right {
        top: 0;
        right: 0;
    }

    .promo :global(.title),
    .promo :global(.text) {
        color: #fff;
    }

    .promo :global(.title.large) {
        font-weight: 400;
    }

    .promo :global(.text) {
        font-size: 16px;
        text-align: center;
    }

    .wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .action {
        margin-top: 30px;
    }

    @media (max-width: 767px) {
        .promo {
            padding-top: 55px;
            padding-bottom: 40px;
        }

        .background {
            display: none;
        }

        .promo :global(.title.large) {
            font-size: 26px;
            line-height: 32px;
        }

        .promo :global(.text) {
            margin-top: 15px;
            line-height: 24px;
        }
    }

    @media (min-width: 768px) {
        .promo {
            padding-top: 75px;
            padding-bottom: 55px;
        }

        .promo :global(.text) {
            line-height: 32px;
        }
    }
</style>

<section class="promo" style="background-color: {backgroundColor}">
    <div class="background left">
        <Image src={backgroundImageSrc} />
    </div>
    <div class="background right">
        <Image src={backgroundImageSrc} />
    </div>
    <div class="container">
        <div class="wrapper">
            <Title size="large" element="h3">{title}</Title>
            <Text content={text} />
            <div class="action">
                <Button link={buttonHref} theme="solid">{buttonTitle}</Button>
            </div>
        </div>
    </div>
</section>
