<script>
	import '../app.css';
    import { fade, slide } from 'svelte/transition';

	let isFeature = false;
	let isCompany = false;

	let isOpen = false;

	let isFeatureMobile = false;
    let isCompanyMobile = false;
</script>

<div class="container">
	<div class="header">
		<div class="headerLeft">
			<img class="logoHeader" src="images/logo.svg" alt="" />
			<div class="headerMenu">
				<div class="menu" on:click={() => (isFeature = !isFeature)}>
					<p style="font-size: 16px;">Features</p>
					<img src="images/icon-arrow-up.svg" alt="" />
				</div>
				{#if isFeature}
					<div class="featureMenus">
						<div class="iconList">
							<img src="images/icon-todo.svg" alt="" />
							<p>Todo List</p>
						</div>
						<div class="iconList">
							<img src="images/icon-calendar.svg" alt="" />
							<p>Calender</p>
						</div>
						<div class="iconList">
							<img src="images/icon-reminders.svg" alt="" />
							<p>Reminders</p>
						</div>
						<div class="iconList">
							<img src="images/icon-planning.svg" alt="" />
							<p>Planning</p>
						</div>
					</div>
				{/if}

				<div class="menu" on:click={() => (isCompany = !isCompany)}>
					<p style="font-size: 16px;">Company</p>
					<img src="images/icon-arrow-up.svg" alt="" />
				</div>
				{#if isCompany}
					<div class="companyMenus">
						<div class="iconList">
							<p>History</p>
						</div>
						<div class="iconList">
							<p>Our Team</p>
						</div>
						<div class="iconList">
							<p>Blog</p>
						</div>
					</div>
				{/if}

				<div class="menu">
					<p style="font-size: 16px;">Careers</p>
				</div>
				<div class="menu">
					<p style="font-size: 16px;">About</p>
				</div>
			</div>
		</div>
		<div class="headerRight">
			<div class="menusRight">
				<div class="menu">
					<p style="font-size: 16px;">Login</p>
				</div>
				<button class="btnHeader"> Register </button>
			</div>
		</div>
		<div class="headerCrumb" on:click={() => (isOpen = !isOpen)}>
			<img src="images/icon-menu.svg" alt="" />
		</div>
		{#if isOpen}
			<div class="menusMobile" >
				<div class="closeBtn" on:click={() => (isOpen = !isOpen)}>
					<img src="images/icon-close-menu.svg" alt=""/>
				</div>
				<div class="menuMobile">
					<div 
                        class="menusListMobile" 
                        on:click={() => (isFeatureMobile = !isFeatureMobile)} 
                        aria-expanded={isFeatureMobile}>
						<p style="font-size: 16px;">Features</p>
						<img class="iconMobile" src="images/icon-arrow-down.svg" alt=""/>
					</div>
                    {#if isFeatureMobile}
                    <div class="featureMenusMobile" transition:slide|local={{ duration: 200 }}>
						<div class="iconList">
							<img src="images/icon-todo.svg" alt="" />
							<p style="font-size: 16px;">Todo List</p>
						</div>
						<div class="iconList">
							<img src="images/icon-calendar.svg" alt="" />
							<p style="font-size: 16px;">Calender</p>
						</div>
						<div class="iconList">
							<img src="images/icon-reminders.svg" alt="" />
							<p style="font-size: 16px;">Reminders</p>
						</div>
						<div class="iconList">
							<img src="images/icon-planning.svg" alt="" />
							<p style="font-size: 16px;">Planning</p>
						</div>
					</div>
                    {/if}
					
				</div>
				<div class="menuMobile">
					<div 
                        class="menusListMobile" 
                        on:click={() => (isCompanyMobile = !isCompanyMobile)}
                        aria-expanded={isCompanyMobile}>
						<p style="font-size: 16px;">Company</p>
						<img class="iconMobile" src="images/icon-arrow-down.svg" alt="" />
					</div>
                    {#if isCompanyMobile}
                    <div class="featureMenusMobile" transition:slide|local={{ duration: 200 }}>
						<div class="iconList">
							<p style="font-size: 16px;">History</p>
						</div>
						<div class="iconList">
							<p style="font-size: 16px;">Our Team</p>
						</div>
						<div class="iconList">
							<p style="font-size: 16px;">Blog</p>
						</div>
					</div>
                    {/if}
                    
				</div>
				<div class="menuMobile">
					<div class="menusListMobile">
						<p style="font-size: 16px;">Careers</p>
					</div>
				</div>
				<div class="menuMobile">
					<div class="menusListMobile">
						<p style="font-size: 16px;">About</p>
					</div>
				</div>
				<div class="btnMobile">
					<div>
						<p class="txtLogin">Login</p>
					</div>
					<button class="btnRegister"> Register </button>
				</div>
			</div>
		{/if}
	</div>
	<div class="content">
		<div class="contentLeft">
			<h1 class="contentHeader">Make</h1>
			<h1 class="contentHeader">remote work</h1>
			<p class="contentSub">
				Get your team in sync, no matter your location. Streamline processes, create team rituals,
				and watch productivity soar.
			</p>
			<div class="btn">
				<button class="contentBtn"> Learn more </button>
			</div>
			<div class="client">
				<img src="images/client-databiz.svg" alt="" />
				<img src="images/client-audiophile.svg" alt="" />
				<img src="images/client-meet.svg" alt="" />
				<img src="images/client-maker.svg" alt="" />
			</div>
		</div>
		<div class="contentRight">
			<img style="width: 100%;" src="images/image-hero-desktop.png" alt="" />
		</div>
		<div class="contentMobile">
			<div class="imgMobile">
				<img style="width: 100%;" src="images/image-hero-mobile.png" alt="" />
			</div>
			<div class="headerMobile">
				<h1 class="titleMobile">Make remote work</h1>
				<p class="subMobile">
					Get your team in sync, no matter your location. Streamline processes, create team rituals,
					and watch productivity soar.
				</p>
				<button class="contentBtn">Learn More</button>
			</div>
			<div class="clientMobile">
				<img src="images/client-databiz.svg" alt="" />
				<img src="images/client-audiophile.svg" alt="" />
				<img src="images/client-meet.svg" alt="" />
				<img src="images/client-maker.svg" alt="" />
			</div>
		</div>
	</div>
</div>

<style>
	.container {
		width: 100%;
		height: 100%;
	}

	.header {
		width: 100%;
		display: flex;
		align-items: center;
		padding: 20px;
	}

	.headerLeft {
		width: 50%;
		display: flex;
		padding: 10px;
		/* justify-content: space-between; */
	}

	.headerMenu {
		position: relative;
		width: 100%;
		display: flex;
		justify-content: space-evenly;
	}

	.headerCrumb {
		display: none;
	}

	.headerMobile {
		display: none;
	}

	.menu {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 10px;
		cursor: pointer;
		font-weight: 500;
	}

	.menu:hover {
		transition: 5s ease-in-out;
		font-weight: 700;
	}

	.headerRight {
		width: 50%;
		padding: 10px;
		display: flex;
		justify-content: flex-end;
	}

	.menusRight {
		display: flex;
		align-items: center;
		gap: 20px;
	}

	.btnHeader {
		border: 1px solid var(--gray);
		border-radius: 10px;
		padding: 10px;
		color: var(--gray);
		font-weight: 700;
		width: 100px;
		cursor: pointer;
	}

	.btnHeader:hover {
		border: 1px solid var(--black);
		color: var(--black);
		transition: 500ms;
	}

	.featureMenus {
		position: absolute;
		top: 45px;
		left: 10px;
		background-color: var(--white);
		padding: 15px;
		box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
		border-radius: 10px;
		height: auto;
	}

	.companyMenus {
		position: absolute;
		top: 45px;
		left: 222px;
		background-color: var(--white);
		padding: 15px;
		box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
		border-radius: 10px;
		height: auto;
	}

	.iconList {
		display: flex;
		/* justify-content: center; */
		align-items: flex-start;
		margin: 10px;
		gap: 10px;
		padding-top: 5px;
	}

	.content {
		width: 100%;
		display: flex;
		padding: 50px;
	}

	.contentMobile {
		display: none;
	}

	.contentLeft {
		width: 50%;
		padding-top: 50px;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.contentHeader {
		font-size: 72px;
		padding: 0px 100px;
		width: 100%;
	}

	.contentSub {
		padding: 60px 130px 60px 100px;
		line-height: 1.5rem;
		color: var(--gray);
	}

	.contentRight {
		width: 50%;
		padding: 0px 120px;
	}

	.btn {
		width: 100%;
		padding: 20px 100px;
	}

	.client {
		width: 100%;
		padding: 60px 100px;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.clientMobile,
	.menusMobile {
		display: none;
	}

	.contentBtn {
		border: 1px solid var(--black);
		border-radius: 10px;
		padding: 15px;
		background-color: var(--black);
		color: var(--white);
		font-weight: 700;
		font-size: 18px;
		/* width: 100px; */
		cursor: pointer;
	}

	.contentBtn:hover {
		color: var(--black);
		background-color: var(--white);
	}

	@media only screen and (max-width: 768px) {
		.content {
			padding: 20px 0px;
		}

		.logoHeader {
			width: 50%;
		}

		.contentRight,
		.contentLeft,
		.headerMenu,
		.headerRight {
			display: none;
		}

		.btnRegister {
			width: 90%;
			border: 1px solid var(--gray);
			border-radius: 10px;
			padding: 10px;
			color: var(--gray);
			font-weight: 700;
			/* width: 100px; */
			cursor: pointer;
		}
		.headerCrumb {
			position: relative;
			display: flex;
			justify-content: flex-end;
			width: 50%;
		}

		.headerMobile {
			display: block;
			width: 100%;
			padding: 30px 0px;
			text-align: center;
		}

		.featureMenusMobile {
			padding: 20px;
		}

		.titleMobile {
			padding: 20px 0px;
		}

		.menusMobile {
			display: block;
			position: absolute;
			top: 0;
			right: 0;
			padding: 10px;
			height: auto;
			/* border: 1px solid var(--black); */
			background-color: var(--white);
			z-index: 10;
			width: 40%;
		}

		.menuMobile {
			position: relative;
			width: 100%;
			color: var(--gray);
			/* padding: 20px; */
		}

		.txtLogin {
			color: var(--gray);
			font-size: 16px;
			cursor: pointer;
			margin-bottom: 20px;
		}

		.btnMobile {
			width: 100%;
			text-align: center;
			margin-top: 20px;
		}

		.menusListMobile {
			display: flex;
			align-items: center;
			gap: 10px;
			padding: 10px 20px;
		}

		.subMobile {
			padding: 10px 10px;
			text-align: center;
			width: 100%;
			color: var(--gray);
			line-height: 2rem;
		}

		.contentMobile {
			display: block;
			width: 100%;
		}

		.imgMobile {
			width: 100%;
		}

		.clientMobile {
			padding: 20px;
			display: flex;
			justify-content: space-between;
			width: 100%;
		}

		.closeBtn {
			width: 100%;
			display: flex;
			justify-content: flex-end;
			padding: 10px;
		}

        [aria-expanded='true'] .iconMobile {
		transform: rotate(0.5turn);
	}
	}
</style>
