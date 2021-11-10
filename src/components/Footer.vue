a
<template>
    <footer>
        <div>&copy; 2022 <a href="#">Multi Cloud Ai</a> & <a href="#">VB Easy</a></div>
        <div class="links">
            <a v-for="(link, i) of links" :key="i" :href="link.url">
                {{ link.title }}
            </a>
        </div>
    </footer>
</template>
<script>
export default {
    name: 'Footer',
    data() {
        return {
            links: [
                {
                    title: 'Multi Cloud Ai',
                    url: '',
                },
                {
                    title: 'VB Easy',
                    url: '',
                },
                {
                    title: 'About Us',
                    url: '',
                },
                {
                    title: 'Blog',
                    url: '',
                },
                {
                    title: 'Privacy',
                    url: '',
                },
            ],
        };
    },
};
</script>
