<template>
	<div class="dmainpage">
		<div class="dmain-content">
			<div class="content-card dheadwithbg">
				<div class="cc-inner">
					<div class="top-left">
						<PageTitle title="All Teachers" subtitle="Show list of all teachers" />
					</div>
					<div class="top-right">
						filters here
					</div>
					<br class="clear">
				</div>
			</div>
			<div class="dteachers-list">
				<div class="dtl-inner">
					<div class="dtl-item" v-for="(item, key) in teachers" :key="key">
						<div class="dtl-item-inner">
							<div class="dprofile-photo">
								<img src="~/assets/images/teacher_diff.png" />
							</div>
							<div class="tname">{{ item.name }}</div>
							<div class="tschool">{{ item.school }}</div>
							<div class="tpos">{{ item.position }}</div>
							<div class="ddetailsbutton">
								<NuxtLink to="/teachers/profile">View Profile</NuxtLink>
								<!-- <button>View Details</button> -->
							</div>
						</div>
					</div>
					<br class="clear">
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Teachers',
		layout: 'Dashboard',
		data(){
			return {
				teachers: [
					{
						id: '12345',
						name: 'Some Teacher',
						position: 'SPED Teacher 1',
						contact: '09234352341',
						school: 'Sta. Ana Central Elementary School',
						id: 'SYS1034fsdf'
					},
					{
						id: '12345',
						name: 'Some Teacher',
						position: 'SPED Teacher 1',
						contact: '09234352341',
						school: 'Sta. Ana Central Elementary School',
						id: 'SYS1034fsdf'
					},
					{
						id: '12345',
						name: 'Some Teacher',
						position: 'SPED Teacher 1',
						contact: '09234352341',
						school: 'Sta. Ana Central Elementary School',
						id: 'SYS1034fsdf'
					},
					{
						id: '12345',
						name: 'Some Teacher',
						position: 'SPED Teacher 1',
						contact: '09234352341',
						school: 'Sta. Ana Central Elementary School',
						id: 'SYS1034fsdf'
					},
					{
						id: '12345',
						name: 'Some Teacher',
						position: 'SPED Teacher 1',
						contact: '09234352341',
						school: 'Sta. Ana Central Elementary School',
						id: 'SYS1034fsdf'
					},
					{
						id: '12345',
						name: 'Some Teacher',
						position: 'SPED Teacher 1',
						contact: '09234352341',
						school: 'Sta. Ana Central Elementary School',
						id: 'SYS1034fsdf'
					},
					{
						id: '12345',
						name: 'Some Teacher',
						position: 'SPED Teacher 1',
						contact: '09234352341',
						school: 'Sta. Ana Central Elementary School',
						id: 'SYS1034fsdf'
					}
				]
			}
		}
	}
</script>

<style scoped>
	.clear {
		clear: both;
	}
	.content-card {
		background: #fff;
		box-shadow: 0 2px 10px 0 rgb(94 86 105 / 10%);
		border-radius: 10px;
		margin-bottom: 25px;
	}
	.content-card.dheadwithbg {
		background: url('~/assets/images/head_bg.png') no-repeat center center;
		background-size: cover !important;
		    padding: 20px;
	}
	.content-card.dheadwithbg .cc-inner {
		background: rgb(255 255 255 / 80%);
		padding: 25px 30px;
		border-radius: 5px;
	}
	.top-left,
	.top-right {
		float: left;
		width: 50%;
	}
	.dtl-item {
		float: left;
		width: 20%;
	}
	.dtl-inner {
		margin: 0 -10px;
	}
	.dtl-item-inner {
		background: #fff;
		box-shadow: 0 2px 10px 0 rgb(94 86 105 / 10%);
		padding: 25px 30px;
		border-radius: 5px;
		margin: 0 10px 15px;
		border: 3px solid #fff;
		transition: .5s ease-out;
	}
	.dtl-item-inner:hover {
		background: #e8def7;
		border: 3px solid #9155fd;
		transition: .5s ease-out;
	}
	.dprofile-photo {
		/* width: 76%; */
		margin: 0 auto;
	}

	.dprofile-photo img {
		width: 100%;
		border-radius: 5px;
	}

	.tname {
		font-weight: 600;
		text-align: center;
		font-size: 16px;
		line-height: 1em;
		margin-top: 10px;
		margin-bottom: 5px;
	}
	.tschool {
		text-align: center;
		font-size: 12px;
		line-height: 1em;
	}
	.tpos {
		text-align: center;
		font-size: 14px;
	}
	.ddetailsbutton {
		text-align: center;
	}
	.ddetailsbutton a {
		background: #9155fd;
		color: #fff;
		margin-top: 15px;
		font-size: 12px;
		text-transform: uppercase;
		line-height: 1em;
		padding: 15px 35px;
		border-radius: 10px;
		display: inline-block;
    	text-decoration: none;
	}
</style>
