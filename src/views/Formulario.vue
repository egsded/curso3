<template>
	<div class="mt-5">
		<h1>Formularios</h1>
		<form>
			<b-row>
				<b-col md="3">		
					<b-form-input type="text" v-model="texto" :state="comprobar"></b-form-input>
					<small>mínimo 3 caracteres</small>
				</b-col>
				<b-col md="3">
					<b-form-select v-model="select" :options="animales"></b-form-select>
					<p>Selección: {{select}}</p>
				</b-col>
				<b-col md="3">
					<b-form-radio-group v-model="radio" :options="animalesradio"></b-form-radio-group>
					<p>Radio: {{radio}}</p>
				</b-col>
				<b-col md="3">
					<b-form-checkbox-group v-model="check" :options="animalesradio"></b-form-checkbox-group>
					<p>Check: {{check}}</p>
				</b-col>
			</b-row>
		</form>
		<p>texto: {{texto}}</p>
	</div>
</template>
<script>
	export default{
		name: 'Formulario',
		data(){
			return{
				texto: "",
				radio: null,
				check:[],
				select: null,
				animales:[
				{value: null, text:'seleccione un animal'},
				{value: 'perro', text:'guau guau'},
				{value: 'gato', text:'miau'},
				{value: 'pato', text:'cuack'},
				],
				animalesradio:[
				{value: 'perro', text:'guau guau'},
				{value: 'gato', text:'miau'},
				{value: 'pato', text:'cuack'},
				]
			}
		},
		computed:{
			comprobar(){
				return this.texto.length > 2 ? true : false
			}
		}
	}
</script>