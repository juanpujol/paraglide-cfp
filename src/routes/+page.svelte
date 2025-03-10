<script lang="ts">
	import { page } from '$app/state';
	import { goto } from '$app/navigation';
	import * as m from '$lib/paraglide/messages.js';
	import { setLocale } from '$lib/paraglide/runtime';

	function switchToLanguage(newLanguage: string) {
		if (!['en', 'pt-br'].includes(newLanguage)) {
			throw new Error(`Invalid language: ${newLanguage}`);
		}

		setLocale(newLanguage as 'en' | 'pt-br');
	}
</script>

<h1>{m.hello_world({ name: 'SvelteKit User' })}</h1>
<div>
	<button onclick={() => switchToLanguage('en')}>en</button>
	<button onclick={() => switchToLanguage('pt-br')}>pt-br</button>
</div>
