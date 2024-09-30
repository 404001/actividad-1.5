> [!IMPORTANT]
> Todos estos comandos son ejecutados por dentro de `root`

## Actividad-1.5

Gestion de usuarios de Linux mediante comandos.

---

### Creacion de los usuarios

Lo primero es crear los usuarios y ponerle su respectiva contraseña cifrada a cada uno usando la erramienta de ` openssl `
```
useradd user1
useradd user2
useradd user3
useradd user4
```
```
openssl rand -base64 12 > pass1.txt
openssl rand -base64 12 > pass2.txt
openssl rand -base64 12 > pass3.txt
openssl rand -base64 12 > pass4.txt
```
Y procedemos a asignar cada cotraseña a su usuario.

---

### Crear grupos de permisos
Para crear grupos de permisos necesitamos saber los nombres de estos, en nuestro caso `ventas` y `jefeventas`

El siguiente comando crea los 2 grupos:
```
groupadd ventas
groupadd jefeventas
```

---

### Crear directorios & archivos
Para crear los directorios a los que los usuarios van a tener acceso tenemos q hacer lo siguiente:

```
mkdir general
mkdir exclusivo
```
```
touch file{1..4}.txt
```

---

### Cambiar las contraseñas de los users

Para poder poner las contraseñas cifradas vamos a usar las contraseñas de antes generadas por `openssl` en base64 con una longitud de 12 caracteres, con el siguiente comando:

```
passwd <user>
```
Y te saldra un input para q pongas la contraseña y la confirmes:
```
Enter new UNIX password:
Retype new UNIX password:
```

---

### Ajustar los permisos

Para ajustar los permisos nos vamos a fijar en la siguiente tabla de datos:

|              | Lectura    | Escritura | Ejecucion |
|--------------|------------|-----------|-----------|
| File 1       | SI         | NO        | NO        |
| File 2       | SI         | SI        | NO        |
| File 3       | SI         | SI        | SI        |
| File 4       | SI         | NO        | NO        |
| general/     | SI         | SI        | NO        |
| exclusivo/   | SI         | NO        | NO        |

Para asignar a un grupo un usuario es con el siguiente comando.

```
useradd <user> ventas/jefeventas
```

Luego para dar permisos sobre un archivo/carpeta tenemos q ejecutar el siguiente comando:

```
setfacl -m u:<user>:<perms> <directory/file>
```


