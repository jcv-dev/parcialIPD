#!/usr/bin/env bash
#
# Este script se encarga de invocar los tres programas que permiten la 
# conversion de un PNG a secuencia de pixeles, se procesan esos pixeles y
# posteriormente se convierte esa secuencia de pixeles a un archivo en formato
# PNG
#
# Autor: John Sanabria - john.sanabria@correounivalle.edu.co
# Fecha: 2024-08-22
#
for img in ./*.jpg ; do
    # Obtener el nombre base del archivo
    img_name=$(basename "$img" .jpg)
    
    # Convertir JPG a PNG temporal
    python3 fromPNG2Bin.py "${img}"
    
    # Aplicar el filtro
    ./main "${img_name}.bin"
    
    # Convertir el resultado a PNG
    python3 fromBin2PNG.py "${img_name}.bin.new"
    
    # Limpiar archivos temporales
    rm "${img_name}.bin" "${img_name}.bin.new"
done