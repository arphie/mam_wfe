<template>
	<div class="page-title">
        <div class="page-title-inner">
            <h2 class="ptitle">{{title}}</h2>
            <div class="sub-title">{{subtitle}}</div>
        </div>
    </div>
</template>

<script>
export default {
    // name: 'Dashboard'
    props: [
        'title',
        'subtitle'
    ],
}
</script>

<style scoped>
    h2.ptitle {
        font-size: 21px;
        line-height: 1em;
        font-weight: 600;
        margin-bottom: 10px;
    }

    .sub-title {
        font-size: 14px;
        line-height: 1em;
    }
</style>