<script lang="ts">
	import { T as Threlte } from '@threlte/core';
	import * as THREE from 'three';
	import Geometry from './Geometry.svelte';
	import { ContactShadows, Environment, interactivity, transitions } from '@threlte/extras';

	interactivity();
	transitions();
</script>

<Threlte.PerspectiveCamera
	makeDefault
	position={[0, 0, 25]}
	aspect={1}
	fov={30}
	near={1}
	far={40}
/>

<Environment files="smallroom.hdr" path="/" format="hdr" />

<!-- Basically where is the ground -->
<ContactShadows position={[0, -3.5, 0]} opacity={0.65} scale={40} blue={1} far={9}></ContactShadows>

<!-- Geometry -->
<Geometry position={[0, 0, 0]} rate={0.3} geometry={new THREE.IcosahedronGeometry(3)} />

<!-- pill -->
<Geometry
	position={[1, -0.75, 4]}
	rate={0.4}
	geometry={new THREE.CapsuleGeometry(0.5, 1.6, 2, 16)}
/>

<!-- ball -->
<Geometry position={[-1.4, 2, -4]} rate={0.6} geometry={new THREE.DodecahedronGeometry(1.5)} />

<!-- donut -->
<Geometry
	position={[-0.8, -0.75, 5]}
	rate={0.5}
	geometry={new THREE.TorusGeometry(0.6, 0.25, 16, 32)}
/>

<!-- diamong -->
<Geometry position={[1.6, 1.6, -4]} rate={0.7} geometry={new THREE.OctahedronGeometry(1.5)} />
