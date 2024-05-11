### Paso 0:

```bash 
sudo apt-get update
```

```bash 
sudo apt-get upgrade
```

### Paso 1: Instalar Java

```bash
sudo apt-get install openjdk-8-jdk
```

Añadimos JAVA_HOME a las variables de entorno en 

```bash 
`nano ~/.bashrc` o `nano ~/.zshrc`, 
```

```bash
EXPORT JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
````

### Paso 2: Instalar Scala

```bash
`sudo apt-get install scala`
```
### Paso 3: Instalar Spark

1. Ir a `http://spark.apache.org/downloads.html`
2. Descargarlo (es el paso 3 en la web)
3. Descomprimirlo: `sudo tar xzvf spark-blabla.tgz`
4. `sudo mv /usr/local/spark_VERSION /usr/local/spark`
5. Añadimos variables de entorno:  
5.1. `nano ~/.bashrc` o `nano ~/.zshrc`  
5.2. Añadimos

```bash
export SPARK_HOME=/usr/local/spark
export PYSPARK_PYTHON=python3

export PATH=$SPARK_HOME/bin:$PATH
```

6. `source ~/.bashrc` o `source ~/.zshrc`

## Entorno Virtual de python

```bash
emi@emi-All-Series:~/Escritorio/curso_spark$ python3 -m venv env
emi@emi-All-Series:~/Escritorio/curso_spark$ ls
env
emi@emi-All-Series:~/Escritorio/curso_spark$ source env/bin/activate
(env) emi@emi-All-Series:~/Escritorio/curso_spark$ pip list
Package       Version
------------- -------
pip           20.0.2 
pkg-resources 0.0.0  
setuptools    44.0.0 
(env) emi@emi-All-Series:~/Escritorio/curso_spark$ pip install pyspark
Collecting pyspark
  Downloading pyspark-3.5.1.tar.gz (317.0 MB)
     |████████████████████████████████| 317.0 MB 25 kB/s 
Collecting py4j==0.10.9.7
  Downloading py4j-0.10.9.7-py2.py3-none-any.whl (200 kB)
     |████████████████████████████████| 200 kB 19.6 MB/s 
Building wheels for collected packages: pyspark
  Building wheel for pyspark (setup.py) ... error
  ERROR: Command errored out with exit status 1:
   command: /home/emi/Escritorio/curso_spark/env/bin/python3 -u -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'/tmp/pip-install-s2g87zf0/pyspark/setup.py'"'"'; __file__='"'"'/tmp/pip-install-s2g87zf0/pyspark/setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, __file__, '"'"'exec'"'"'))' bdist_wheel -d /tmp/pip-wheel-j0edjzed
       cwd: /tmp/pip-install-s2g87zf0/pyspark/
  Complete output (6 lines):
  usage: setup.py [global_opts] cmd1 [cmd1_opts] [cmd2 [cmd2_opts] ...]
     or: setup.py --help [cmd1 cmd2 ...]
     or: setup.py --help-commands
     or: setup.py cmd --help
  
  error: invalid command 'bdist_wheel'
  ----------------------------------------
  ERROR: Failed building wheel for pyspark
  Running setup.py clean for pyspark
Failed to build pyspark
Installing collected packages: py4j, pyspark
    Running setup.py install for pyspark ... done
Successfully installed py4j-0.10.9.7 pyspark-3.5.1
(env) emi@emi-All-Series:~/Escritorio/curso_spark$ pip list
Package       Version 
------------- --------
pip           20.0.2  
pkg-resources 0.0.0   
py4j          0.10.9.7
pyspark       3.5.1   
setuptools    44.0.0  
```
## instalar jupyter en el entorno

```bash
(env) emi@emi-All-Series:~/Escritorio/curso_spark$ pip install jupyter

(env) emi@emi-All-Series:~/Escritorio/curso_spark$ python -m ipykernel install --user --name pyspark --display-name pyspark
Installed kernelspec pyspark in /home/emi/.local/share/jupyter/kernels/pyspark
```

### Comprobar kernel istalado en sistema 

```bash
(env) emi@emi-All-Series:~/Escritorio/curso_spark$ jupyter kernelspec list
Available kernels:
  python3       /home/emi/Escritorio/curso_spark/env/share/jupyter/kernels/python3
  anaconda      /home/emi/.local/share/jupyter/kernels/anaconda
  bots-api      /home/emi/.local/share/jupyter/kernels/bots-api
  ir            /home/emi/.local/share/jupyter/kernels/ir
  py310         /home/emi/.local/share/jupyter/kernels/py310
  py_global     /home/emi/.local/share/jupyter/kernels/py_global
  pyspark       /home/emi/.local/share/jupyter/kernels/pyspark   <-- este es el que vamos a usar
  javascript    /usr/local/share/jupyter/kernels/javascript
```
## Abrir VS Code 

```bash
(env) emi@emi-All-Series:~/Escritorio/curso_spark$ code . 
```
