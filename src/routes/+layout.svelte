<script>
	import Header from "./Header.svelte";
	import "./styles.css";
</script>

<div class="app">
    <Header />

    <main>
        <slot />
    </main>

    <footer>
        <div class="feur" style="display: flex; justify-content: space-between;">
            <div class="CDG">
                <p>Conditions générale d'utilisation</p>
                <p>Politique de confidentialité</p>
                <p>Gestion de la confidentialité</p>
                <p>Plan du site</p>
                <p>Mentions légales</p>
            </div>
            <div class="logo"> 
                <a href="https://www.twitch.tv/">
                    <img
                        alt="twitter logo"
                        src="https://store-images.s-microsoft.com/image/apps.45406.9007199266244427.4d45042b-d7a5-4a83-be66-97779553b24d.2a88a418-b96d-44a6-ad4f-5e0ee6289b2c"
                    /></a
                >
                <a href="https://www.twitch.tv/">
                    <img
                        alt="instagram logo"
                        src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e7/Instagram_logo_2016.svg/2048px-Instagram_logo_2016.svg.png"
                    /></a
                >
                <a href="https://www.twitch.tv/">
                    <img
                        alt="linkedin logo"
                        src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/LinkedIn_logo_initials.png/800px-LinkedIn_logo_initials.png"
                    /></a
                >
            </div>
        </div>
    </footer>
</div>

<style>
 footer{
	bottom:0; left:0; right:0;
    position:relative;
    padding: 50px 0px;
 }
	.logo {
		padding-top: 0.5%;
		display: flex;
		flex-direction: row;
		gap: 50px;
	}

	.feur {
		
		width: 80%;
		border-top: 2.5px solid rgba(0, 0, 0, 0.44);
	}
	img {
		border-radius: 50%;
		width: 50px;
		height: 50px;
	}

	.CDG {
		align-items: flex-end;
		display: flex;
		flex-direction: row;
		gap: 30px;
	}

	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 12px;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}
</style>
