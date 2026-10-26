<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Misión Eco-Reto</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #f3f8fa;
    color: #254653;
}

header {
    background: #176b75;
    color: white;
    padding: 20px 5%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
}

.logo {
    display: flex;
    align-items: center;
    gap: 12px;
}

.logo img {
    width: 65px;
    height: 65px;
    border-radius: 50%;
    object-fit: cover;
    border: 3px solid #b9eee2;
}

header h1 { margin: 0; }
header p { margin-bottom: 0; color: #d5f5ed; }

button {
    border: none;
    border-radius: 20px;
    padding: 12px 18px;
    cursor: pointer;
    background: #20a58e;
    color: white;
    font-weight: bold;
    margin: 3px;
    transition: .3s;
}

button:hover {
    background: #147966;
    transform: translateY(-2px);
}

.hero {
    padding: 40px 5%;
    display: flex;
    align-items: center;
    gap: 30px;
    background: #d9f1ef;
}

.hero div { flex: 1; }

.hero h2 {
    font-size: 34px;
    color: #176b75;
}

.hero img {
    width: 45%;
    height: 280px;
    object-fit: cover;
    border-radius: 25px;
    box-shadow: 0 5px 15px #176b7530;
}

main { padding: 25px 5%; }

h2 { color: #176b75; }

.estadisticas, .galeria {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 18px;
}

.tarjeta {
    background: white;
    padding: 22px;
    border-radius: 20px;
    text-align: center;
    box-shadow: 0 4px 14px #176b7515;
    border-bottom: 4px solid #65cbb6;
    transition: .3s;
}

.tarjeta:hover { transform: translateY(-5px); }

.tarjeta img {
    width: 60px;
    height: 60px;
    object-fit: contain;
}

.tarjeta strong {
    display: block;
    font-size: 27px;
    color: #20a58e;
    margin: 8px;
}

.galeria article {
    background: white;
    border-radius: 18px;
    overflow: hidden;
    box-shadow: 0 4px 14px #176b7515;
    transition: .3s;
}

.galeria article:hover { transform: translateY(-4px); }

.galeria img {
    width: 100%;
    height: 165px;
    object-fit: cover;
}

.galeria h3, .galeria p { padding: 0 12px; }

.galeria h3 { color: #176b75; }

.galeria p {
    line-height: 1.5;
    color: #587078;
}

.panel {
    background: white;
    padding: 25px;
    border-radius: 20px;
    margin-top: 25px;
    box-shadow: 0 4px 14px #176b7515;
}

label {
    display: block;
    font-weight: bold;
    margin: 12px 0 6px;
    color: #176b75;
}

input, select, textarea {
    width: 100%;
    padding: 12px;
    border: 1px solid #b9dcd8;
    border-radius: 10px;
    font: inherit;
    background: #f8fcfc;
    color: #254653;
}

input:focus, select:focus, textarea:focus {
    outline: 2px solid #65cbb6;
    border-color: #20a58e;
}

textarea { min-height: 80px; }

table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 15px;
    min-width: 650px;
}

th, td {
    padding: 12px;
    border: 1px solid #dcebea;
    text-align: left;
}

th {
    background: #d9f1ef;
    color: #176b75;
}

tr:nth-child(even) { background: #f5fbfa; }

.tabla { overflow-x: auto; }

.editar { background: #3288b8; }
.eliminar { background: #dc6666; }

footer {
    text-align: center;
    padding: 24px;
    background: #14545e;
    color: white;
    margin-top: 25px;
}

@media (max-width: 750px) {
    .hero { flex-direction: column; }
    .hero img { width: 100%; }

    .estadisticas, .galeria {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 450px) {
    .estadisticas, .galeria {
        grid-template-columns: 1fr;
    }
}
</style>
</head>

<body>

<header>
    <div class="logo">
        <img src="https://images.unsplash.com/photo-1470071459604-3b5ec3a7fe05?auto=format&fit=crop&w=150&q=80" alt="Naturaleza">
        <div>
            <h1>🌿 Misión Eco-Reto</h1>
            <p>Pequeñas acciones, grandes cambios</p>
        </div>
    </div>
    <button onclick="irRegistro()">＋ Nueva acción</button>
</header>

<section class="hero">
    <div>
        <h2>¡Bienvenido a Misión Eco-Reto!</h2>
        <p>Registra tus acciones ecológicas y descubre cómo tus pequeños hábitos pueden ayudar al planeta.</p>
        <button onclick="irRegistro()">Comenzar mi reto 🌱</button>
    </div>
    <img src="https://images.unsplash.com/photo-1441974231531-c6227db76b6e?auto=format&fit=crop&w=900&q=80" alt="Bosque verde">
</section>

<main>

<h2>📊 Mi impacto ecológico</h2>

<section class="estadisticas">
    <div class="tarjeta">
        <img src="https://img.icons8.com/color/96/leaf.png" alt="Hoja">
        <strong id="total">0</strong>
        Acciones registradas
    </div>

    <div class="tarjeta">
        <img src="https://img.icons8.com/color/96/water.png" alt="Agua">
        <strong id="agua">0 L</strong>
        Agua ahorrada
    </div>

    <div class="tarjeta">
        <img src="https://img.icons8.com/color/96/recycle.png" alt="Reciclaje">
        <strong id="reciclaje">0 kg</strong>
        Material reciclado
    </div>

    <div class="tarjeta">
        <img src="https://img.icons8.com/color/96/deciduous-tree.png" alt="Árbol">
        <strong id="plantas">0</strong>
        Plantas registradas
    </div>
</section>

<h2 style="margin-top:32px;">🌱 Explora los eco-retos</h2>

<section class="galeria">
    <article>
        <img src="https://images.unsplash.com/photo-1532996122724-e3c354a0b15b?auto=format&fit=crop&w=500&q=80" alt="Reciclaje">
        <h3>♻️ Reciclaje</h3>
        <p>Separa los residuos y reutiliza materiales para reducir la contaminación.</p>
    </article>

    <article>
        <img src="https://images.unsplash.com/photo-1437482078695-73f5ca6c96e2?auto=format&fit=crop&w=500&q=80" alt="Agua">
        <h3>💧 Ahorro de agua</h3>
        <p>Cierra la llave y cuida cada gota de agua.</p>
    </article>

    <article>
        <img src="https://images.unsplash.com/photo-1416879595882-3373a0480b5b?auto=format&fit=crop&w=500&q=80" alt="Plantas">
        <h3>🌳 Reforestación</h3>
        <p>Planta y cuida árboles y plantas de tu comunidad.</p>
    </article>

    <article>
        <img src="https://images.unsplash.com/photo-1473341304170-971dccb5ac1e?auto=format&fit=crop&w=500&q=80" alt="Energía">
        <h3>⚡ Energía</h3>
        <p>Apaga las luces y desconecta aparatos que no utilices.</p>
    </article>
</section>

<section class="panel" id="registro">
    <h2>📝 Registrar una acción ecológica</h2>

    <form id="formulario">
        <label for="tipo">Tipo de acción</label>
        <select id="tipo" required>
            <option value="Reciclaje">♻️ Reciclaje</option>
            <option value="Ahorro de agua">💧 Ahorro de agua</option>
            <option value="Reforestación">🌳 Reforestación</option>
            <option value="Energía">⚡ Energía</option>
            <option value="Transporte">🚲 Transporte sostenible</option>
        </select>

        <label for="descripcion">Descripción</label>
        <textarea id="descripcion" placeholder="Ejemplo: Separé botellas de plástico" required></textarea>

        <label for="fecha">Fecha</label>
        <input type="date" id="fecha" required>

        <label for="cantidad">Cantidad del impacto</label>
        <input type="number" id="cantidad" min="0" step="any" value="1" required>

        <label for="unidad">Unidad</label>
        <select id="unidad">
            <option value="kg">Kilogramos (kg)</option>
            <option value="litros">Litros</option>
            <option value="plantas">Plantas</option>
            <option value="veces">Veces realizadas</option>
        </select>

        <br><br>
        <button type="submit" id="guardar">💚 Guardar acción</button>
        <button type="reset" style="background:#64756c">Limpiar</button>
    </form>
</section>

<section class="panel">
    <h2>📋 Mis acciones registradas</h2>

    <input id="buscar" placeholder="🔎 Buscar una acción...">

    <div class="tabla">
        <table>
            <thead>
                <tr>
                    <th>ID</th>
                    <th>Fecha</th>
                    <th>Tipo</th>
                    <th>Descripción</th>
                    <th>Impacto</th>
                    <th>Opciones</th>
                </tr>
            </thead>
            <tbody id="tabla"></tbody>
        </table>
    </div>

    <p id="vacio">Todavía no hay acciones registradas. ¡Agrega la primera! 🌱</p>
</section>

</main>

<footer>
    🌎 Misión Eco-Reto | ¡Juntos podemos cuidar nuestro planeta!
</footer>

<script>
let acciones = [];
let siguienteId = 1;
let editando = null;

const $ = id => document.getElementById(id);

$("fecha").value = new Date().toLocaleDateString("en-CA");

function irRegistro() {
    $("registro").scrollIntoView({ behavior: "smooth" });
}

$("formulario").addEventListener("submit", function(e) {
    e.preventDefault();

    const accion = {
        id: editando === null ? siguienteId++ : editando,
        tipo: $("tipo").value,
        descripcion: $("descripcion").value.trim(),
        fecha: $("fecha").value,
        cantidad: Number($("cantidad").value),
        unidad: $("unidad").value
    };

    if (!accion.descripcion || !accion.fecha ||
        !Number.isFinite(accion.cantidad) ||
        accion.cantidad < 0) {
        alert("Revisa los datos del formulario.");
        return;
    }

    if (editando === null) {
        acciones.push(accion);
    } else {
        const indice = acciones.findIndex(a => a.id === editando);
        if (indice !== -1) acciones[indice] = accion;
    }

    editando = null;
    $("formulario").reset();
    $("fecha").value = new Date().toLocaleDateString("en-CA");
    $("guardar").textContent = "💚 Guardar acción";

    actualizar();
});

$("buscar").addEventListener("input", actualizar);

function actualizar() {
    const tabla = $("tabla");
    tabla.replaceChildren();

    const texto = $("buscar").value.toLowerCase();

    const lista = acciones.filter(a =>
        (a.tipo + " " + a.descripcion + " " + a.fecha)
        .toLowerCase().includes(texto)
    );

    lista.forEach(a => {
        const fila = document.createElement("tr");

        [a.id, a.fecha, a.tipo, a.descripcion,
         a.cantidad + " " + a.unidad].forEach(valor => {
            const celda = document.createElement("td");
            celda.textContent = valor;
            fila.appendChild(celda);
        });

        const opciones = document.createElement("td");

        const editar = document.createElement("button");
        editar.textContent = "✏️ Editar";
        editar.className = "editar";
        editar.onclick = () => editarAccion(a.id);

        const borrar = document.createElement("button");
        borrar.textContent = "🗑️ Eliminar";
        borrar.className = "eliminar";
        borrar.onclick = () => eliminarAccion(a.id);

        opciones.append(editar, borrar);
        fila.appendChild(opciones);
        tabla.appendChild(fila);
    });

    $("vacio").hidden = lista.length > 0;
    $("total").textContent = acciones.length;

    $("agua").textContent =
        acciones.filter(a => a.tipo === "Ahorro de agua" &&
            a.unidad === "litros")
        .reduce((s, a) => s + a.cantidad, 0) + " L";

    $("reciclaje").textContent =
        acciones.filter(a => a.tipo === "Reciclaje" &&
            a.unidad === "kg")
        .reduce((s, a) => s + a.cantidad, 0) + " kg";

    $("plantas").textContent =
        acciones.filter(a => a.tipo === "Reforestación" &&
            a.unidad === "plantas")
        .reduce((s, a) => s + a.cantidad, 0);
}

function editarAccion(id) {
    const a = acciones.find(item => item.id === id);
    if (!a) return;

    editando = id;
    $("tipo").value = a.tipo;
    $("descripcion").value = a.descripcion;
    $("fecha").value = a.fecha;
    $("cantidad").value = a.cantidad;
    $("unidad").value = a.unidad;
    $("guardar").textContent = "💾 Actualizar acción";

    irRegistro();
}

function eliminarAccion(id) {
    if (confirm("¿Quieres eliminar esta acción?")) {
        acciones = acciones.filter(a => a.id !== id);
        actualizar();
    }
}
</script>

</body>
</html>