<template>
	<div>
		<div id="modifiers">
			<div @click.capture="clickDiv">
				DIV 영역
				<p @click="clickP">
					P영역
					<span @click="clickSpan">span영역</span>
					<a href="https://naver.com" @click.prevent="clickA">a영역</a>
				</p>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	setup() {
		const clickDiv = () => {
			console.log('click Div');
			// location.href = 'https://naver.com';
		};
		const clickP = () => {
			console.log('click P');
		};
		const clickSpan = e => {
			console.log('click Span');
			e.stopPropagation();
			alert('좋아요');
		};

		const clickA = event => {
			event.preventDefault();
			event.stopPropagation();
			alert('어떤기능~');
		};

		return {
			clickDiv,
			clickP,
			clickSpan,
			clickA,
		};
	},
};
</script>

<style>
#modifiers div,
#modifiers p,
#modifiers span {
	padding: 40px;
}

#modifiers div {
	background-color: #ccc;
}
#modifiers p {
	background-color: #999;
}
#modifiers span {
	background-color: #666;
	display: block;
}
</style>
