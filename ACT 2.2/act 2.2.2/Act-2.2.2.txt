SELECT * FROM clients;
SELECT * FROM produits;
SELECT DISTINCT type FROM produits;
SELECT type ,COUNT(*) FROM produits GROUP BY type;
SELECT * FROM clients WHERE `nom` LIKE '%s%'
ALTER TABLE `produits` ADD `prix` FLOAT NOT NULL DEFAULT '200' AFTER `réference_au_fournisseur`;

/*Afficher pour tous les produits les infos suivantes :nom, type, prix, nom du fournisseur */ 
SELECT nomproduit, type, prix, nomfournisseur FROM produits JOIN fournisseurs ON produits.réference_au_fournisseur= nomfournisseur;

/*Afficher le nombre de produit pour chaque fournisseur*/
SELECT nomfournisseur, COUNT(nomproduit)
FROM produits JOIN fournisseurs ON produits.réference_au_fournisseur= nomfournisseur GROUP BY nomfournisseur;