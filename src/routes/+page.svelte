<script>
	import star from '$lib/images/icon-star.svg';
	import icon from '$lib/images/illustration-thank-you.svg';

	let num;
	let show = false;

	const toggle = (number) => {
		num = number;
	};

	const submitBtn = () => {
		show = !show;
	};
</script>

<div class="container">
	{#if !show}
		<div class="toggle">
			<div class="circle">
				<img class="star" src={star} alt="" />
			</div>
			<h1 class="heading">How did we do?</h1>
			<p class="text">
				Please let us know how we did with your support request. All feedback is appreciated to help
				us improve our offering!
			</p>
			<div class="btns">
				<!-- svelte-ignore a11y-no-static-element-interactions -->
				<!-- svelte-ignore a11y-click-events-have-key-events -->
				<div class={num === 1 ? 'active' : 'btn'} on:click={() => toggle(1)}>1</div>
				<!-- svelte-ignore a11y-no-static-element-interactions -->
				<!-- svelte-ignore a11y-click-events-have-key-events -->
				<div class={num === 2 ? 'active' : 'btn'} on:click={() => toggle(2)}>2</div>
				<!-- svelte-ignore a11y-no-static-element-interactions -->
				<!-- svelte-ignore a11y-click-events-have-key-events -->
				<div class={num === 3 ? 'active' : 'btn'} on:click={() => toggle(3)}>3</div>
				<!-- svelte-ignore a11y-no-static-element-interactions -->
				<!-- svelte-ignore a11y-click-events-have-key-events -->
				<div class={num === 4 ? 'active' : 'btn'} on:click={() => toggle(4)}>4</div>
				<!-- svelte-ignore a11y-no-static-element-interactions -->
				<!-- svelte-ignore a11y-click-events-have-key-events -->
				<div class={num === 5 ? 'active' : 'btn'} on:click={() => toggle(5)}>5</div>
			</div>
			<!-- svelte-ignore a11y-no-static-element-interactions -->
			<!-- svelte-ignore a11y-click-events-have-key-events -->
			<div class="submit" on:click={submitBtn}>SUBMIT</div>
		</div>
	{:else}
		<div class="hide">
			<img class="icon" src={icon} alt="" />
			<div class="box">You selected {num} out of 5</div>
			<div class="thx">Thank you!</div>
			<div class="text-alt">
				We appreciate you taking the time to give a rating. If you ever need more support, don’t
				hesitate to get in touch!
			</div>
		</div>
	{/if}
</div>

<style>
	.container {
		width: 412px;
		height: 416px;
		background: radial-gradient(#232a34, #181e27);
		border-radius: 30px;
		padding: 32px 39px 32px 32px;
	}
	.circle {
		margin-bottom: 30px;
		width: 48px;
		height: 48px;
		border-radius: 100%;
		background-color: #262e38;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.heading {
		margin-bottom: 15px;
		font-weight: bold;
		font-size: 28px;
	}
	.text {
		width: 340px;
		font-size: 15px;
		line-height: 24px;
		color: #969fad;
		margin-bottom: 24px;
	}
	.btns {
		display: flex;
		flex-direction: row;
		gap: 21px;
	}
	.btn {
		width: 51px;
		height: 51px;
		background-color: #262e38;
		border-radius: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		cursor: pointer;
		transition: 0.3s ease-out;
	}
	.btn:hover {
		color: #262e38;
		background-color: #fc7614;
	}
	.active {
		width: 51px;
		height: 51px;
		color: #262e38;
		background-color: white;
		border-radius: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		cursor: pointer;
		transition: 0.3s ease-out;
	}
	.submit {
		margin-top: 32px;
		width: 341px;
		height: 45px;
		border-radius: 22.5px;
		background-color: #fc7614;
		color: #131518;
		font-size: 15px;
		font-weight: bold;
		letter-spacing: 2px;
		display: flex;
		justify-content: center;
		align-items: center;
		cursor: pointer;
		transition: 0.3s ease-out;
	}
	.submit:hover {
		color: #262e38;
		background-color: white;
	}
	.hide {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.icon {
		margin-top: 13px;
		margin-bottom: 32px;
		width: 162px;
		height: 108px;
	}
	.box {
		margin-bottom: 32px;
		display: flex;
		justify-content: center;
		align-items: center;
		border-radius: 22.5px;
		width: 193px;
		height: 32px;
		background-color: #262e38;
		color: #fc7614;
		font-size: 15px;
		line-height: 24px;
	}
	.thx {
		margin-bottom: 15px;
		font-size: 28px;
		font-weight: bold;
	}
	.text-alt {
		text-align: center;
		color: #969fad;
		font-size: 15px;
		line-height: 24px;
	}
	@media only screen and (max-width: 375px) {
		.container {
			width: 327px;
			height: 360px;
			padding: 32px 24px 32px 24px;
		}
		.circle {
			margin-bottom: 16px;
			width: 40px;
			height: 40px;
		}
		.heading {
			margin-bottom: 10px;
			font-size: 24px;
		}
		.text {
			width: 279px;
			font-size: 14px;
			line-height: 22px;
		}
		.btns {
			gap: 17px;
		}
		.btn {
			width: 42px;
			height: 42px;
		}
		.active {
			width: 42px;
			height: 42px;
		}
		.submit {
			margin-top: 24px;
			width: 279px;
			height: 45px;
			font-size: 14px;
			letter-spacing: 1.87px;
		}
		.icon {
			margin-top: 2px;
			margin-bottom: 24px;
			width: 144px;
			height: 96px;
		}
		.box {
			margin-bottom: 24px;
			width: 168px;
			font-size: 14px;
			line-height: 22px;
		}
		.thx {
			margin-bottom: 10px;
			font-size: 24px;
		}
		.text-alt {
			font-size: 14px;
			line-height: 22px;
		}
	}
</style>
