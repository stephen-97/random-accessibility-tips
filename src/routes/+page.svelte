<script lang="ts">
	import Wysiwyg from "$lib/components/Wysiwyg.svelte";

	const html = `
		<h2>Pourquoi utiliser l'attribut <code>role</code> ?</h2>

		<p>
			L'attribut <strong>role</strong> fait partie des spécifications ARIA. Il permet
			de donner une signification sémantique à un élément pour les technologies
			d'assistance comme les lecteurs d'écran.
		</p>

		<p>
			Quand la sémantique HTML ne suffit pas, <code>role</code> permet d'expliquer
			la fonction réelle d'un élément dans l'interface.
		</p>

		<h3>Exemple simple</h3>

		<p>
			Voici un élément <code>div</code> qui agit comme un bouton. Sans sémantique,
			un lecteur d'écran ne comprendra pas son rôle.
		</p>

		<pre><code class="language-html">
&lt;div role="button" tabindex="0"&gt;
  Ouvrir le menu
&lt;/div&gt;
		</code></pre>

		<h3>Pourquoi c'est important</h3>

		<ul>
			<li>Améliore l'accessibilité des interfaces</li>
			<li>Aide les lecteurs d'écran à comprendre l'interface</li>
			<li>Clarifie le rôle des éléments non sémantiques</li>
		</ul>

		<h3>Bonnes pratiques</h3>

		<p>
			Il est généralement préférable d'utiliser les éléments HTML natifs avant
			d'ajouter un <code>role</code>.
		</p>

		<pre><code class="language-html">
&lt;button&gt;Ouvrir le menu&lt;/button&gt;
		</code></pre>

		<p>
			Les éléments natifs sont déjà accessibles et nécessitent moins de code.
		</p>
	`;
</script>

<section class="w-full max-w-xl flex flex-col">
	<h1 class="text-4xl font-bold mb-8">
		Conseils d'accesibilité aléatoire
	</h1>

	<button
		type="button"
		on:click={() => console.log('tiep')}
		class="mx-auto px-4 py-2 bg-black text-white rounded-md hover:bg-gray-800 transition cursor-pointer"
	>
		Générer
	</button>

	<Wysiwyg {html} />
</section>