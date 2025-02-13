<script lang="ts">
	import {
		TUILogin
	} from '@tencentcloud/tui-core';
	// #ifdef APP-PLUS || H5
	import {
		TUIChatKit
	} from './TUIKit';
	TUIChatKit.init();
	// #endif

	let vueVersion = 2;
	// #ifdef VUE3
	vueVersion = 3;
	// #endif

	// Required information
	// You can get userSig from TencentCloud chat console for Testing TUIKit.
	// Deploy production environment please get it from your server.
	// View https://cloud.tencent.com/document/product/269/32688
	uni.$SDKAppID = 1600072287; // Your SDKAppID
	uni.$userID = 'test_001'; // Your userID
	uni.$userSig = 'eJwtzFELgjAYheH-sltDv83mptBFN0WgIBVFIISxGR*xWG6FEf33TL08zwvnQ-b5LnzplmSEhUBmw0al7x4bHNhr588AdGpO3WprUZGMJgAgGJNiLLqz2OreOeesT6N6NH8TcRrPEw7p9ILX-trl76SKlJVVJOmmioygZXHs6vKxOjy3pgA82cZc1oFYBq5YkO8PKsYycg__'; // Your userSig

	export default {
		onLaunch: function() {
			TUILogin.login({
				SDKAppID: uni.$SDKAppID,
				userID: uni.$userID,
				userSig: uni.$userSig,
				useUploadPlugin: true, // If you need to send rich media messages, please set to true.
				framework: `vue${vueVersion}` // framework used vue2 / vue3
			}).catch(() => {});
		}
	};
</script>
<style>
	/* common css for page */
	uni-page-body,
	html,
	body,
	page {
		width: 100% !important;
		height: 100% !important;
		overflow: hidden;
	}
</style>
