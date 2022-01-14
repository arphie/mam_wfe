<template>
	<div class="pecs-custom-main">
        <div class="pecs-custom-inner">

            show pecs pages

            <div class="pecs-icon-list">
                <div class="pil-item">
                    <div class="dx-pecs-icon" :style="{backgroundImage: 'url('+ require('/assets/images/icons/places.png')+')'}">&nbsp;</div>
                    <div class="dx-pecs-name">Places</div>
                </div>
                <div class="pil-item">
                    <div class="dx-pecs-icon" :style="{backgroundImage: 'url('+ require('/assets/images/icons/food.jpg')+')'}">&nbsp;</div>
                    <div class="dx-pecs-name">Food</div>
                </div>
            </div>
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
    .pecs-icon-list .pil-item {
        display: inline-block;
        width: 13%;
        margin-right: 2%;
    }
</style>