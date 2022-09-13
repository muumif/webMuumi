<script>
    export let Name, Description, Link, LinkText; // Link as array

</script>

<div class="projectCard">
    <span>
        <p class="projectName">{Name}</p>
        <p class="projectDesc">{Description}</p>
        <a href={Link} target="_blank">{LinkText}</a>
    </span>
</div>

<style>
    .projectCard {
        display: block;
        height: 100%;
        margin: 1rem;
        position: relative;
        width: 90%;
    }

    .projectName {
        font-size: 1.125rem;
        color: #BB86FC;
        text-decoration: underline;
    }

    .projectDesc {
        font-size: 1rem;
        color: #cecece;
    }

    a {
        color: #BB86FC;
        text-decoration: none;
    }

    a:after {
        content: '';
        position: absolute;
        width: 12%;
        transform: scaleX(0);
        height: 3px;
        bottom: 0;
        left: 0;
        background-color: #8a8989;
        transform-origin: bottom right;
        transition: transform 0.25s ease-out;
    }
    a:hover:after {
        transform: scaleX(1);
        transform-origin: bottom left;
    }
</style>