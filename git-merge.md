Sirve para unir dos ramas. Una vez que sabes que tu codigo no tiene conflictos y esta apta para usarla, hay que incorporar esos cambios a la rama principal "main" y se usa "merge". 
Primero debes moverte a la rama destino que en este caso es "main": git checkout main 
y despues mergeas la rama que queres incorporar (login): git merge login 
Es importante que dos personas no modifiquen el mismo archivo en ramas distintas porque al mergear aparece un conflicto, ya que git no sabe con que version quedarse y te pide que lo resuelvas vos.