<script setup lang="ts">
import { Link } from '@inertiajs/vue3';
import { 
LayoutGrid,
  Users,
  Package,
  RefreshCcw,
  ShoppingCart

     } from 'lucide-vue-next';

import NavFooter from '@/components/NavFooter.vue';
import NavMain from '@/components/NavMain.vue';
import NavMainTwo from '@/components/NavMainTwo.vue';
import NavUser from '@/components/NavUser.vue';
import {
    Sidebar,
    SidebarContent,
    SidebarFooter,
    SidebarHeader,
    SidebarMenu,
    SidebarMenuButton,
    SidebarMenuItem,
} from '@/components/ui/sidebar';
import { dashboard } from '@/routes';
import { type NavItem } from '@/types';

import AppLogo from './AppLogo.vue';

const mainNavItems: NavItem[] = [
    {
        title: 'Панель управления',
        href: dashboard(),
        icon: LayoutGrid,
    },
     {
        title: 'Товары',
        // href: dashboard(),
        icon: Package,
    },
     {
        title: 'Пользователи',
        // href: dashboard(),
        icon: Users,
    },
     {
        title: 'Заказы',
        // href: dashboard(),
        icon: ShoppingCart,
    },
];

const mainNavItemsTwo: NavItemTwo[] = [
    {
        title: 'Синхронизация',
        // href: 
        icon: RefreshCcw,
    },
];

</script>

<template>
    <Sidebar collapsible="icon" variant="inset">
        <SidebarHeader>
            <SidebarMenu>
                <SidebarMenuItem>
                    <SidebarMenuButton size="lg" as-child>
                        <Link :href="dashboard()">
                            <AppLogo />
                        </Link>
                    </SidebarMenuButton>
                </SidebarMenuItem>
            </SidebarMenu>
        </SidebarHeader>

        <SidebarContent>
            <NavMain :items="mainNavItems" />
        </SidebarContent>

        <SidebarContent>
            <NavMainTwo :items="mainNavItemsTwo" />
        </SidebarContent>

        <SidebarFooter>
            <NavUser />
        </SidebarFooter>

    </Sidebar>
    <slot />
</template>
