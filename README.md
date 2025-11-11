# Evaluación Módulo 3 - Seguridad Lógica  
**Alumno:** Alejandro García-Mauriño Salas  

---

## Parte 1. Cifrado simétrico con AES Crypt

Para empezar, creé una carpeta llamada **DocumentosSeguros** en el escritorio.  
Dentro puse tres archivos de prueba:  
- `clientes.txt`  
- `contratos.txt`  
- `manual.pdf`  

Instalé **AES Crypt (versión para Windows)** y, haciendo clic derecho en cada archivo, elegí la opción **“AES Encrypt”**.  
Usé una **contraseña segura** y el programa generó los archivos cifrados con la extensión `.aes`.  
Luego probé a descifrar uno de ellos (`clientes.txt.aes`) usando la misma contraseña y se recuperó correctamente.  

**Ventajas y riesgos de usar una misma clave:**  
Usar una sola clave para todo es más rápido y cómodo, pero si alguien la consigue puede acceder a todos los archivos.  
Por eso, lo mejor sería usar contraseñas diferentes o guardarla en un gestor de contraseñas.

---

## Parte 2. Cifrado asimétrico con Gpg4win / Kleopatra

Instalé **Gpg4win** y abrí **Kleopatra**.  
Allí creé un par de claves con mi nombre y un correo ficticio:  
**Alejandro Mauriño – alejandro@securedevsolutions.com**  

Después exporté mi **clave pública** con el nombre `clave_publica.asc`.  
Luego creé un archivo `mensaje.txt` con un texto de prueba y lo cifré con esa clave pública, lo que generó el archivo `mensaje.txt.gpg`.  

**Explicación:**  
Solo el destinatario puede descifrar el mensaje porque se cifra con su clave pública, y solo su **clave privada** sirve para abrirlo.  
Si se filtrara mi clave privada, alguien podría hacerse pasar por mí o leer mis mensajes, por eso hay que protegerla con una contraseña fuerte y guardarla en un sitio seguro.

---

## Parte 3. Verificación de integridad con MD5

Abrí el **Símbolo del sistema (CMD)** y generé el hash de uno de los archivos originales, guardándolo en `hash_original.txt`.  
Después modifiqué el archivo levemente y generé otro hash, guardado en `hash_modificado.txt`.  
Los valores salieron completamente distintos, aunque el cambio fue mínimo.

**Explicación:**  
El hash cambia totalmente aunque se modifique solo una letra, porque el algoritmo MD5 crea una huella digital única de cada archivo.  
Esto sirve para comprobar si un documento ha sido alterado o manipulado.

---

## Parte 4. Control de acceso con ACL en Windows

Desde **Administrar equipos → Usuarios y grupos locales**, creé tres usuarios nuevos:
- tecnico  
- gerente  
- externo  

Después configuré los permisos en la carpeta **DocumentosSeguros** desde Propiedades → Seguridad → Editar.  
Les asigné los siguientes permisos:

| Usuario  | Permiso            |
|-----------|--------------------|
| tecnico   | Control total      |
| gerente   | Solo lectura       |
| externo   | Ninguno            |

Comprobé que cada usuario tenía los permisos correctos al intentar acceder a la carpeta con sus respectivas cuentas.

---

## Reflexión final

Este trabajo me ayudó a entender mejor cómo proteger la información en una empresa.  
El cifrado garantiza que solo las personas autorizadas puedan acceder a los archivos, el hash asegura que nadie los modifique, y los permisos evitan accesos indebidos.  
Todo esto forma parte de la **seguridad lógica**, que es clave para proteger datos sensibles en cualquier organización.

---
