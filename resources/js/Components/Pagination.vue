<template>
    <nav>
        <ul :class="`pagination justify-content-${align} mb-0`">
            <li 
                v-for="(link, index) in links" 
                :key="index" 
                :class="[
                    'page-item', 
                    link.url === null ? 'disabled' : '',
                    link.active ? 'active' : ''
                ]">
                <Link 
                    class="page-link" 
                    :href="link.url === null ? '#' : link.url">
                    {{ link.label }} <!-- Menggunakan interpolasi untuk menampilkan label -->
                </Link>
            </li>
        </ul>
    </nav>
</template>

<script>
import { Link } from '@inertiajs/inertia-vue3';

export default {
    props: {
        links: {
            type: Array,
            required: true
        },
        align: {
            type: String,
            default: 'center' // Menetapkan nilai default untuk alignment
        }
    },
    components: {
        Link,
    },
}
</script>

<style scoped>
/* Tambahkan gaya khusus untuk pagination di sini */
</style>