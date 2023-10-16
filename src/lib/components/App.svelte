<script lang="ts">
	import { Canvas } from '@threlte/core';
	import Scene from './Scene.svelte';
	import Renderer from './renderer/Renderer.svelte';
</script>

<Canvas>
	<Scene />
	<Renderer />
</Canvas>
