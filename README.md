# Hola Mundo en Vagrant

## 1. Instalación de Vagrant

Vagrant lo podemos instalar para nuestro sistema operativo descargando directamente desde este sitio:

https://www.vagrantup.com/downloads.html

Descargamos la versión que necesitemos y la instalamos. En nuestro caso vamos a descargar la versión de Debian, que es compatible con Ubuntu 16.04, que es el sistema operativo que estamos usando.

Podemos comprobar que se ha instalado bien ejecutando:

```shell
$ vagrant --version
Vagrant 2.2.4
```

En el momento de escribir este documento, la versión más reciente era la 2.2.4

## 2. Creación de la primera máquina virtual usando Vagrant

Ejecutamos:

```shell
$ vagrant init hashicorp/precise64
```

Esto nos crea el fichero Vagrantfile, que es el fichero principal descriptor de Vagrant.

Simplificando y eliminando todos los comentarios, el fichero es así:

```Vagrantfile
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/precise64"
end
```

## 3. Arranque

Ejecutamos:

```shell
$ vagrant up
```

Con esto nos va a descargar el "box" de la distribución hashicorp/precise64 a nuestro repositorio local, y nos la va a arrancar.

Podemos comprobar que está levantada viendo la consola pricipal de Virtual Box.

## 4. Ver que boxes tenemos instalados en nuestro repositorio local

Podemos ver que máquinas tenemos instaladas en nuestro repositorio local de boxes ejecutando:


```shell
$ vagrant box list
hashicorp/precise64 (virtualbox, 1.1.0)
```

## 5. Comprobar el estado de las máquinas controladas por Vagrant

Comprobamos el estado de las máquinas controladas por Vagrant.

```shell
$ vagrant status
Current machine states:

default                   running (virtualbox)

The VM is running. To stop this VM, you can run `vagrant halt` to
shut it down forcefully, or you can run `vagrant suspend` to simply
suspend the virtual machine. In either case, to restart it again,
simply run `vagrant up`.
```

En este caso tenemos la máquina default

## 6. Accediendo por ssh a nuestra máquina

```shell
$ vagrant ssh
Welcome to Ubuntu 12.04 LTS (GNU/Linux 3.2.0-23-generic x86_64)

 * Documentation:  https://help.ubuntu.com/
New release '14.04.6 LTS' available.
Run 'do-release-upgrade' to upgrade to it.

Welcome to your Vagrant-built virtual machine.
Last login: Mon Mar 11 15:15:28 2019 from 10.0.2.2
```

Con esto ya estaríamos dentro de la máquina virtual que hemos levantado

## 7. Apagado de la máquina

```shell
$ vagrant halt default
```

## 8. Consideraciones finales

Con esto ya hemos sido capaces de instalar una máquina virtual, basada en una box oficial de Vagrant, entrar con ssh, y pararla.









