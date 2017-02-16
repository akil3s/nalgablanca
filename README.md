# nalgablanca
#Script para cortar un fichero tocho en varios más pequeños. creado por alhkÿtran.

#!/bin/bash
aux=$(head -1 $1)
contador=0
num=1
for i in $(cat $1)
do
        if [ $contador = 0 ]; then
                echo "$aux" > ./nalga$num
                contador=$(expr $contador + 1)
        else
                echo $i >> ./nalga$num
                contador=$(expr $contador + 1)
        fi
        if [ $contador = 1500000 ]; then
                contador=0
                num=$(expr $num + 1)
        fi

done

