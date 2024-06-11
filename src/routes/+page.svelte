<Menu/>
<script>
  import "../app.css";
	import Menu from '$lib/Menu.svelte'
	let messageCoder = '';
  let keyEncode = 0;
  function codeCesar(str, shift) {
      return str.replace(/[a-zA-Z]/g, c => String.fromCharCode(c.charCodeAt(0) + shift));
  }

  $: message = codeCesar(messageCoder, keyEncode);
</script>

<div class="flex flex-col items-center min-h-screen bg-gray-200 p-20 justify-center">
<h1 class="pb-10">Cesar Encoder </h1>

<h1>Votre Message :</h1>
<textarea class="border rounded shadow mb-4 p-2 w-full max-w-lg" bind:value={messageCoder} placeholder="coder ici"></textarea>

<h1>Clé d'encodage :</h1>
<input class="border rounded shadow mb-4 p-2 w-full max-w-lg"type="number" bind:value={keyEncode}>

<h1>Votre message encodé :</h1>
<div class="w-full max-w-lg p-4 border rounded shadow bg-white">{message}</div>

</div>