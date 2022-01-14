<template>
	<v-app class="main-structure">
		<div class="ms-inner">
			<div class="ms-sidebar">
				<SidebarMenu />
			</div>
			<div class="ms-content">
				<div class="ms-content-inner">
					<div class="ms-header">
						<div class="ms-header-inner">
							this is the header
						</div>
					</div>
					<router-view />
				</div>
			</div>
		</div>
	</v-app>
</template>

<script>
export default {
    name: 'Dashboard'
}
</script>

<style scoped>
	
	.main-structure{
		background: #f4f5fa;
		color: rgba(94,86,105,.87);
		font-family: 'Inter', sans-serif;
	}
	.ms-sidebar {
		position: absolute;
		width: 260px;
		height: 100vh;
	}
	.ms-content {
		margin-left: 400px;
		width: 75%;
	}
	
</style>