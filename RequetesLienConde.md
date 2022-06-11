# Projet de fin d'études 

> 3) Les requêtes concernant les items possédant une page Wikipédia  

  > c. Le musée Condé de Chantilly 

La première requête va permettre d’afficher les collections d'œuvres exposées au musée Condé, sous la forme d’items de type “Sculptures”, ayant leur propre page Wikipédia. Le résultat est affiché sous la forme d’une liste des œuvres.  Actuellement, aucun objet ne dispose d’un lien Wikipédia, puisque ce musée conserve en majorité des objets de type "Peintures". 

```sparql
SELECT DISTINCT ?item ?itemLabel ?itemDescription ?collection ?articleFR  
WHERE {
   ?item wdt:P31/wdt:P279* wd:Q860861 ; #sculpture
   wdt:P195/wdt:P361* ?collection . # qui font partie de musées et de tous ses départements si existant

FILTER ( ?collection = wd:Q1236032 ) #musee conde
  
?articleFR schema:about ?item . ?articleFR schema:isPartOf <https://fr.wikipedia.org/> . # qui ont une page Wikipédia en français

SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE]" }
  
}
```
<iframe style="width: 60vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#SELECT%20DISTINCT%20%3Fitem%20%3FitemLabel%20%3FitemDescription%20%3Fcollection%20%3FarticleFR%20%20WHERE%20%7B%0A%20%20%20%3Fitem%20wdt%3AP31%2Fwdt%3AP279%2a%20wd%3AQ860861%20%3B%20%23sculpture%0A%20%20%20wdt%3AP195%2Fwdt%3AP361%2a%20%3Fcollection%20.%20%23%20qui%20font%20partie%20de%20mus%C3%A9es%20et%20de%20tous%20ses%20d%C3%A9partements%20si%20existant%0A%0AFILTER%20%28%20%3Fcollection%20%3D%20wd%3AQ1236032%20%29%20%23musee%20conde%0A%20%20%0A%3FarticleFR%20schema%3Aabout%20%3Fitem%20.%20%3FarticleFR%20schema%3AisPartOf%20%3Chttps%3A%2F%2Ffr.wikipedia.org%2F%3E%20.%23%20qui%20ont%20une%20page%20en%20wikipeida%20FR%0A%0ASERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%22%20%7D%0A%20%20%0A%7D%0A%0A%0A%0A%0A%0A%0A" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" ></iframe>

******************************************************************

La seconde requête va permettre d’afficher les collections d'œuvres exposées au musée Saint-Raymond, sous la forme d’items de type “Peintures”, ayant leur propre page Wikipédia. Le résultat est affiché sous la forme d’une liste des œuvres.  Actuellement, 29 objets de type “Peintures” disposent chacun un lien Wikipédia. 

```sparql
SELECT DISTINCT ?item ?itemLabel ?itemDescription ?collection ?articleFR  
WHERE {
    ?item wdt:P31/wdt:P279* wd:Q3305213 ; # peinture et sous-classe de peinture
    wdt:P195/wdt:P361* ?collection . # qui font partie de musées et de tous ses départements si existant

FILTER ( ?collection = wd:Q1236032 ) #musee conde
  
?articleFR schema:about ?item . ?articleFR schema:isPartOf <https://fr.wikipedia.org/> . # qui ont une page Wikipédia en français

SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE]" }
  
}
```
<iframe style="width: 60vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#SELECT%20DISTINCT%20%3Fitem%20%3FitemLabel%20%3FitemDescription%20%3Fcollection%20%3FarticleFR%20%20WHERE%20%7B%0A%20%20%20%20%3Fitem%20wdt%3AP31%2Fwdt%3AP279%2a%20wd%3AQ3305213%20%3B%20%23%20peinture%20et%20sous-classe%20de%20peinture%0A%20%20%20%20wdt%3AP195%2Fwdt%3AP361%2a%20%3Fcollection%20.%20%23%20qui%20font%20partie%20de%20mus%C3%A9es%20et%20de%20tous%20ses%20d%C3%A9partements%20si%20existant%0A%0AFILTER%20%28%20%3Fcollection%20%3D%20wd%3AQ1236032%20%29%20%23musee%20conde%0A%20%20%0A%3FarticleFR%20schema%3Aabout%20%3Fitem%20.%20%3FarticleFR%20schema%3AisPartOf%20%3Chttps%3A%2F%2Ffr.wikipedia.org%2F%3E%20.%23%20qui%20ont%20une%20page%20en%20wikipeida%20FR%0A%0ASERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%22%20%7D%0A%20%20%0A%7D%0A%0A%0A%0A%0A%0A%0A%0A%0A" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" ></iframe>

****************************************************************

[Page précédente](RequetesLienStRaymond.md)


[Page suivante](RequetesLienParisMusees.md)


[Retour à la page d'accueil](README.md)
