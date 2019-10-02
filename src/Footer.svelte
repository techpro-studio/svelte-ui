<script>
    import Image from './Image.svelte';

    export let phone;
    export let email;
    export let socialNetworks;
    export let copyright;
    export let description;
    export let logoSrc;

</script>

<style>
    .footer {
        background-color: #1e212a;
    }

    .top {
        padding-top: 100px;
        padding-bottom: 60px;
        color: #fff;
        font-size: 14px;
        line-height: 20px;
    }

    .bottom {
        border-top: 1px solid #535353;
    }

    .wrapper {
        display: flex;
        justify-content: space-between;
    }

    .column {
        width: calc(100% / 3);
        max-width: 240px;
    }

    .column-content {
        margin-top: 20px;
    }

    .title {
        font-weight: 600;
        text-transform: uppercase;
    }

    .list {
        display: flex;
        align-items: center;
    }

    .link-icon:not(:last-child) {
        margin-right: 32px;
    }

    .contacts a {
        text-decoration: none;
    }

    .row:not(:last-child) {
        margin-bottom: 15px;
    }

    .copyright {
        padding: 14px 0;
        color: #c4c4c4;
        font-size: 12px;
        line-height: 18px;
        text-align: center;
    }

    @media (max-width: 767px) {
        .wrapper {
            flex-direction: column;
            align-items: center;
        }

        .top {
            padding-top: 42px;
            padding-bottom: 42px;
        }

        .column {
            display: flex;
            flex-direction: column;
            align-items: center;
            width: 100%;
        }

        .column:not(:first-child) {
            margin-top: 60px;
        }

        .column-content {
            text-align: center;
        }
    }
</style>

<footer class="footer">
    <div class="top">
        <div class="container">
            <div class="wrapper">
                <div class="column">
                    <div class="column-header">
                        <a href="..">
                            <Image src={logoSrc} />
                        </a>
                    </div>
                    <div class="column-content">{description}</div>
                </div>
                <div class="column order-mobile-1">
                    <div class="column-header hide-for__mobile">
                        <div class="title">Social networks</div>
                    </div>
                    <div class="column-content">
                        <div class="list">
                            {#each socialNetworks as social}
                                <a href={social.href} class="link-icon" target="_blank">
                                    <img src={social.icon} alt="Icon" />
                                </a>
                            {/each}
                        </div>
                    </div>
                </div>
                <div class="column">
                    <div class="column-header">
                        <div class="title">Contact us</div>
                    </div>
                    <div class="column-content">
                        <div class="contacts">
                            <div class="row">
                                <span>UA:</span>
                                <a href="callto:{phone}">{phone}</a>
                            </div>
                            <div class="row">
                                <a href="mailto:{email}">{email}</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="bottom">
        <div class="container">
            <div class="copyright">{copyright}</div>
        </div>
    </div>
</footer>
