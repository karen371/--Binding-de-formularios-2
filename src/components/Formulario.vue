<script>
export default {
    name: "Formulario",
    data() {
        return {
            formulario: {
                titulo: '',
                emoji: '',
                apreciacion: '',
                competencias: [],
                opinion: ''
            }
        };
    },
    methods: {
        emitData() {
            console.log(this.formulario);
            this.$emit('datos-actualizados', { ...this.formulario });
        }
    }
};
</script>

<template>
    <form>
        <div class="formulario-c">
            <span>Titulo</span>
            <input v-model="formulario.titulo" @input="emitData" />
        </div>
        <div class="formulario-c">
            <span>Emoji</span>
            <select v-model="formulario.emoji" @change="emitData">
                <option disabled value="">seleccione</option>
                <option>💻</option>
                <option>🧑‍💻</option>
                <option>🖥️</option>
            </select>
        </div>
        <div class="formulario-campo">
            <span>Apreciación</span>
            <input type="radio" id="regular" value="Regular" v-model="formulario.apreciacion" @change="emitData" />
            <label for="regular">Regular</label>
            <input type="radio" id="bien" value="Bien" v-model="formulario.apreciacion" @change="emitData" />
            <label for="bien">Bien</label>
            <input type="radio" id="muyBien" value="Muy Bien" v-model="formulario.apreciacion" @change="emitData" />
            <label for="muyBien">Muy Bien</label>
            <input type="radio" id="increible" value="Increible" v-model="formulario.apreciacion" @change="emitData" />
            <label for="increible">Increible</label>
        </div>
        <div class="formulario-campo">
            <span>Competencias</span>
            <input type="checkbox" id="MC" value="Morfología de un componente" v-model="formulario.competencias" @change="emitData"/>
            <label for="MC">Morfología de un componente</label>
            
            <input type="checkbox" id="ot" value="One-way y Two-Way data binding" v-model="formulario.competencias" @change="emitData"/>
            <label for="ot">One-way y Two-Way data binding</label>
            
            <input type="checkbox" id="MV" value="El patrón de diseño MVVM" v-model="formulario.competencias" @change="emitData"/>
            <label for="MV">El patrón de diseño MVVM</label>
            
            <input type="checkbox" id="directivas" value="Directivas" v-model="formulario.competencias" @change="emitData"/>
            <label for="directivas">Directivas</label>
            
            <input type="checkbox" id="estado" value="Estado" v-model="formulario.competencias" @change="emitData"/>
            <label for="estado">Estado</label>
        </div>
        <div class="formulario-c">
            <span>Opinión:</span>
            <textarea v-model="formulario.opinion" @input="emitData"></textarea>
        </div>
    </form>
</template>

<style>
form {
    width: 50%;
    margin: 0 auto; /* Centrar el formulario */
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    background-color: #222; /* Fondo más suave */
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3); /* Sombra para dar profundidad */
}

.formulario-c {
    display: flex;
    margin-bottom: 20px; /* Espacio entre los campos */
    gap: 10px;
}

.formulario-campo {
    display: flex;
    justify-content: space-around;
    margin-bottom: 20px; /* Espacio entre los campos */
    gap: 10px;
}

.formulario-campo span {
    font-size: 16px;
    color: #fff;
    margin-bottom: 8px; /* Espacio entre el label y el input */
}

.formulario-c input,
.formulario-campo select,
.formulario-campo textarea {
    padding: 8px;
    border: 1px solid #444;
    background-color: #333;
    color: #fff;
    border-radius: 4px;
    font-size: 14px;
}

.formulario-campo input[type="radio"],
.formulario-campo input[type="checkbox"] {
    width: auto; /* Permitir tamaño automático para radio y checkbox */
}

.formulario-campo label {
    color: #fff;
    margin-left: 8px;
}

textarea {
    resize: vertical; /* Permitir solo redimensionar verticalmente */
    height: 80px;
    width: 500px;
}

input:focus,
select:focus,
textarea:focus {
    outline: none;
    border-color: #555;
    box-shadow: 0 0 5px rgba(255, 255, 255, 0.5);
}

</style>