Combien la base de données contient-elle de sociétés offshores différentes dont la source est "Panama Papers" ?
    SELECT COUNT(*) AS num_offshoresociety_sourcepanama FROM entity WHERE source = 'Panama Papers'



Quel intermédiaire a créé le plus de sociétés offshores ? A-t-on son adresse et son pays ?
   SELECT intermediary.id AS intermediary_id, intermediary.name AS intermediary_name, entity.name AS entity_name, entity.jurisdiction_description, address.address, count(*) 
    FROM entity, intermediary, assoc_inter_entity, address
    WHERE assoc_inter_entity.entity = entity.id AND assoc_inter_entity.inter = intermediary.id AND address.id_address = entity.id_address 
    GROUP BY intermediary.name
    ORDER BY count(*) DESC


Combien la base contient-elle de bénéficiaires avec un nom unique ? Quel est le bénéficiaire dont le nom revient le plus souvent ?


Donner la liste des juridictions avec le nombre d'entreprises offshores enregistrées sur chaque territoire, triée par ordre décroissant.


Regrouper les sociétés offshores par statut, et trier la liste par ordre décroissant.


Trouver la liste des bénéficiaires dont le nom contient "BNP" et ajouter, pour chaque bénéficiaire, le nom des sociétés offshores.


Trouver la liste des sociétés dont la juridiction est "France", "Monaco" ou "Réunion".


Trouver la liste des sociétés dont le pays de l'adresse et le pays de la juridiction sont différents.


Trouver la liste des bénéficiaires qui ont des sociétés au même nom et enregistrée à la même date, trier la liste par odre décroissant.


Donner la liste des intermédiaires qui ont aussi été bénéficiaires, en ajoutant leur nom de bénéficiaire et leur adresse.


Donner le top 10 des bénéficiaires qui ont le plus d'identités différentes (similar name and address) et le nombre d'identités correspondant.


Donner le top 10 des bénéficiaires qui ont le plus de parts toujours valides dans des entreprises offshores (dont la date de fin n'est pas encore passée).


