<Menu/>
<script>
  import "../../app.css";
  import Menu from '$lib/Menu.svelte';
  let coderMessage = '';
  let keyEncode = 0;

  function decodeCesar(str, shift) {
      return str.replace(/[a-zA-Z]/g, c => String.fromCharCode(c.charCodeAt(0) - shift));
  }

  $: messagedecoder = decodeCesar(coderMessage, keyEncode);
</script>

<div class="flex flex-col items-center min-h-screen bg-gray-200 p-20 justify-center">
  <h1 class="pb-10 text-4xl font-bold">Cesar Decoder</h1>
  
  <h1>Votre Message :</h1>
  <textarea class="border rounded shadow mb-4 p-2 w-full max-w-lg" bind:value={coderMessage} placeholder="décoder ici"></textarea>
  
  <h2>Clé d'encodage :</h2>
  <input class="border rounded shadow mb-4 p-2 w-full max-w-lg" type="number" bind:value={keyEncode} placeholder="Shift">
  
  <h2>Votre message décodé :</h2>
  <div class="w-full max-w-lg p-4 border rounded shadow bg-white">{messagedecoder}</div>
</div>
