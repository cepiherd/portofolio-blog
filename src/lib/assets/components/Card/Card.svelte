<script>
    export let image, title, description;
</script>

<div id="card" class="max-w-[320px] w-full shadow rounded-2xl">
    <figure>
        <img src={image} alt="" class="w-full rounded-t-2xl h-full" />
    </figure>

    <div class="px-3 pb-3">
        <h1 class="font-semibold py-2 text-lg">
            {title}
        </h1>
        <p class="line-clamp-2">
            {description}
        </p>
    </div>
</div>
