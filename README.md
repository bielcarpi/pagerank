# Page Rank
## Mineria de Dades

---

Aquesta pràctica té com a objectiu implementar i analitzar l'algorisme de PageRank. PageRank és una mètrica desenvolupada pels fundadors de Google, Larry Page i Sergey Brin, que permet classificar pàgines web basant-se en la quantitat i qualitat dels enllaços que les apunten. En aquesta implementació, s'ha donat un esquelet de codi per computar el PageRank, i l'usuari ha d'implementar l'algorisme segons les indicacions donades.


## Datasets
El conjunt de dades proporcionat amb la pràctica es denomina gr0.California i conté un graph de totes les webs relacionades amb la cerca "California". El format del dataset és el següent:

* Línies que comencen amb n: Defineixen un node del graph. Exemple: n ID URL on ID és un identificador únic per al node i URL és l'URL de la pàgina web.
* Línies que comencen amb e: Defineixen una aresta del graph. Exemple: e IDFROM IDTO on IDFROM és l'identificador de la pàgina d'origen i IDTO és l'identificador de la pàgina de destinació.


## Exemple d'Execució

Per executar el programa amb el conjunt de dades proporcionat, fes servir la següent comanda:

```bash
python3 pagerank.py gr0.California.txt [--beta 0.85]
```

On beta és el paràmetre de damping. El valor per defecte (en el cas de no ser proporcionat) és 0.85.

Després d'executar el programa, s'imprimirà la llista de pàgines web ordenades segons el seu PageRank. També es mostrarà el temps que ha trigat l'algorisme a convergir.


## Anàlisi de Resultats
L'algorisme de PageRank implementat proporciona resultats ràpids i precisos, amb una convergència sorprenentment ràpida per un conjunt de dades de 10,000 pàgines web, requerint menys de 0.03 segons per arribar a una solució. Aquesta eficiència no només destaca la potència de l'algorisme de PageRank, sinó també la qualitat de l'implementació.

Un dels paràmetres centrals de l'algorisme de PageRank és el factor de amortiment, β. Aquest paràmetre, que pren valors entre 0 i 1, representa la probabilitat que un usuari continuï seguint enllaços dins d'una pàgina web, en lloc de saltar a una pàgina aleatòria. De fet, (1-β) és la probabilitat que l'usuari faci aquest "salt" aleatori.

En la nostra implementació, β pot ser ajustat per veure com afecta els resultats finals de PageRank. Alguns punts clau sobre β són:

* Influència en la Convergència: Un valor més alt de β pot fer que l'algorisme trigui més a convergir. Això es deu al fet que amb un β elevat, l'algorisme dóna més pes als enllaços existents, fent que les puntuacions de PageRank es distribueixin més lentament.
* Relevància vs. Aleatorietat: Amb un β elevat, els resultats de PageRank estan més influenciats pels enllaços existents del conjunt de dades, donant lloc a puntuacions més basades en la "reputació" del web. En canvi, amb un β més baix, hi ha una major probabilitat de saltar a pàgines aleatòries, el que pot fer que pàgines amb menys enllaços entrants obtinguin puntuacions més altes de PageRank.
* Valors Extrems: Amb β = 1, l'usuari sempre seguirà enllaços i mai no farà salts aleatoris, el que pot no ser realista. Amb β = 0, l'usuari sempre saltarà aleatòriament, ignorant completament la estructura d'enllaços del web.

Després d'analitzar diversos valors de β, és clar que la selecció apropiada d'aquest paràmetre pot tenir un impacte significatiu en la interpretació i aplicació dels resultats de PageRank. La tria d'un valor de β adequat és essencial per assegurar-se que el ranking produït per PageRank reflecteixi de manera precisa la importància i relevància real de les pàgines web. En general, un valor de β entre 0.8 i 0.9 produeix resultats satisfactoris.

<br>

### Autor
Biel Carpi (biel.carpi@students.salle.url.edu)