<!--
  # Component
  Title
 -->

<script>
    export let element;
    export let fontWeightMedium = false;
    export let size;
    export let align;
    export let color;

    function buildCssClass(size, align, color, fontWeightMedium) {
        let value = `title ${size}`;
        if (fontWeightMedium) {
            value += " fw-medium"
        }
        if (color) {
            value += ` ${color}`
        }
        if (align) {
            value += ` ${align}`
        }
        return value;
    }

    $: cssClass = buildCssClass(size, align, color, fontWeightMedium);

</script>

<style>
    .title {
        margin: 0;
        font-size: 28px;
        font-weight: 600;
        text-align: center;
    }

    .medium {
        font-size: 32px;
        font-weight: 700;
        line-height: 48px;
    }

    .large {
        font-size: 36px;
        font-weight: 700;
        line-height: 54px;
    }

    .extra-large {
        font-size: 48px;
        font-weight: 700;
        line-height: 48px;
    }

    .fw-medium {
        font-weight: 600;
    }

    .left {
        text-align: left;
    }

    .secondary {
        color: #bebebe;
    }

    .home--service-card {
        font-size: 24px;
        font-weight: 400;
        line-height: 36px;
    }

    @media (max-width: 767px) {
        .title,
        .title.large {
            font-size: 24px;
            line-height: 48px;
        }

        .title.extra-large {
            font-size: 26px;
            text-align: center;
        }

        .home--service-card {
            font-size: 16px;
            line-height: 24px;
        }
    }
</style>

{#if element === 'h1'}
    <h1 class={cssClass}>
        <slot></slot>
    </h1>
{:else if element === 'h2'}
    <h2 class={cssClass}>
        <slot></slot>
    </h2>
{:else if element === 'h3'}
    <h3 class={cssClass}>
        <slot></slot>
    </h3>
{:else if element === 'h4'}
    <h4 class={cssClass}>
        <slot></slot>
    </h4>
{:else if element === 'h5'}
    <h5 class={cssClass}>
        <slot></slot>
    </h5>
{:else if element === 'h6'}
    <h6 class={cssClass}>
        <slot></slot>
    </h6>
{/if}

