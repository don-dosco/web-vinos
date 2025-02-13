<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Don Dosco - Tienda de Vinos Mendocinos</title>
    <style>
        /* Estilos Generales */
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        /* Header */
        header {
            background-color: #800020; /* Color Bordó */
            color: white;
            padding: 20px 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        /* Logo */
        .logo {
            margin-left: 20px;
            width: 150px;
            height: auto;
        }

        /* Navegación */
        nav ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
        }

        nav ul li {
            margin: 0 15px;
        }

        nav ul li a {
            color: white;
            text-decoration: none;
            font-size: 1.1rem;
            transition: color 0.3s;
        }

        nav ul li a:hover {
            color: #f39c12;
        }

        /* Carrito */
        .carrito {
            margin-right: 20px;
            display: flex;
            align-items: center;
        }

        .carrito img {
            width: 30px;
            height: auto;
        }

        .carrito p {
            color: white;
            margin-left: 10px;
            font-size: 1.1rem;
        }

        /* Slider Principal */
        #slider {
            width: 100%;
            overflow: hidden;
            position: relative;
            max-height: 500px;
        }

        #slider img {
            width: 100%;
            height: auto;
            display: none;
            position: absolute;
            top: 0;
            left: 0;
        }

        #slider img.active {
            display: block;
        }

        /* Secciones */
        .section {
            padding: 40px 20px;
            background-color: #fff;
            display: none; /* Ocultar secciones inicialmente */
        }

        .section.active {
            display: block; /* Mostrar la sección activa */
        }

        /* Títulos de secciones */
        h2 {
            text-align: center;
            font-size: 2rem;
            margin-bottom: 40px;
        }

        /* Diseño de productos */
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            justify-items: center;
        }

        .product {
            background-color: #fff;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            text-align: center;
            max-width: 250px;
            position: relative;
        }

        .product:hover {
            transform: translateY(-10px);
            box-shadow: 0 6px 16px rgba(0, 0, 0, 0.2);
        }

        .product img {
            width: 100%;
            border-bottom: 1px solid #f4f4f4;
            transition: transform 0.3s ease;
        }

        .product:hover img {
            transform: scale(1.05);
        }

        .product h3 {
            font-size: 1.2rem;
            margin: 15px 0;
        }

        .product p {
            font-size: 1rem;
            color: #2c3e50;
        }

        .hover-info {
            display: none;
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background-color: rgba(0, 0, 0, 0.8);
            color: white;
            padding: 10px;
            font-size: 0.9rem;
        }

        .product:hover .hover-info {
            display: block;
        }

        button {
            background-color: #800020;
            color: white;
            border: none;
            padding: 10px 20px;
            cursor: pointer;
            border-radius: 5px;
            transition: background-color 0.3s ease;
            font-size: 1rem;
        }

        button:hover {
            background-color: #a00000;
        }

        /* Modal para Descripción de Vino */
        .modal {
            display: none;
            position: fixed;
            z-index: 1;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            max-width: 400px;
            width: 80%;
        }

        .modal-content h3 {
            margin-top: 0;
        }

        .close {
            color: #800020;
            float: right;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Footer */
        footer {
            background-color: #800020;
            color: white;
            text-align: center;
            padding: 20px 0;
            margin-top: 50px;
        }

        footer p {
            margin: 0;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .product-grid {
                grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            }

            .modal-content {
                width: 90%;
            }
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header>
        <div>
            <img src="potos/jj.png" alt="Logo de Viñedos Don Dosco" class="logo">
        </div>
        <nav>
            <ul>
                <li><a href="#vinos" onclick="showSection('vinos')">Vinos</a></li>
                <li><a href="#promociones" onclick="showSection('promociones')">Promociones</a></li>
                <li><a href="#contacto" onclick="showSection('contacto')">Contacto</a></li>
            </ul>
        </nav>
        <div class="carrito">
            <img src="imagenes/icono-carrito.png" alt="Carrito">
            <p id="cart-count">0</p>
        </div>
    </header>

    <!-- Slider Principal -->
    <section id="slider">
        <img src="potos/valle.jpeg" alt="Viñedos de Mendoza" class="active">
        <img src="potos/bodega 3.jpeg" alt="Barricas de Vino">
        <img src="potos/promocion.jpeg" alt="Botellas de Vino">
    </section>

    <!-- Secciones -->
    <section id="vinos" class="section active">
        <h2>Vinos Destacados</h2>
        <div class="product-grid">
            <div class="product" data-price="2000">
                <img src="potos/caja3.jpeg" alt="Vino Malbec">
                <h3>Vino Malbec</h3>
                <p>$2000</p>
                <div class="hover-info">un vino ideal para el verano.</div>
                <button onclick="addToCart('Vino Malbec', 2000)">Comprar</button>
                <p class="description" style="display:none;">Descripción: Vino Blend con notas de frutas y especias.</p>
            </div>
            <div class="product" data-price="80000">
                <img src="potos/vino2.jpeg" alt="Vino Cabernet Sauvignon">
                <h3>Vino Cabernet Sauvignon</h3>
                <p>$80000</p>
                <div class="hover-info">Un vino intenso, ideal para carnes rojas.</div>
                <button onclick="addToCart('Cabernet Sauvignon', 80000)">Comprar</button>
                <p class="description" style="display:none;">Descripción: Vino Blend con notas de frutas y especias.</p>
            </div>
            <div class="product" data-price="2200">
                <img src="potos/caja5.jpeg" alt="Vino Blend">
                <h3>Vino Blend</h3>
                <p>$2200</p>
                <div class="hover-info">Un ensamblaje perfecto de uvas seleccionadas.</div>
                <button onclick="addToCart('Vino Blend', 2200)">Comprar</button>
                <p class="description" style="display:none;">Descripción: Vino Blend con notas de frutas y especias.</p>
            </div>
        </div>
    </section>

    <section id="promociones" class="section">
        <h2>Promociones Especiales</h2>
        <div class="product-grid">
            <div class="product" data-price="10000">
                <img src="potos/promocion.jpeg" alt="dos vinos de la mayor calidad">
                <h3>Vino Rosado</h3>
                <p>$10000</p>
                <div class="hover-info">Un dos vinos frescos y afrutados, ideal para el verano.</div>
                <button onclick="addToCart('Vino Rosado', 10000)">Comprar</button>
                <p class="description" style="display:none;">Descripción: Vino rosado con notas de fresas y frambuesas.</p>
            </div>
            <div class="product" data-price="1600">
                <img src="potos/vino botella.jpeg" alt="Vino Malbec Reserva">
                <h3>Vino Malbec Reserva</h3>
                <p>$1600</p>
                <div class="hover-info">Un Malbec con cuerpo, perfecto para carnes asadas.</div>
                <button onclick="addToCart('Malbec Reserva', 1600)">Comprar</button>
                <p class="description" style="display:none;">Descripción: Vino Malbec con un año de barrica, ideal para ocasiones especiales.</p>
            </div>
            <div class="product" data-price="1500">
                <img src="potos/pack.jpeg" alt="Vino Cabernet Franc">
                <h3>Vino Cabernet Franc</h3>
                <p>$1500</p>
                <div class="hover-info">Un vino elegante, con notas herbales y especiadas.</div>
                <button onclick="addToCart('Cabernet Franc', 1500)">Comprar</button>
                <p class="description" style="display:none;">Descripción: Vino Cabernet Franc, ideal para acompañar quesos fuertes.</p>
            </div>
        </div>
    </section>

    <section id="contacto" class="section">
        <h2>Contacto</h2>
        <p>Si tienes alguna consulta, por favor envíanos un correo a <a href="mailto:tuemail@gmail.com">familiadondosco@gmail.com</a>.</p>
    </section>

    <!-- Modal para Descripción de Vino -->
    <div id="modal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal()">&times;</span>
            <h3 id="modal-title"></h3>
            <p id="modal-description"></p>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <p>&copy; 2024 Viñedos Don Dosco. Todos los derechos reservados.</p>
    </footer>

    <script>
        // Funciones de JavaScript
        let currentIndex = 0;
        const slides = document.querySelectorAll('#slider img');
        const totalSlides = slides.length;

        function showSlides() {
            slides.forEach((slide, index) => {
                slide.classList.remove('active');
                if (index === currentIndex) {
                    slide.classList.add('active');
                }
            });
            currentIndex = (currentIndex + 1) % totalSlides;
        }

        setInterval(showSlides, 3000); // Cambia de imagen cada 3 segundos

        function showSection(sectionId) {
            document.querySelectorAll('.section').forEach(section => {
                section.classList.remove('active');
            });
            document.getElementById(sectionId).classList.add('active');
        }

        function addToCart(productName, productPrice) {
            alert(`Has agregado ${productName} al carrito por $${productPrice}.`);
            const cartCount = document.getElementById('cart-count');
            cartCount.textContent = parseInt(cartCount.textContent) + 1;
        }

        function openModal(title, description) {
            document.getElementById('modal-title').textContent = title;
            document.getElementById('modal-description').textContent = description;
            document.getElementById('modal').style.display = 'flex';
        }

        function closeModal() {
            document.getElementById('modal').style.display = 'none';
        }
    </script>
</body>
</html>
