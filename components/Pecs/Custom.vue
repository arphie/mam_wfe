<template>
	<div class="pecs-custom-main">
        <div class="pecs-custom-inner">
			<div class="pecs-icon-list" v-for="(item, key) in boards" :key="key">
				<h4>{{item.label}}</h4>
				<div class="pecs-icon-list">
					<div class="pil-item">
						<div class="dx-pecs-icon add-pecs-icon" v-on:click="toogleAddNewIcon()">+</div>
						<div class="dx-pecs-name">&nbsp;</div>
					</div>
					<div class="pil-item" v-for="(ocitem, ockey) in item.item" :key="ockey" v-on:click="toggleSelectedItem(item.label, ocitem.name)">
						<div class="dx-pecs-icon" :style="{backgroundImage: 'url('+ require('/assets/images/icons/places.png')+')'}">&nbsp;</div>
						<div class="dx-pecs-name">{{ocitem.name}}</div>
					</div>
					<v-dialog v-model="showAddPecsModal" width="500" transition="dialog-bottom-transition">
						<div class="pecs-modal-item add-pecs-modal">
							<h4>Add New Tile</h4>
							<div class="d-subtitle">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse vel ligula eu tortor iaculis congue nec eu mi. Aliquam suscipit est vitae scelerisque posuere.</div>
							<div class="add-pecs-item">
								<label for="">Category</label>
								<select name="" id="">
									<option value="">Category 1</option>
									<option value="">Category 2</option>
									<option value="">Category 3</option>
									<option value="">Category 4</option>
									<option value="">Category 5</option>
								</select>
							</div>
							<div class="add-pecs-item">
								<label for="">Items</label>
								<select name="" id="">
									<option value="">Item 1</option>
									<option value="">Item 2</option>
									<option value="">Item 3</option>
									<option value="">Item 4</option>
									<option value="">Item 5</option>
								</select>
							</div>
							<div class="add-pecs-buttons">
								<button class="add-tile-cancel" v-on:click="toogleCloseAddIcon()">Cancel</button>
								<button class="add-tile-save">Save tile</button>
							</div>
						</div>
					</v-dialog>
				</div>
				
				<div class="pil-item-modal">
					<v-dialog v-model="showPecsItemModal" width="900" transition="dialog-bottom-transition">
						<div class="pecs-modal-item">
							<div class="pecs-modal-item-inner">
								<div class="pmi-left-info">
									<div class="base-image">
										<div class="base-left-part">
											<div class="pmi-main-image">
												<img src="@/assets/images/icons/places.png" alt="">
											</div>
										</div>
										<div class="base-right-part">
											<h2>{{selectedItem.item}}</h2>
											<div class="pmi-item-category">{{selectedItem.category}}</div>
										</div>
									</div>
									<div class="pmi-item-frequency">
										<h4>Frequency</h4>
										<div class="weekly-frequency">
											<div class="weekly-frq-item" v-for="(freqitem, freqindex) in frequency" :key="freqindex" >
												<div class="dweek-bar">
													<div class="dw-bar-item" :style="{'height': (freqitem.level * 3)+'px'}">&nbsp;</div>
												</div>
												<div class="dweek-text">{{freqitem.name}}</div>
											</div>
										</div>
									</div>
								</div>
								<div class="pmi-right-info">
									<div class="pmi-item-frequency">
										<h4>Past Usage</h4>
										<div class="past-usage">
											<div class="past-usage-item" v-for="(usageitem, usageindex) in pastUsage" :key="usageindex">
												<div class="psi-name">{{usageitem.usage}}</div>
												<div class="psi-date">{{usageitem.date}}</div>
											</div>
										</div>
									</div>
								</div>
							</div>
						</div>
					</v-dialog>
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
			showAddPecsModal: false,
			showPecsItemModal: false,
			selectedItem: {
				'category': '',
				'item': ''
			},
			frequency: [
				{
					name: 'sun',
					level: 50
				},
				{
					name: 'mon',
					level: 23
				},
				{
					name: 'tue',
					level: 62
				},
				{
					name: 'wed',
					level: 14
				},
				{
					name: 'thu',
					level: 22
				},
				{
					name: 'fri',
					level: 52
				},
				{
					name: 'sat',
					level: 34
				},
			],
			pastUsage: [
				{
					usage: 'this is a sample usage',
					date: 'October 13, 2021 7:30pm'
				},
				{
					usage: 'this is a sample usage',
					date: 'October 13, 2021 7:30pm'
				},
				{
					usage: 'this is a sample usage',
					date: 'October 13, 2021 7:30pm'
				},
				{
					usage: 'this is a sample usage',
					date: 'October 13, 2021 7:30pm'
				},
				{
					usage: 'this is a sample usage',
					date: 'October 13, 2021 7:30pm'
				},
				{
					usage: 'this is a sample usage',
					date: 'October 13, 2021 7:30pm'
				},
				{
					usage: 'this is a sample usage',
					date: 'October 13, 2021 7:30pm'
				},
			],
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
	},
	methods: {
		toggleSelectedItem(category, nitem){
			this.selectedItem.category = category;
			this.selectedItem.item = nitem;
			this.showPecsItemModal = true;
		},
		toogleAddNewIcon(){
			console.log('herer');
			this.showAddPecsModal = true;
		},
		toogleCloseAddIcon(){
			this.showAddPecsModal = false;
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
        width: 13%;
        margin-right: 2%;
		margin-bottom: 15px;
		cursor: pointer;
        vertical-align: top;
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

	/* modal */
	.pecs-modal-item-inner h2 {
		/* text-align: center; */
	}
	.pmi-item-category {
		/* text-align: center; */
	}
	.pecs-modal-item-inner {
		background: #fff;
	}
	.pmi-main-image {
	}
	.pmi-main-image img {
		border-radius: 150px;
		border: 5px solid #ff9392;
	}
	.pmi-item-category,
	.pmi-item-frequency {
		/* padding: 15px 20px; */
	}

	.pmi-left-info {
		vertical-align: top;
		display: inline-block;
		width: 50%;
	}
	.pmi-right-info {
		vertical-align: top;
		display: inline-block;
		width: 49%;
	}
	
	.weekly-frequency {
		text-align: center;
	}
	
	.weekly-frequency .weekly-frq-item {
		display: inline-block;
		width: 11%;
		text-align: center;
		font-size: 14px;
		margin: 0 1%;
	}

	.pmi-left-info .base-image .base-left-part {
		display: inline-block;
		vertical-align: middle;
		width: 25%;
	}

	.pmi-left-info .base-image .base-left-part img {
		width: 100%;
	}

	.pmi-left-info .base-image .base-right-part {
		display: inline-block;
		vertical-align: middle;
		width: 73%;
		text-align: left;
		padding-left: 20px;
	}

	.pecs-modal-item-inner {
		padding: 20px;
	}

	.weekly-frequency .weekly-frq-item .dweek-bar .dw-bar-item {
		background: #ff9392;
		border-radius: 5px;
		width: 80%;
    	margin: 0 auto;
	}

	.weekly-frequency .weekly-frq-item .dweek-text {
		text-transform: uppercase;
		font-weight: bold;
		font-size: 12px;
	}

	.pmi-item-frequency h4 {
		text-transform: capitalize;
		font-weight: 400;
		line-height: 1em;
		margin-bottom: 15px;
		border-bottom: 1px solid #ccc;
		padding-bottom: 5px;
	}

	.pmi-item-frequency {
		padding: 0 20px;
	}

	.base-image {
		margin-bottom: 20px;
	}

	.past-usage .past-usage-item .psi-name {
		font-size: 12px;
		background: #ff939260;
		padding: 5px 10px;
		line-height: 1.3em;
		border-radius: 5px;
	}

	.past-usage .past-usage-item {
		margin-bottom: 10px;
	}

	.past-usage .past-usage-item .psi-date {
		font-size: 11px;
		text-align: right;
	}
	.add-pecs-modal {
		background: #fff;
		padding: 20px;
	}
	.add-pecs-item {
		margin-bottom: 15px;
	}
	.add-pecs-item label {
		display: block;
		font-size: 14px;
		line-height: 1em;
		margin-bottom: 3px;
	}
	.add-pecs-modal h4 {
		line-height: 1em;
		margin-bottom: 5px;
		font-size: 17px;
		border-bottom: 1px solid #ccc;
		padding-bottom: 5px;
	}
	.add-pecs-modal .d-subtitle {
		line-height: 1.2em;
		font-size: 13px;
		margin-bottom: 15px;
	}
	.add-pecs-item select {
		width: 100%;
		display: block;
		border: 1px solid #ccc;
		font-size: 14px;
		padding: 10px 20px;
		border-radius: 6px;
	}
	.add-pecs-buttons {
		text-align: center;
	}
	.add-pecs-buttons .add-tile-cancel{
		background: #ccc;
		font-weight: bold;
		font-size: 13px;
		line-height: 1em;
		padding: 10px 20px;
		border-radius: 5px;
		margin-right: 10px;
	}
	.add-pecs-buttons .add-tile-save{
		background: #ff9392;
		font-weight: bold;
		font-size: 13px;
		line-height: 1em;
		padding: 10px 20px;
		border-radius: 5px;
		margin-right: 15px;
	}
</style>
