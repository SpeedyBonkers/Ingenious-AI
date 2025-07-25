<script>
	let email = "";
	let password = "";
</script>

<main>
	<div class="header">
		<div class="logo-area">
			<span class="menu-icon">&#9776;</span>
			<img src="/Ingenious.png" alt="Ingenious AI" />
		</div>
		<div class="header-actions">
			<div class="Login">Log in</div>
			<button class="Signup">Sign up</button>
			<div class="header-avatar">👤</div>
		</div>
	</div>

	<div class="main">
		<div class="login-container">
			<div class="login-title">Log in</div>
			<div class="underline"></div>
			<form>
				<input type="email" placeholder="Email" bind:value={email} />
				<input
					type="password"
					placeholder="Password"
					bind:value={password}
				/>
				<button type="submit" class="login-btn">Log in</button>
				<a class="forgot-link" href="#">Forgot password?</a>
			</form>
		</div>
	</div>
</main>

<style>
	body,
	:global(body) {
		margin: 0;
		padding: 0;
		background: #efe9e0;
		font-family: "Inter", Arial, sans-serif;
	}

	.main {
		display: flex;
		justify-content: center;
		align-items: center;
		height: calc(100vh - 56px);
		background-color: #efe9e0;
		}
	.header {
		background: #0f9e99;
		height: 56px;
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 0 24px;
		box-sizing: border-box;
	}
	.logo-area {
		display: flex;
		align-items: bottom;
		justify-content: bottom;
		width: 20%;
	}

	.menu-icon {
	min-width: 36px;
    height: 36px;
    border: 2px solid #222;
    border-radius: 8px;
    background: none;
    margin-right: 16px;
    margin-top: auto;
    margin-bottom: auto;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
	}

	.header-actions {
		display: flex;
		align-items: center;
		gap: 18px;
	}
	.Login {
		font-size: 0.95rem;
		color: #000000;
		text-decoration: none;
		padding: 0 6px;
	}
	.Signup {
		background: #fff;
		color: #222;
		border: 2px solid #222;
		border-radius: 8px;
		padding: 5px 16px;
		font-weight: bold;
		cursor: pointer;
		font-size: 1rem;
		box-shadow: 0 1px 2px #0001;
		min-width: 100px;
	}
	.header-avatar {
		background: #fff;
		width: 32px;
		height: 32px;
		border: 2px solid #222;
		border-radius: 50%;
		display: flex;
		align-items: center;
		justify-content: center;
		font-weight: bold;
	}

	.login-container {
		background: transparent;
		padding: 32px 32px 16px 32px;
		border-radius: 8px;
		box-shadow: none;
		width: 320px;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.login-title {
		font-size: 2.5rem;
		font-weight: 400;
		margin-bottom: 10px;
		text-align: center;
		letter-spacing: 1px;
	}
	.underline {
		width: 90%;
		height: 2px;
		background: #bdbdbd;
		margin: 0 auto 16px auto;
	}
	form {
		width: 100%;
		display: flex;
		flex-direction: column;
		gap: 10px;
	}
	input[type="email"],
	input[type="password"] {
		border: 1px solid #ccc;
		border-radius: 8px;
		padding: 8px;
		font-size: 1rem;
		background: #fff;
	}
	.login-btn {
		background: #222;
		color: #fff;
		border: none;
		border-radius: 8px;
		padding: 8px 0;
		font-size: 1rem;
		margin-top: 6px;
		cursor: pointer;
	}
	.forgot-link {
		font-size: 0.95rem;
		color: #222;
		margin-top: 4px;
		text-align: center;
		text-decoration: underline;
		cursor: pointer;
	}
	
	@media (max-width: 500px) {
		.login-container {
			width: 90vw;
			padding: 16px 4vw;
		}
	}
</style>
