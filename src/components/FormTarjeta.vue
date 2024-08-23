<script>
export default {
    name: 'FormTarjeta',
    data() {
        return {
            tituloTarjeta: '',
            chipSrc: '../../public/chip.png',
            numeroTarjeta: '',
            fechaExpiracion: '',
            propietario: '',
            tarjetaSeleccionada:'Visa',
            tipoTarjetaSrc: {
                'Visa':'../../public/visa.png',
                'Mastercard':'../../public/mastercard.png',
            },
        }
    }
}
</script>
<template>
    <div id="app">
        <form>
            <div>
                <label>Título de la tarjeta: </label>
                <input v-model="tituloTarjeta" />
            </div>

            <div>
                <label>Chip SRC: </label>
                <input v-model="chipSrc" />
            </div>

            <div>
                <label>Número: </label>
                <input v-model="numeroTarjeta" />
            </div>

            <div>
                <label for="fecha">Fecha de expiración: </label>
                <!-- Esto funciona para chrome, no funciona pa mozilla-->
                <input v-model="fechaExpiracion" type="month" name="fecha"/>
            </div>

            <div>
                <label>Propietario: </label>
                <input v-model="propietario" />
            </div>

            <div>
                <label>Tipo de tarjeta SRC: </label>
                <select v-model="tarjetaSeleccionada" id="">
                    <option value="Visa">Visa</option>
                    <option value="Mastercard">Mastercard</option>
                </select>
                <!-- <input v-model="tipoTarjetaSrc" /> -->
            </div>
        </form>

        <div class="carnet">
            <h3>{{ tituloTarjeta }}</h3>
            <img width="40" v-bind:src=chipSrc alt="" />
            <div>
                <h2>{{ numeroTarjeta }}</h2>
                <span>Fecha Exp: <b>{{ fechaExpiracion }}</b></span>
            </div>
            <footer>
                <span>{{ propietario }}</span>
                <img v-bind:src=tipoTarjetaSrc[tarjetaSeleccionada] width="60" />
            </footer>
        </div>
    </div>
</template>
<style scoped></style>