<script lang="ts">
	import { useThrelte, useRender } from '@threlte/core';
	import {
		EffectComposer,
		EffectPass,
		RenderPass,
		SMAAEffect,
		SMAAPreset,
		BloomEffect,
		KernelSize
	} from 'postprocessing';
	import type { Camera } from 'three';
	const { scene, renderer, camera, size } = useThrelte();
	const composer = new EffectComposer(renderer);
	const setupEffectComposer = (camera: Camera) => {
		composer.removeAllPasses();
		composer.addPass(new RenderPass(scene, camera));
	};
	$: setupEffectComposer($camera);
	$: composer.setSize($size.width, $size.height);
	useRender((_, delta) => {
		composer.render(delta);
	});
</script>
