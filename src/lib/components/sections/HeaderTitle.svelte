<script>
    export let title;
    export let subtitle;
</script>

<div class="mt-[2rem] md:mt-[15rem] md:my-28">
    <div class="text-center" data-aos="fade-up">
        <h1 class="text-4xl">{title}</h1>
        {#if subtitle}
            <p>{subtitle}</p>
        {/if}
    </div>
</div>
