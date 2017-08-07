# API Annuaire de l’administration

> Le contenu de cet annuaire est généré automatiquement par le script d'import disponible à l'adresse [https://github.com/sgmap/annuaire-import](https://github.com/sgmap/annuaire-import)

## /organismes - Liste des organismes par couple _(département, pivot)_

  Retourne une [FeatureCollection](https://tools.ietf.org/html/rfc7946#section-3.3) des établissements d'un type donné pour un département donné.

* **URL**

  /organismes/**:departement**/**:type**.json
  
  > example: [https://sgmap.github.io/annuaire/organismes/14/maison_handicapees.json](https://sgmap.github.io/annuaire/organismes/14/maison_handicapees.json)

* **Methode:**

  `GET`
  
*  **Paramètres**

   **Obligatoires:**
   
   `departement` - Code departement sur deux caractères (ex: `14`)
   
   `type` - Code du type de l'organisme (ex: `maison_handicapees`)

* **Réponse:**

  * **Code:** 200 <br />
    **Contenu:**   
```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [
          6.1544449,
          48.686989
        ]
      },
      "properties": {}
    }
  ]
}
```
 
* **Erreur:**

  * **Code:** 404 NOT FOUND <br />
