
Requête finale permettant d’afficher le nombre d’oeuvres de type "Peintures" publié par les musées français (100%) 

```sparql
SELECT ?CollectionLabel (COUNT(?item) AS ?count)
WHERE
{
 ?item wdt:P31/wdt:P279* wd:Q3305213.
 ?item wdt:P195 ?Collection.
 ?Collection wdt:P17 wd:Q142.  
OPTIONAL {
 ?item wdt:P18 ?pic .
}
  SERVICE wikibase:label { 
bd:serviceParam wikibase:language "fr,en"}
    
}
GROUP BY ?CollectionLabel
ORDER BY DESC (?count) 

```
********************
<iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#SELECT%20%3FCollectionLabel%20%28COUNT%28%3Fitem%29%20AS%20%3Fcount%29%0AWHERE%0A%7B%0A%20%3Fitem%20wdt%3AP31%2Fwdt%3AP279%2a%20wd%3AQ3305213.%0A%20%3Fitem%20wdt%3AP195%20%3FCollection.%0A%20%3FCollection%20wdt%3AP17%20wd%3AQ142.%20%20%0AOPTIONAL%20%7B%0A%20%3Fitem%20wdt%3AP18%20%3Fpic%20.%0A%7D%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20%0Abd%3AserviceParam%20wikibase%3Alanguage%20%22fr%2Cen%22%7D%0A%20%20%20%20%0A%7D%0AGROUP%20BY%20%3FCollectionLabel%0AORDER%20BY%20DESC%20%28%3Fcount%29%20%0A" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" ></iframe>


**************
Requête finale permettant d’afficher le nombre d’oeuvres de type "Peintures" publié par les vingt musées français 

```sparql 
#defaultView:BarChart

SELECT ?CollectionLabel (COUNT(?item) AS ?count)
WHERE
{
 ?item wdt:P31/wdt:P279* wd:Q3305213.
 ?item wdt:P195 ?Collection.
 ?Collection wdt:P17 wd:Q142.  
OPTIONAL {
 ?item wdt:P18 ?pic .
}
  SERVICE wikibase:label { 
bd:serviceParam wikibase:language "fr,en"}
    
}
GROUP BY ?CollectionLabel
ORDER BY DESC (?count) 

LIMIT 20
```
********************
<iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3ABarChart%0A%0ASELECT%20%3FCollectionLabel%20%28COUNT%28%3Fitem%29%20AS%20%3Fcount%29%0AWHERE%0A%7B%0A%20%3Fitem%20wdt%3AP31%2Fwdt%3AP279%2a%20wd%3AQ3305213.%0A%20%3Fitem%20wdt%3AP195%20%3FCollection.%0A%20%3FCollection%20wdt%3AP17%20wd%3AQ142.%20%20%0AOPTIONAL%20%7B%0A%20%3Fitem%20wdt%3AP18%20%3Fpic%20.%0A%7D%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20%0Abd%3AserviceParam%20wikibase%3Alanguage%20%22fr%2Cen%22%7D%0A%20%20%20%20%0A%7D%0AGROUP%20BY%20%3FCollectionLabel%0AORDER%20BY%20DESC%20%28%3Fcount%29%20%0A%0ALIMIT%2020" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" ></iframe>
********
