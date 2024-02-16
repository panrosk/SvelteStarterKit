<script lang="ts">
  export let title:string;
  export let description:string;
  export let keywords:string;
  export let author:string = "Oscar Fuentes";
  export let favicon:string = "/favicon.ico";
  export let canonical:string;
  export let schema: object | null = null;
  export let type: string = "website";
  export let image: string = "/logo.png";
  export let twitter: string|null = null;




</script>

<svelte:head>
  <title>{title}</title>i
  <meta charset="UTF-8">
  <meta name="description" content={description} />
  <meta name="keywords" content={keywords} />
  <meta name="author" content={author} />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="robots" content="index, follow">
  <meta name="googlebot" content="index, follow">
  <meta name="bingbot" content="index, follow">
  <meta name="og:title" content={title} />
  <meta name="og:description" content={description} />
  <meta name="og:type" content={type} />
  <meta name="og:url" content={canonical} />
  <meta name="og:image" content={image} />
  <meta name="og:site_name" content={title} />
  {#if twitter!=null}
    <meta name="twitter:card" content="summary_large_image" />
    <meta name="twitter:site" content={twitter} />
    <meta name="twitter:creator" content={twitter} />
    <meta name="twitter:image" content={image} />
  {/if}
  <link rel="icon" href={favicon} />
  {#if schema!=null}
    <script type="application/ld+json">
      {JSON.stringify(schema)}
    </script>
  {/if}


</svelte:head>
