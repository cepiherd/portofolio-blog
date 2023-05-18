<script>
    import { page } from "$app/stores";

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

    let filterBlogResult = findBlog($page.params.slug);

    function findBlog(keyword) {
        return Listblogs.filter((item) => {
            return item.slug
                .toLocaleLowerCase()
                .includes(keyword.toLocaleLowerCase());
        });
    }

    let blog = filterBlogResult[0];
</script>

<img src={blog.image} alt="" class="w-full rounded-2xl" />
<h1 class="text-2xl font-semibold my-4">{blog.title}</h1>
<p>
    {blog.description}
</p>

<button class="bg-primary text-white px-8 py-2 shadow-md rounded my-2">
    Share
</button>
