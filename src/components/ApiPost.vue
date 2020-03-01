<template>
    <div class="apiPost">
        <h2>{{ title }}</h2>
        <p>{{ body }}</p>
    </div>
</template>
<script>
    export default {
        name: 'ApiPost',
        props: {
            title: String,
            body: String,
        },
    }
</script>