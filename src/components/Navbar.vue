<template>
    <nav :class="[`navbar-${theme}`, `bg-${theme}`, 'navbar', 'navbar-expand-lg']">
        <!-- :class="{'navbar-light bg-light':!useDarkNavBar,'navbar-dark bg-dark':useDarkNavBar}" -->
        <div class="container-fluid">
            <a href="#" class="navbar-brand">My Vue</a>
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li class="nav-item" v-for="(page, index) in pages" :key="index">
                    <navbar-link :page="page" :isActive="activePage === index">
                    </navbar-link>
                </li>
            </ul>
            <form class="d-flex">
                <button class="btn btn-primary" @click.prevent="changeTheme()">
                    Toggle Navbar</button>
            </form>
        </div>
    </nav>
</template>

<script>
export default {
    props: ['pages', 'activePage', 'navLinkClick'],
    data() {
        return {
            theme: 'light'
        }
    }, methods: {
        changeTheme() {
            let theme = 'light';
            if (this.theme == 'light') {
                theme = 'dark';
            }
            this.theme = theme;
        }
    }
}
</script>