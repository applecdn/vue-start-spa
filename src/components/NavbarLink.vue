<template>
    <a 
        class="nav-link" 
        :class="{ active: activePage == index }" 
        aria-current="page" 
        :href="page.link.url"
        :title="`This link goes to the ${page.link.text} page`" @click.preve="navLinkClick(index)">
        {{ page.link.text }}</a>
</template>

<script>
export default {
    props: ['page', 'isActive'],
    computed: {
        activeClasses() {
            return {
                active: this.isActive,
                emphasize: this.isActive
            };
        }
    }
}
</script>