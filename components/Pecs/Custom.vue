<template>
	<div class="pecs-custom-main">
        <div class="pecs-custom-inner">
			<div class="pecs-icon-list" v-for="(item, key) in boards" :key="key">
				<h4>{{item.label}}</h4>
				<div class="pecs-icon-list">
					<div class="pil-item">
						<div class="dx-pecs-icon add-pecs-icon">+</div>
						<div class="dx-pecs-name">&nbsp;</div>
					</div>
					<div class="pil-item" v-for="(ocitem, ockey) in item.item">
						<div class="dx-pecs-icon" :style="{backgroundImage: 'url('+ require('/assets/images/icons/places.png')+')'}">&nbsp;</div>
						<div class="dx-pecs-name">{{ocitem.name}}</div>
					</div>
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
	data() {
		return {
			boards: [
				{
					label: 'places',
					item: [
						{ name: 'mall', icon: 'icon'},
						{ name: 'church', icon: 'icon'},
						{ name: 'school', icon: 'icon'},
						{ name: 'home', icon: 'icon'},
						{ name: 'kitchen', icon: 'icon'},
						{ name: 'sala', icon: 'icon'},
						{ name: 'bedroom', icon: 'icon'},
						{ name: 'comfort room', icon: 'icon'},
						{ name: 'market', icon: 'icon'},
					]
				},
				{
					label: 'action',
					item: [
						{ name: 'eat', icon: 'icon'},
						{ name: 'sleep', icon: 'icon'},
						{ name: 'go', icon: 'icon'},
						{ name: 'brush', icon: 'icon'},
						{ name: 'bath', icon: 'icon'},
					]
				},
				{
					label: 'person',
					item: [
						{ name: 'I', icon: 'icon'},
						{ name: 'mother', icon: 'icon'},
						{ name: 'father', icon: 'icon'},
						{ name: 'brother 1', icon: 'icon'},
						{ name: 'brother 2', icon: 'icon'},
					]
				}
			]
		}
	}
}
</script>

<style scoped>
	.pecs-icon-list  {
		margin-bottom: 30px;
	}

    .pecs-icon-list .pil-item {
        display: inline-block;
        width: 10%;
        margin-right: 2%;
		margin-bottom: 15px;
		cursor: pointer;
    }

	.pecs-icon-list .pil-item  .dx-pecs-icon {
		height: 100px;
	    width: 100px;
	    margin: 0 auto;
	    background-size: cover;
	    background-position: center center;
	    border-radius: 11px;
	    box-shadow: 0 0 12px #ccc;

	}

	.pecs-icon-list .pil-item .dx-pecs-name {
		text-align: center;
	    font-weight: bold;
	    text-transform: capitalize;
	    font-size: 14px;
	    margin-top: 10px;
	}

	.pecs-icon-list h4 {
	    font-size: 18px;
	    text-transform: capitalize;
	    margin-bottom: 30px;
	    border-bottom: 1px solid #cccccc90;
	    line-height: 1em;
	    padding-bottom: 10px;
	}

	.add-pecs-icon {
	    font-size: 65px;
	    text-align: center;
	    line-height: 1em;
	    font-weight: bold;
	    padding-top: 13px;
	    display: block;
	}



</style>
