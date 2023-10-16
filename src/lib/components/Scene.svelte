<script lang="ts">
	import { T } from '@threlte/core';
	import { ContactShadows, Float, Grid, OrbitControls } from '@threlte/extras';
	import Peirene from './models/peirene.svelte';
</script>

<T.PerspectiveCamera makeDefault position={[-15, 15, 15]} fov={15}>
	<OrbitControls autoRotate enableDamping autoRotateSpeed={0.1} target.x={-5} target.y={1.5} />
</T.PerspectiveCamera>

<T.DirectionalLight intensity={1.8} position.x={5} position.y={10} />
<T.AmbientLight intensity={0.7} />

<Float floatIntensity={1} floatingRange={[0, 1]}>
	<T.Mesh position.y={1.2} position.z={-0.75}>
		<T.BoxGeometry />
		<T.MeshStandardMaterial color="#0059BA" />
	</T.Mesh>
</Float>

<Peirene />

<T.Group position.x={-5} position.y={-3} position.z={-3}>
	<Float floatIntensity={1} floatingRange={[0, 1]}>
		<T.Mesh position={[1.2, 1.5, 0.75]} rotation.x={5} rotation.y={71}>
			<T.TorusKnotGeometry args={[0.5, 0.15, 100, 12, 2, 3]} />
			<T.MeshStandardMaterial color="#F85122" />
		</T.Mesh>
	</Float>

	<Float floatIntensity={1} floatingRange={[0, 1]}>
		<T.Mesh position={[-1.4, 1.5, 0.75]} rotation={[-5, 128, 10]}>
			<T.IcosahedronGeometry />
			<T.MeshStandardMaterial color="#F8EBCE" />
		</T.Mesh>
	</Float>
</T.Group>
