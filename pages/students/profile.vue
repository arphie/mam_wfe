<template>
	<div class="dstudentprofile">
		<div class="ds-inner">
			<div class="dmain-cont">
				<div class="dm-left">
					<div class="dm-left-inner">
						<div class="dprofilecard">
							<div class="dpc-inner">
								<div class="dprofileimage">
									<img src="~/assets/images/teacher_diff.png" />
								</div>
								<div class="dstudentname">John Peter Doe</div>
								<div class="dstudent">Sample elementary school</div>
								<div class="dheaddetails">
									<ul>
										<li><button v-on:click="changeMainContent('user')">Personal Details</button></li>
										<li><button v-on:click="changeMainContent('pecs')">Personal Pecs</button></li>
									</ul>
								</div>
							</div>
						</div>
					</div>
					<div class="side-timeline">
						<div class="pc-inner">
							<v-timeline align-top dense class="dtimeline">
								<v-timeline-item>
									<div class="dactivityinner">
										<h3>Sent request for connection with Teacher</h3>
										<div class="ddate">Jan 01, 2021 12:34pm</div>
										<div class="dmessage">
											Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla ut sollicitudin orci. Nam eget risus eget lorem lobortis maximus vel sit amet lacus.
										</div>
									</div>
								</v-timeline-item>
								<v-timeline-item>
									<div class="dactivityinner">
										<h3>Successfully connected with teacher</h3>
										<div class="ddate">Jan 08, 2021 12:34pm</div>
										<div class="dmessage">
											Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla ut sollicitudin orci. Nam eget risus eget lorem lobortis maximus vel sit amet lacus.
										</div>
									</div>
								</v-timeline-item>
								<v-timeline-item>
									<div class="dactivityinner">
										<h3>Teacher setup PECS Board</h3>
										<div class="ddate">Jan 09, 2021 12:34pm</div>
										<div class="dmessage">
											Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla ut sollicitudin orci. Nam eget risus eget lorem lobortis maximus vel sit amet lacus.
										</div>
									</div>
								</v-timeline-item>
							</v-timeline>
						</div>
					</div>
				</div>
				<div class="dm-right">
					<div class="dm-right-inner">
						<div class="profcontent">
							<div class="profcontent-inner">
								<!-- pecs board manipulation -->
								<div class="pc-item">
									<div class="pc-inner" v-if="showUserDetails == 'pecs'">
										<PecsCustom />
									</div>
									<div class="pc-inner" v-if="showUserDetails == 'user'">
										<UserProfileInfo />
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
				<br class="clear">
			</div>

		</div>
	</div>
</template>
<script>
	export default {
		name: 'Profile',
		layout: 'Dashboard',
		data() {
			return {
				showUserDetails: 'user',
			}
		},
		methods: {
			changeMainContent(item){
				this.showUserDetails = item;
			}
		}
	}
</script>

<style scoped>
	.clear {
		clear: both;
	}
	.dm-left {
		float: left;
		width: 30%;
	}
	.dm-right {
		float: right;
		width: 70%;
	}
	.dprofilecard {
		padding: 25px 30px;
		border-radius: 5px;
		margin: 0 10px 15px;
		transition: .5s ease-out;
	}
	.dprofileimage {
		text-align: center;
	}
	.dprofileimage img {
		border-radius: 150px;
		border: 5px solid #ff9392;
	}
	.dheaddetails {
		line-height: 1em;
		/* border-bottom: 1px solid rgba(94,86,105,.14); */
		margin-top: 20px;
		padding-bottom: 5px;
		font-weight: bold;
	}
	.dheaddetails ul {
		padding: 0;
	}
	.dheaddetails ul li {
		list-style: none;
		margin-bottom: 5px;
	}
	.dheaddetails ul li button {
		background: linear-gradient(137deg, #ff8f8f 0%, #eb4949 100%);
		display: block;
		width: 100%;
		text-align: left;
		line-height: 1em;
		padding: 10px 15px;
		text-decoration: none;
		font-size: 13px;
		font-weight: 400;
		color: #fff;
		border-radius: 5px;
		border: 1px solid #eb4949;
	}
	.dstudentname {
		text-align: center;
		font-size: 21px;
		font-weight: bold;
	}
	.teacher_details {
		text-align: center;
	}
	.teacher_details .tschool,
	.teacher_details .teacher_details {
		font-size: 14px;
		text-transform: capitalize;
	}
	.teacher_details .semail {
		font-size: 14px;
	}
	.pc-item {
		background: #fff;
		box-shadow: 0 2px 10px 0 rgb(94 86 105 / 10%);
		padding: 25px 30px;
		border-radius: 5px;
		margin: 0 10px 15px;
		border: 3px solid #fff;
		transition: .5s ease-out;
	}
	.dactivityinner h3 {
		font-size: 16px;
		line-height: 1em;
		margin-bottom: 5px;
	}
	.dactivityinner .ddate {
		font-size: 13px;
		line-height: 1em;
		margin-bottom: 5px;
	}
	.dactivityinner .dmessage {
		font-size: 14px;
		line-height: 1.3em;
	}
	.ddash-inner .dleft {
		float: left;
		width: 60%;
	}
	.dright {
		float: left;
		width: 40%;
	}
	.profheader {
		text-align: right;
    	padding: 0 10px 15px;
	}
	.profheader ul {
		margin: 0;
		padding: 0;
	}
	.profheader ul li {
		list-style: none;
		display: inline-block;
	}
	.profheader ul li button {
		background: rgb(196,142,255);
		background: linear-gradient(137deg, #c48eff 0%, #9155fd 100%);
		color: #fff;
		font-size: 14px;
		font-weight: 400;
		line-height: 1em;
		padding: 10px 30px;
		border-radius: 50px;
	}
	.side-timeline {
	    width: 95%;
	}
</style>

<style>
	.dtimeline .v-timeline-item__inner-dot.primary {
		background: #ff8f8f;
		background: linear-gradient(137deg, #ff8f8f 0%, #eb4949 100%);
		height: 20px;
		width: 20px;
	}
	.dtimeline .v-timeline-item__dot {
		background: #ffcdce !important;
		width: unset;
    	height: unset;
	}
	.dtimeline.v-timeline::before {
		background: #ffcdce !important;
	}
</style>
