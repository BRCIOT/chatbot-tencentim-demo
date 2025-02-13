<template>
	<div>
		<button @click="openConversationList">打开会话列表</button>
		<button @click="openContact">打开联系人</button>
		<button @click="openContactUserDirect">发起Chatbot对话</button>
	</div>
</template>
<script>
	export default {
		methods: {
			// 打开会话列表
			openConversationList() {
				uni.navigateTo({
					url: '/TUIKit/components/TUIConversation/index'
				});
			},
			// 打开联系人
			openContact() {
				uni.navigateTo({
					url: '/TUIKit/components/TUIContact/index'
				});
			},
			openContactUserDirect() {
				// 1v1 chat: conversationID = `C2C${userID}`
				// group chat: conversationID = `GROUP${groupID}`
				const userID = uni.$userID;
				const conversationID = `C2C${userID}`
				uni.navigateTo({
					url: `/TUIKit/components/TUIChat/index?conversationID=${conversationID}`
				});
			},
			// onSubmitSendMsg() {
			// import {
			// 		TUIChatService
			// 	} from "@tencentcloud/chat-uikit-engine";
			// 	let promise = TUIChatService.sendCustomMessage({
			// 		payload: {
			// 			data: JSON.stringify({
			// 				// 评价类消息标识字段
			// 				businessID: "evaluation",
			// 				version: 1,
			// 				// 评价分数，此处表示五星
			// 				score: 5,
			// 				// 评价内容文本
			// 				comment: "很棒"
			// 			}),
			// 			description: "对本次的服务评价",
			// 			extension: "对本次的服务评价"
			// 		}
			// 	});
			// 	promise.catch((error) => {
			// 		// 调用异常时业务侧可以通过 promise.catch 捕获异常进行错误处理
			// 	});
			// }
		},
	};
</script>