# Práctica 2 - Instalación y configuración de Visual Studio Code

En esta práctica llevaremos a cabo la instalación y configuración del entorno de desarrollo que utilizaremos
durante toda la asignatura, esto es, Visual Studio Code.

Tendrán que llevar a cabo un informe acerca de todos los pasos que han seguido, además de enumerar
los diferentes problemas a los que se han enfrentado con sus respectivas soluciones.

## Instalación y funcionalidad de Visual Studio Code

[Visual Studio Code](https://code.visualstudio.com/) (VSCode) es uno de los entornos más utilizados por los
desarrolladores. Como primer paso, [instale VSCode](https://code.visualstudio.com/docs/setup/setup-overview)
en su máquina local. Si está trabajando en una distribución Linux Debian/Ubuntu puede instalarlo haciendo uso
del siguiente comando:

```bash
edusegre@lluvia:~$ sudo apt install code
```

También puede hacer uso de snap para instalar VSCode:

```bash
edusegre@lluvia:~$ sudo snap install code --classic
```

A continuación, lea los tutoriales sobre VSCode y aprenda las funcionalidades básicas:
* [Additional Components](https://code.visualstudio.com/docs/setup/additional-components)
* [User Interface](https://code.visualstudio.com/docs/getstarted/userinterface)
* [Basic Editing](https://code.visualstudio.com/docs/editor/codebasics)
* [Extension MarketPlace](https://code.visualstudio.com/docs/editor/extension-gallery)
* [IntelliSense](https://code.visualstudio.com/docs/editor/intellisense)
* [Code Navigation](https://code.visualstudio.com/docs/editor/editingevolved)
* [Debugging](https://code.visualstudio.com/docs/editor/debugging)
* [Version Control](https://code.visualstudio.com/docs/editor/versioncontrol)
* [Working with GitHub](https://code.visualstudio.com/docs/editor/github)
* [Integrated Terminal](https://code.visualstudio.com/docs/editor/integrated-terminal)
* [Tasks](https://code.visualstudio.com/docs/editor/tasks)
* [Snippets](https://code.visualstudio.com/docs/editor/userdefinedsnippets)
* [Emmet](https://code.visualstudio.com/docs/editor/emmet)
* [Command Line](https://code.visualstudio.com/docs/editor/command-line)
* [Multiroot Workspaces](https://code.visualstudio.com/docs/editor/multi-root-workspaces)
* [Accessibility](https://code.visualstudio.com/docs/editor/accessibility)

## Configuración de Visual Studio Code para conectarse a una máquina remota por SSH

En este apartado, llevaremos a cabo la configuración necesaria para [conectarnos desde VSCode a una máquina
remota por SSH](https://code.visualstudio.com/docs/remote/ssh-tutorial), en concreto, a nuestra máquina
virtual del IaaS.

Si ha llevado a cabo la [Práctica 1 de DSI](https://ull-esit-inf-dsi-2021.github.io/prct01-iaas/), habrá
configurado su máquina local y virtual con todo lo necesario para poder realizar una conexión vía SSH. Si
aún no lo ha hecho, deberá hacerlo ahora. También recuerde que para establecer una conexión vía SSH con una
máquina del IaaS, debe estar conectado a la VPN de la ULL.

Una vez que se haya asegurado de que puede establecer una conexión SSH desde su máquina local a su máquina
virtual del IaaS, lo que debe hacer ahora es abrir una instancia de VSCode, buscar e instalar la extensión
de VSCode denominada *Remote - SSH*. Si no sabe cómo instalar una extensión en VSCode, aprenda a utilizar el
[*Extension Marketplace* de VSCode](https://code.visualstudio.com/docs/editor/extension-gallery).

A continuación, pulse la tecla `F1` o la combinación de teclas `Ctrl + Shift + P` para mostrar la paleta de
comandos, teclee `ssh` y pulse sobre `Connect to Host...`. Si completó todos los pasos de configuración
indicados durante la primera práctica, incluyendo la configuración del fichero `~/.ssh/config`, entre las
opciones del menú desplegable aparecerá el nombre de su máquina virtual. Si así no fuera, pulse sobre la
opción `Configure SSH Hosts...` y elija la opción `~/.ssh/config`. Seguidamente, incluya las siguientes
líneas en dicho fichero y guarde los cambios:

```bash
Host iaas-dsi2
  HostName iaas-dsi2
  User usuario
```

Tenga en cuenta que donde pone `iaas-dsi2`, deberá indicar el nombre de host que le otorgó en su momento
a su máquina virtual del IaaS.

Una vez hecho lo anterior, vuelva a pulsar `F1`, teclee `ssh`, pulse sobre `Connect to Host...` y haga clic
sobre el nombre de su máquina virtual. Se iniciará una nueva instancia de VSCode y se iniciará la conexión
SSH. Para comprobar que se ha conectado a su máquina virtual de manera remota, abra una terminal desde el
propio VSCode, pulsando la combinación de teclas `Ctrl + Shift + ``. En la terminal teclee el siguiente comando:

```bash
[~()]$hostname
iaas-dsi2
[~()]$
```

Como puede observar, dicho comando devuelve el nombre de host de la máquina virtual remota. En la esquina inferior
izquierda de la interfaz, en un área de color verde, podrá ver el nombre de la máquina virtual a la que acaba de
conectarse.

## Sesiones colaborativas con Visual Studio Live Share

[Visual Studio Live Share](https://code.visualstudio.com/blogs/2017/11/15/live-share) permite colaborar en las
tareas de desarrollo en tiempo real. Para poder utilizarlo, en primer lugar, debe buscar e instalar la extensión
denominada
[*Live Share Extension Pack*](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack),
así como todas las extensiones recomendadas que podrá encontrar en el enlace anterior.

Una vez hecho lo anterior, siga las instrucciones proporcionadas en la sección *Getting Started* del enlace anterior
para iniciar una sesión colaborativa. Comparta el enlace con otros estudiantes y pruebe las diferentes funcionalidades
como, por ejemplo, los chats, llamadas o pizarra. Cabe mencionar que si está usando una instancia de VSCode conectada
a la máquina virtual del IaaS, no podrá utilizar la funcionalidad de llamadas en una sesión colaborativa.

Para más información, puede leer la [documentación de Visual Studio Live Share](https://docs.microsoft.com/en-us/visualstudio/liveshare/).
