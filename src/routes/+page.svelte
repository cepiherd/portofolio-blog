<script>
    import src from "$lib/assets/avatar.jpeg";
    import Card from "$lib/assets/components/Card/Card.svelte";
    let keyword = "";
    let Listblogs = [
        {
            title: "What is Svelte kit",
            slug: "what-is-sveltep-kit",
            description:
                "Svelte Kit is a powerful framework for building webapplications with exceptional efficiency. It combinesthe best features of Svelte, a popular JavaScriptframework known for its lightweight and reactive approach, with a comprehensive toolkit for streamlineddevelopment",
            image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSLK-lYSsU_QU2UBVjx-dZHajBuXbP3xsmqsg&usqp=CAU",
        },
        {
            title: "For What Svelte kit exists ?",
            slug: "for-what-svelte-kit-exists",
            description:
                "Svelte Kit is a powerful framework for building webapplications with exceptional efficiency. It combinesthe best features of Svelte, a popular JavaScriptframework known for its lightweight and reactive approach, with a comprehensive toolkit for streamlineddevelopment",
            image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQZ_ybAZmR4LhHvL_151zp997BBuRbTPOOmOA&usqp=CAU",
        },
        {
            title: "ini apa ?",
            slug: "ini-apa",
            description:
                "Svelte Kit is a powerful framework for building webapplications with exceptional efficiency. It combinesthe best features of Svelte, a popular JavaScriptframework known for its lightweight and reactive approach, with a comprehensive toolkit for streamlineddevelopment",
            image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQZ_ybAZmR4LhHvL_151zp997BBuRbTPOOmOA&usqp=CAU",
        },
        {
            title: "apa ini sih ?",
            slug: "apa-ini-sih",
            description:
                "Svelte Kit is a powerful framework for building webapplications with exceptional efficiency. It combinesthe best features of Svelte, a popular JavaScriptframework known for its lightweight and reactive approach, with a comprehensive toolkit for streamlineddevelopment",
            image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQZ_ybAZmR4LhHvL_151zp997BBuRbTPOOmOA&usqp=CAU",
        },
    ];
    let filterBlogResult = Listblogs;
    function findBlog(keyword) {
        filterBlogResult = Listblogs.filter((item) => {
            return item.title
                .toLocaleLowerCase()
                .includes(keyword.toLocaleLowerCase());
        });
    }

    $: findBlog(keyword);
</script>

<section id="identity">
    <div class="flex gap-5 border rounded-lg p-3 shadow items-center">
        <div>
            <img {src} alt="" class="rounded-full" />
        </div>
        <div id="tentang-saya" class="text-sm">
            <p class="font-bold">Cepi Herdiansyah</p>
            As a Frontend Developer, I possess expertise in creating engaging and
            responsive user interfaces. I have a strong understanding of modern web
            technologies and the ability to translate design concepts into functional
            code.
        </div>
    </div>
</section>

<input
    type="text"
    bind:value={keyword}
    class="border rounded-md w-full py-3 px-2 mt-2"
    placeholder="Search article"
/>
<section id="blog" class="mt-10">
    <div class="flex gap-3 flex-wrap">
        {#each filterBlogResult as item}
            <a href={"blog/" + item.slug}>
                <Card
                    title={item.title}
                    image={item.image}
                    description={item.description}
                />
            </a>
        {/each}
    </div>
</section>
