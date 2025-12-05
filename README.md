# Proyecto-Hackathon-TCG-Ilustrated
Sistema para vincular sobre o productos sellados de trading card games o TCG,  añadiendo un UID único a cada producto con el cual se tiene acceso a un NFT que valida la posesión del producto, esto con el objetivo de garantizar que el producto sea legitimo y no se encuentre intervenido, así como añadir un segundo valor añadido de coleccionismo.

# Tecnologías Utilizadas

HTML5 / CSS3 / JavaScript – Construcción de la interfaz y lógica del lado del cliente.

Ethers.js (v5.7.2) – Interacción con el contrato inteligente, provider, signer y envío de transacciones.

MetaMask – Proveedor de cuentas y conexión Web3 a través de window.ethereum.

Avalanche Fuji Testnet – Red blockchain donde se encuentra desplegado el contrato.

# Integración Web3

La aplicación establece la conexión con MetaMask y la red Fuji empleando las siguientes APIs:

eth_requestAccounts – Solicita acceso a las cuentas del usuario.

wallet_switchEthereumChain – Cambia automáticamente a Avalanche Fuji si el usuario no está en la red correcta.

wallet_addEthereumChain – Agrega la red Fuji a MetaMask si no existe en la configuración del usuario.

Una vez establecida la conexión, la app crea:

Un Web3Provider a partir de window.ethereum.

Un signer para firmar transacciones.

Una instancia del contrato inteligente utilizando su dirección y ABI.

# Funciones del Contrato Integradas

El frontend interactúa con un contrato inteligente que expone tres funciones:

registerPack(uint256 id) – Registra un nuevo sobre.

verifyPack(uint256 id) – Consulta si un sobre existe o está registrado.

openPack(uint256 id) – Abre un sobre previamente registrado.

La aplicación implementa validaciones previas para evitar transacciones innecesarias, tales como verificar si el pack ya está registrado antes de intentar abrirlo o registrarlo.

# Interfaz

La interfaz está construida en HTML y estilizada con CSS, incorporando animaciones suaves y un diseño moderno.
Incluye:

Input para ingresar el ID del pack.

Botones para conectar MetaMask, registrar, verificar y abrir packs.

Mensajes dinámicos para mostrar resultados, errores o estados de transacción.

# Manejo de Errores

El sistema captura y muestra errores comunes durante la interacción con MetaMask o la blockchain, incluyendo:

Rechazo de transacciones.

Contrato no desplegado en la red seleccionada.

Errores tipo CALL_EXCEPTION.

Fallas en la conexión con MetaMask o funciones no soportadas.

# Flujo General de Uso

El usuario abre la aplicación y conecta MetaMask.

Si no está en Fuji, la app solicita cambiar o agregar la red.

El usuario ingresa el ID del sobre.

Puede elegir entre registrar, verificar o abrir el pack.

La aplicación interactúa con el contrato y muestra los resultados.

# Objetivo del Proyecto

PackGuard busca demostrar una integración simple y eficiente entre un frontend web tradicional y un smart contract en Avalanche, ofreciendo una experiencia completa de interacción Web3 sin dependencias innecesarias ni complejidad adicional.

# Instrucciones de Uso

## Cómo Ejecutar la Aplicación

### Paso 1: Iniciar el Servidor Local

Abre una terminal en la carpeta del proyecto y ejecuta:

python -m http.server 8000

Verás un mensaje como este:

Serving HTTP on :: port 8000 (http://[::]:8000/) ...


### Paso 2: Abrir en el Navegador DONDE TIENES EL PLUGIN CARGADO

Abre tu navegador y visita:

http://localhost:8000**
