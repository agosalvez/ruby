# Instalación de Ruby con rbenv

Con Ubuntu instalado en WSL, sigue estos pasos para instalar Ruby 2.5.1 utilizando rbenv.

Actualiza el listado de paquetes e instala dependencias:

```bash
sudo apt-get update
```

```bash
sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev software-properties-common libffi-dev
```

El siguiente paso es instalar Ruby a través de uno de los tres métodos disponible: rbenv, rvm y por medio del código fuente. En este tutorial vamos a utilizar rbenv porqué nos da la posibilidad de tener una versión global de Ruby y además manejar diferentes versiones de Ruby por aplicación.

La instalación de Ruby a través rbenv consta de dos pasos, el primero es instalar rbenv y el segundo ruby-build.

```bash
cd ~

# Instalación de rbenv
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL

# Instalación de ruby-build
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL
```

Si no tuviste ningún error en los pasos anteriores deberías ser capaz de ver la siguiente información de rbenv al momento de introducir el comando "rbenv" en la terminal:

```bash
rbenv 1.1.1-39-g59785f6
Usage: rbenv <command> [<args>]
Some useful rbenv commands are:
   commands    List all available rbenv commands
   local       Set or show the local application-specific Ruby version
   global      Set or show the global Ruby version
   shell       Set or show the shell-specific Ruby version
   install     Install a Ruby version using ruby-build
   uninstall   Uninstall a specific Ruby version
   rehash      Rehash rbenv shims (run this after installing executables)
   version     Show the current Ruby version and its origin
   versions    List all Ruby versions available to rbenv
   which       Display the full path to an executable
   whence      List all Ruby versions that contain the given executable
See `rbenv help <command>' for information on a specific command.
For full documentation, see: https://github.com/rbenv/rbenv#readme
```

Con rbenv y ruby-build disponibles en el sistema operativo, podemos instalar la última versión estable de Ruby y nuestro gestor de gemas con los siguientes comandos:

```bash
# Instalamos la última versión estable
rbenv install 2.5.1
rbenv global 2.5.1

# Verificamos que todo se haya instalado correctamente
ruby -v

# Instalamos bundler
gem install bundler

rbenv rehash
```

Con tu entorno de trabajo configurado llego el momento de programar aplicaciones asombrosas. Para esto escoge tu editor de texto favorito y ejecuta tus archivos desde la terminal de Ubuntu.
