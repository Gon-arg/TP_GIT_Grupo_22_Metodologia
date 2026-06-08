1. Integrante con mas commits:Gonzalo
comando: git shortlog -sn --all
 17  Gon-arg
15  ricardo herbas
10  Celina
    3  Celina Vega
    2  ricardoherbas

2. Cantidad total de merges: 9 
   (git log --oneline --merges).Count

3. Cantidad de ramas: 5 son las ramas reales del repositorio en GitHub. excluyo el puntero HEAD que aparece en git branch -a.
comando: git branch -r

4. Cantidad de conflictos: 1

5. Commit con más archivos modificados: 7
df01000 chore: mover archivos de comandos a la carpeta comandos
comando: git log --stat --oneline
comando para el commit que tenga más archivos: git show df01000

