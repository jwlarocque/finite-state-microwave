<script>
import LinkSvg from '../../assets/svg/link.svg';

export let id = '';
export let size = 1;
export let centered = false;

$: sharedClasses = `font-mono font-bold text-blue-600 underline ${centered ? 'text-center' : ''}`;
</script>

<div class="relative">
    {#if !!id}
        <div class="flex justify-center items-center absolute inset-y-0 -left-6 md:-left-8 text-blue-600">
            <a href="#{id}">
                <LinkSvg width="16" />
            </a>
        </div>
    {/if}

    {#if size === 1}
        <h1 {...$$props} class="text-6xl {sharedClasses}"><slot/></h1>
    {:else if size === 2}
        <h2 {...$$props} class="text-5xl {sharedClasses}"><slot/></h2>
    {:else if size === 3}
        <h3 {...$$props} class="text-4xl {sharedClasses}"><slot/></h3>
    {:else if size === 4}
        <h4 {...$$props} class="text-3xl {sharedClasses}"><slot/></h4>
    {:else if size === 5}
        <h5 {...$$props} class="text-2xl {sharedClasses}"><slot/></h5>
    {:else if size === 6}
        <h6 {...$$props} class="text-xl {sharedClasses}"><slot/></h6>
    {/if}
</div>