<template>
	<div class="main-menu">
        <div class="menu-inner">
            <ul>
                <li class="main-segment">
                    <div class="ms-title-host">
                        Dashboard
                    </div>
                </li>
                <li class="main-segment">
                    <div class="ms-title-holder"><div class="ms-title"><span>Teachers</span></div></div>
                    <ul>
                        <li><NuxtLink to="/teachers/all">All Teachers</NuxtLink></li>
                    </ul>
                </li>
                <li class="main-segment">
                    <div class="ms-title-holder"><div class="ms-title"><span>Students</span></div></div>
                    <ul>
                        <li><NuxtLink to="/students/all">My Students</NuxtLink></li>
                    </ul>
                </li>
                <li class="main-segment">
                    <div class="ms-title-holder"><div class="ms-title"><span>Reports</span></div></div>
                    <ul>
                        <li><NuxtLink to="/records/all">Report Generation</NuxtLink></li>
                    </ul>
                </li>
                <li class="main-segment">
                    <div class="ms-title-holder"><div class="ms-title"><span>Settings</span></div></div>
                    <ul>
                        <li><NuxtLink to="/settings/accounts">Account Setting</NuxtLink></li>
                        <li><NuxtLink to="/settings/site">Site Setting</NuxtLink></li>
                    </ul>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    // name: 'Dashboard'
}
</script>

<style scoped>
    .menu-inner ul {
        margin: 0;
        padding: 0;
    }
    .menu-inner ul li {
        list-style: none;
    }
    .main-segment {
        position: relative;
    }
    .ms-title-holder {
        position: relative;
        margin: 15px 0;
        white-space: nowrap;
        align-items: center;
        display: flex;
    }
    li.main-segment {
        margin-bottom: 10px;
        display: flow-root;
    }
	.main-segment .ms-title{
        width: 100%;
        position: absolute;
        left: 0;
        border-bottom: 1px solid rgba(94,86,105,.14);
        line-height: .1em;
    }
    .main-segment .ms-title span {
		margin-left: 30px;
		background: #f4f5fa;
		font-size: 12px;
		text-transform: uppercase;
		font-weight: 600;
		padding: 0 10px;
	}
    .main-segment ul {
        /* margin-left: 50px; */
    }
    .main-segment ul li {
        font-size: 14px;
        line-height: 1em;
        /* margin-bottom: 10px; */
    }
    .main-segment ul li a {
        display: block;
        padding: 15px;
        padding-left: 40px;
        text-decoration: none;
        border-radius: 0 50px 50px 0;
        color: rgba(94,86,105,.87);
    }
    .main-segment ul li a:hover,
    .main-segment ul li a.nuxt-link-exact-active.nuxt-link-active {
        background: rgb(196,142,255);
        background: linear-gradient(137deg, rgba(196,142,255,1) 0%, rgba(145,85,253,1) 100%);
        color: #fff;
    }
</style>