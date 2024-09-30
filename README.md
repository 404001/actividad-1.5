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

### Crear directorios
Para crear los directorios a los que los usuarios van a tener acceso tenemos q hacer lo siguiente:

```
mkdir general
mkdir exclusivo
```

###


