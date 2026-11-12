# SISTEMAS-OPERATIVOS
echo $(date '+%d-%m-%Y %H:%M') $(whoami) $(hostname)
printf "%s %s %s\n" "$(date '+%d-%m-%Y %H:%M')" "$(whoami)" "$(hostname)"
Resultado:
11-11-2026 21:57 karipc
ls
cd Documentos/
mkdir -p Primer\ Ciclo/Sistemas\ Operativos Primer\ Ciclo/Redes\ de\ Datos Primer\ Ciclo/Laboratorio\ de\ Infraestructura
tree Primer\ Ciclo/
mkdir -p Primer\ Ciclo/Sistemas\ Operativos/{U1,U2} && mkdir -p Primer\ Ciclo/Redes\ de\ Datos/{U1,U2} && mkdir -p Primer\ Ciclo/Laboratorio\ de\ Infraestructura/{U1,U2}
mkdir -p Primer\ Ciclo/Sistemas\ Operativos/U1/{Act,Prac,Eval} && mkdir -p Primer\ Ciclo/Sistemas\ Operativos/U2/{Act,Prac,Eval}
Resultado:
Primer Ciclo/
├── Laboratorio de Infraestructura
│   ├── U1
│   └── U2
├── Redes de Datos
│   ├── U1
│   └── U2
└── Sistemas Operativos
    ├── U1
    │   ├── Act
    │   ├── Eval
    │   └── Prac
    └── U2
        ├── Act
        ├── Eval
        └── Prac
        
touch Primer\ Ciclo/Sistemas\ Operativos/U1/Prac/{"AltaE1","BajaE2","MediaE3"}
touch Primer\ Ciclo/Sistemas\ Operativos/U2/Act/{"AltaE2","BajaE3","MediaE1"} && touch Primer\ Ciclo/Sistemas\ Operativos/U2/Prac/{"AltaE3","BajaE1","MediaE2"}
tree Primer\ Ciclo/
RESULTADO:
├── Laboratorio de Infraestructura
│   ├── U1
│   └── U2
├── Redes de Datos
│   ├── U1
│   └── U2
└── Sistemas Operativos
    ├── U1
    │   ├── Act
    │   ├── Eval
    │   └── Prac
    │       ├── AltaE1
    │       ├── BajaE2
    │       └── MediaE3
    └── U2
        ├── Act
        │   ├── AltaE2
        │   ├── BajaE3
        │   └── MediaE1
        ├── Eval
        └── Prac
            ├── AltaE3
            ├── BajaE1
            └── MediaE2
            
tar -czvf CopiaPrimerCiclo_$(date '+%d%m%Y_%H%M%S').tar.gz "Primer Ciclo"
tar -czvf Parcial01_$(date '+%d%m%Y_%H%M%S').tar.gz "Primer Ciclo/Sistemas Operativos" "Primer Ciclo/Redes de Datos"
Resultado:
CopiaPrimerCiclo_11112026_222017.tar.gz   Parcial01_11112026_222106.tar.gz

find Primer\ Ciclo/ -type d -name "Pra*"
find Primer\ Ciclo/ -type f -name "Alta??"
find Primer\ Ciclo/ -type d -name "?[2]"
find . -type d -name "*[1-3]"
find . -type f -name "*[E][3]"
Nombres de los compañeros
nano Primer\ Ciclo/Redes\ de\ Datos/U2/estudiantes.txt
<img width="476" height="98" alt="image" src="https://github.com/user-attachments/assets/92eca010-3e40-4eb6-8c43-5d3a096b8a25" />
Ctrl + O, ENTER, Ctrl + X
tree Primer\ Ciclo/
RESULTADO:
Primer Ciclo/
├── Laboratorio de Infraestructura
│   ├── U1
│   └── U2
├── Redes de Datos
│   ├── U1
│   └── U2
│       └── estudiantes.txt
└── Sistemas Operativos
    ├── U1
    │   ├── Act
    │   ├── Eval
    │   └── Prac
    │       ├── AltaE1
    │       ├── BajaE2
    │       └── MediaE3
    └── U2
        ├── Act
        │   ├── AltaE2
        │   ├── BajaE3
        │   └── MediaE1
        ├── Eval
        └── Prac
            ├── AltaE3
            ├── BajaE1
            └── MediaE2

