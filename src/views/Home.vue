<template>
    <span>
        <home-hi></home-hi>
        <home-details></home-details>
    </span>
</template>

<script>
import HomeHi from '@/components/HomeHi';
import HomeDetails from '@/components/HomeDetails';

export default {
    name: 'home',
    components: {
        HomeHi,
        HomeDetails
    }
};
</script>
