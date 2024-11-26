# LinuxExtendDiskFS 
#### Tenemos un disco de 20GB y queremos ampliarlo a X capacidad.

## 1. Comprobar el fs de la partición actual (xfs, ext)
```
df -Th  /dev/sda1
```

## 2. Ejecutar el comando fdisk
```
fdisk /dev/sda
```

<h4>Secuencia a seguir</h4>

```
d --> Eliminamos la particion actual de 20GB (NO se eliminan datos)
```

```
n --> Creamos una nueva particion
```

```
Primary --> Tipo de Particion (Primary o Extended)
```

```
Start Block: Default - ENTER
End Block: Default - ENTER
```

```
w --> Guardar los cambios y salir de fdisk
```

<h4>Reiniciar la maquina</h4>

```
reboot
```

## 3. Maquina iniciada ya arrancada
```
xfs_growfs /
```

<h4>Comprobar que se ha extendido la particion</h4>

```
lsblk
```
![image](https://github.com/user-attachments/assets/3a323871-21d4-4697-be70-021ab5f1e781)




