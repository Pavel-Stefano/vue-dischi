<template>
    <div class="container">
        <div class="yellow"></div>
        <div class="red"></div>
        <div class="blue"></div>
        <div class="violet"></div>
    </div>
</template>

<script>
export default {
    name:'AppLoader',
}
</script>

<style scoped lang="scss">
@import '../style/variables';

.container {
	display: flex;
	justify-content: center;
	align-items: center;
}
div > div {
	width: 3vw;
	height: 3vw;
	border-radius: 100%;
	margin: 2vw;
	background-image: linear-gradient(145deg, rgba(255,255,255,0.5) 0%, rgba(0,0,0,0) 100%);
	animation: bounce 1.5s 0.5s linear infinite;
}
.yellow {
	background-color: $colorAyellow;
}

.red {
	background-color: $colorAred;
	animation-delay: 0.1s;
}

.blue {
	background-color: $colorAblue;
	animation-delay: 0.2s;
}

.violet {
	background-color: $colorAviolet;
	animation-delay: 0.3s;
}

@keyframes bounce {
	0%, 50%, 100% {
		transform: scale(1);
		filter: blur(0px);
	}
	25% {
		transform: scale(0.6);
		filter: blur(3px);
	}
	75% {
		filter: blur(3px);
		transform: scale(1.4);
	}
}

</style>