cat Primer\ Ciclo/Redes\ de\ Datos/U2/estudiantes.txt
Primeros 4 compañeros:
head -n 4  Primer\ Ciclo/Redes\ de\ Datos/U2/estudiantes.txt
3 últimos compañeros:
tail -n 3  Primer\ Ciclo/Redes\ de\ Datos/U2/estudiantes.txt
Apellidos:
cut -f 2 -d " " Primer\ Ciclo/Redes\ de\ Datos/U2/estudiantes.txt
Solo nombres:
cut -f 1 -d " " Primer\ Ciclo/Redes\ de\ Datos/U2/estudiantes.txt
Pasar los apellido a otra carpeta
cut -f 2 -d " " Primer\ Ciclo/Redes\ de\ Datos/U2/estudiantes.txt > Primer\ Ciclo/Laboratorio\ de\ Infraestructura/U1/apellidos.txt
tree Primer\ Ciclo/
RESULTADO:
Primer Ciclo/
├── Laboratorio de Infraestructura
│   ├── U1
│   │   └── apellidos.txt
│   └── U2
├── Redes de Datos
│   ├── U1
│   └── U2
│       └── estudiantes.txt
└── Sistemas Operativos
    ├── U1
    │   ├── Act
    │   ├── Eval
    │   └── Prac
    │       ├── AltaE1
    │       ├── BajaE2
    │       └── MediaE3
    └── U2
        ├── Act
        │   ├── AltaE2
        │   ├── BajaE3
        │   └── MediaE1
        ├── Eval
        └── Prac
            ├── AltaE3
            ├── BajaE1
            └── MediaE2

COMPROBACIÓN:
cat Primer\ Ciclo/Laboratorio\ de\ Infraestructura/U1/apellidos.txt                
Crear un nuevo Backup con el formato ya establecido
tar -cvf PrimerCiclo_$(date '+%d-%m-%Y_%H-%M').tar "Primer Ciclo"
Finalmente cree un archivo comprimido:
tar -czvf PrimerCiclo_$(date '+%d-%m-%Y_%H_%M').tar.gz "Primer Ciclo"
Mover el archivo a la carpeta descargas y descomprimir el archivo; evidenciar el árbol desde Descargas luego de descomprimir.
mv PrimerCiclo_*.tar.gz ~/Descargas/
cd ~/Descargas
tar -xzvf PrimerCiclo_*.tar.gz
tree "Primer Ciclo"
RESULTADO:
[karipc@localhost Descargas]$ tree "Primer Ciclo"
Primer Ciclo
├── Laboratorio de Infraestructura
│   ├── U1
│   │   └── apellidos
│   └── U2
├── Redes de Datos
│   ├── U1
│   └── U2
│       └── estudiantes.txt
└── Sistemas Operativos
    ├── U1
    │   ├── Act
    │   ├── Eval
    │   └── Prac
    │       ├── AltaE1
    │       ├── BajaE2
    │       └── MediaE3
    └── U2
        ├── Act
        │   ├── AltaE2
        │   ├── BajaE3
        │   └── MediaE1
        ├── Eval
        └── Prac
            ├── AltaE3
            ├── BajaE1
            └── MediaE2

PARA LOS CUENTOS, PRIMERO DESCARGA Y ABRE EN GOOGLE PARA COPIAR EL LINK Y EJECUTA ESTE COMANDO copiando el link de la pagina:
wget https://www.seracademia.com/academia/MilyUnaNoche.txt
ls
Este comando a continuación ayudará a contar cuántas palabras tiene el archivo MilyUnaNoche.txt y mostrar el resultado en pantalla con una etiqueta personalizada, evitando que aparezca el nombre del archivo al final.
echo "Mil y una Noche: $(wc -w < MilyUnaNoche.txt)"

PARA CAPERUCITA ROJA EJECUTA LO MISMO SOLO CAMBIANDO EL NOMBRE DEL ARCHIVO:
wget https://www.seracademia.com/academia/caperucitaraoja.txt
ls
echo "Caperucita Roja: $(wc -w < caperucitaraoja.txt)"



16 directories, 11 files


