[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24064796&assignment_repo_type=AssignmentRepo)
# Lab04 - Visualización usando pantalla LCD 16x2

# Integrantes

-Jonathan Alexander Ducuara Enciso - C.C. 1031648483

-Sofia Cabanzo Sanabia - C.C. 1053332421

-Valentina Parra Stella - vparras@unal.edu.co

18 de Junio del 2026


# Informe

Indice:

1. [Diseño implementado](#diseño-implementado)
2. [Simulaciones](#simulaciones)
3. [Implementación](#implementación)
4. [Conclusiones](#conclusiones)
5. [Referencias](#referencias)

## Diseño implementado
### Descripción

En este laboratorio se busca comprender el funcionamiento de una pantalla LCD (*Liquid Crystal Display* o pantalla de cristal líquido), así como los principios básicos de su comunicación y control. Con este propósito, se diseñará e implementará un código capaz de mostrar mensajes predeterminados en la pantalla mediante una visualización estática y, posteriormente, modificar dichos mensajes de acuerdo con las condiciones de operación del sistema mediante una visualización dinámica. De esta manera, se analizará tanto el proceso de envío de información a la LCD como la gestión de diferentes mensajes en tiempo real.

## Implementación

Una pantalla LCD es un dispositivo que permite visualizar información mediante cristales líquidos. En el casillero, su función es comunicar al usuario el estado del sistema, mostrando mensajes como el ingreso de clave, el cambio de contraseña o los dígitos digitados:

![Diagrama del sistema](Bus-de-datos-lcd.webp)


Para la implementación del sistema de visualización del casillero se utilizará una pantalla LCD de 16 columnas y 2 filas compatible con el controlador HD44780. Su función será proporcionar comunicación visual entre el sistema y el usuario, mostrando mensajes relacionados con el estado del casillero, como el ingreso de la clave, la verificación de acceso, el cambio de contraseña y la confirmación de operaciones.

La visualización será dinámica, de manera que el mensaje mostrado dependa del estado actual de la máquina de estados finitos (FSM). Para ello, la FSM genera una señal de control de 3 bits que será utilizada por el módulo de la LCD para seleccionar el mensaje correspondiente.

Los caracteres que visualizados en la pantalla se representarán mediante el código ASCII, permitiendo visualizar letras, números y símbolos requeridos por la aplicación. La comunicación entre la FPGA y la pantalla se realiza a través de las líneas de datos y las señales de control RS, R/W y E, encargadas de seleccionar el tipo de información enviada, definir la operación de lectura o escritura y sincronizar la transferencia de datos, respectivamente.


Para esto, se deben diseñar los mensajes estáticos y luego, convertirlos en dinámicos:

- **LCD estática:**  Se implementará una máquina de estados encargada de inicializar la pantalla LCD mediante la secuencia de comandos requerida por el controlador HD44780. Una vez completada la inicialización, esta misma lógica permitirá enviar los caracteres correspondientes al mensaje seleccionado por la FSM. Debido a que la LCD opera a una velocidad considerablemente menor que la FPGA, se utilizará un divisor de frecuencia para generar una señal de reloj más lenta y asi evitar errores por los tiempos de operación exigidos por el dispositivo.

## Conclusiones


## Referencias

