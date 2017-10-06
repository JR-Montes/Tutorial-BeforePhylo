## Tutorial BeforePhylo

By José Rubén Montes Montiel

Octubre 2017


### Introducción


[BeforePhylo](https://github.com/qiyunzhu/BeforePhylo)

### Crear un directorio de trabajo


Entra a tu directorio `BeforePhylo`y utiliza la siguiente línea de comando para descargar BeforePhylo

`wget https://github.com/qiyunzhu/BeforePhylo.git`


Primero slecciona la lista de genes desde Geneious y exporta los genes con la opción "_export bacht_" que se encuentra en la opción "_Archivo_" de la pestaña de herramientas y guarda los genes en formato "_FASTA sequences/alignment_" 

A través del softwere libre de transferencia de datos FTP [FileZilla](https://filezilla-project.org/download.php), exporta los genes o la lista de genes que seleccionaste en Geneious a tu directorio de trabajo en la terminal del servidor.

 `BeforePhylo`
 
 Ahora ve a la terminal y visualiza lo que hay dentro del directorio, teclea:


`ls -l`

### Crear un archivo `.txt` para correr múltiples muestras. 

Para utilzar el escript de perl necesitas un archivo .txt con la lista de ejemplares que deseas trabajar. Utiliza la siguiente línea de comandos desde el directorio `BeforePhylo`:

nano taxa_list.txt

```
```


Para ejecutar el script de perl BeforePhylo debes contar con el script ya instalado, un archivo con los ejemplares en formato .txt y la lista de genes en formato .fasta. Ahora ejecuta el escript con la siguinte línea de comandos desde tu directorio:

`perl BeforePhylo.pl -filter=taxa_list.txt -trim *.fasta -output=phylip`


**NOTA**: En esta ocasión necesitamos que los archivos se guarden en formato `phylip` pero puedes gurdar los archivos en formato `nexus`y entonces debes cambiar el archivo de salida por `-output=nexus` 

### Crear archivo `tar`

El formato `tar`funciona como un programa para comprimir y descomprimir archivos. Para almacenar todos lo genes con formato `.phy`en un archivo `tar`, teclea:

`tar -zcvf Cembroides_t21_n304.phy.tar.gz *.phy`

**NOTA**: En esta ocasión necesitamos que en el archivo `tar` se guarden los genes en formato `phylip` pero puedes gurdar los archivos en formato `nexus`, entonces debes cambiar el formato, ejemplo: 

`tar -zcvf Cembroides_t21_n304.nex.tar.gz *.nex`

### Crear nuevo directorio para archivos en formato `.phy`

Ahora debes crear un directorio para guardar los archivos que has generado, teclea:

`mkadir Cembroides_t21_n304`

Mueve los archivos al nuevo directorio con la siguinet línea de comandos:

`mv *.phy Cembroides_t21_n304`

**NOTA**: Después puedes borrar los archivos en formato `.fasta`para no saturar el espacio en el servidor, teclea:

`rm -r *.fasta`

