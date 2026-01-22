<script setup lang="ts">
import { Head } from '@inertiajs/vue3';

import AppLayout from '@/layouts/AppLayout.vue';
import { dashboard } from '@/routes';
import { type BreadcrumbItem } from '@/types';



const breadcrumbs: BreadcrumbItem[] = [
    {
        title: 'Dashboard',
        href: dashboard().url,
    },
];
</script>

<template>


    <Head title="Панель управления" />

    <AppLayout :breadcrumbs="breadcrumbs">
        <div>
       
        </div>
    </AppLayout>


</template>
