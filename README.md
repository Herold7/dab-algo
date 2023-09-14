# Algorithme DAB

Conception d'un algorithme de DAB¹, sous forme de pseudo-code.

  *¹Distributeur Automatique de billets*

---

```text
Le client insère la carte dans le distributeur
Le processus de vérification de la carte est lancé
    SI la carte n'est pas conforme
        ALORS le distributeur rejette la carte
        Le programme s'arrête
    SINON SI la carte est bloquée 
        ALORS le distributeur avale la carte
        Le programme s'arrête
    SINON 
        La carte est valide
        Lancer la demande du code de la carte
Le distributeur affiche un message demandant "le code de la carte"
Le client tape un code
    SI le code est incorrect 
        ALORS le distributeur affiche un message "code incorrect"
        ET le compteur de tentative est incrémenté de 1
        SI le compteur de tentative est égal à 3
            ALORS le distributeur avale la carte
            Le programme s'arrête
        Lancer la demande du code de la carte
    SINON
    Le code est correct
    Lancer la demande du montant à retirer
Le distributeur affiche un message "demandant de choisir un montant à retirer"
Le processus de vérification de solde du client est lancé
    SI le montant > que le solde || (ou) le montant > plafond
        le retrait est refusé
        le distributeur affiche un message
        Le distributeur relance la demande du montant à retirer
    SINON 
        Le retrait est autorisé
        Le processus de vérification de solde du DAB est lancé
            SI le montant > le solde
                Le retrait est refusé
                Le distributeur affiche un message 
                Le distributeur relance la demande du montant à retirer
            SINON
                Le retrait est autorisé
                Le distributeur remet le montant choisi
Le client récupère sa carte bancaire
Le client récupère l'argent du distributeur
Fin du programme
```