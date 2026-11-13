Règles:

RG1. Un jouer est identifié par son adresse e-mail unique. On connaît son surnom, son pays et doit se connecter.

RG2. Un joueur peut posséder plusieurs personnages, mais un personnage appartient à un seul joueur. 

RG3. Chaque personnage possède un nom, un niveau, une quantité de point d’expérience et les point de vie. 

RG4. Chaque personnage possède un inventaire dont la capacité de stockage limitée. 

RG5. Un inventaire peut contenir plusieurs objets (armes, armures, potions, équipements). 

RG6. Chaque objet possède des caractéristiques spécifiques selon son types (dégâts, défense, rareté, quantité, etc.). 

RG7. Un personnage peut gagner des points d’expérience en accomplissant des missions ou en battant des ennemis. 

RG8. Le classement des joueurs est établi en fonction de leur score. Un joueur ne peut occuper qu’une seule position dans un même classement. 

RG9. Le classement est mis à jour lorsqu’un joueur gagne ou perd des points.

MCD: 

<img width="227" height="787" alt="image" src="https://github.com/user-attachments/assets/abdd6570-f945-41cd-a360-2989ca13ec25" />

	class JOUEUR {
	    +Guid id
	    +string email
	    +string surnom
	    +string pays
        +personnage personnage
	    +bool connecté_le
    }

    class PERSONNAGE {
	    +Guid id
        +string nom
        +string niveau
        +int pointExp
        +int pointDeVie
	    +statut statut
    }

    class INVENTAIRE {
	    +Guid id
	    +string nom
	    +int espace
        +objet objet
    }

    class CLASSEMENT {
	    +Guid id
	    +string nom
      +list score
    }


    JOUEUR "1,1" -- "1,1" PERSONNAGE : Possède
    PERSONNAGE "1,1" --> "1,1" INVENTAIRE : Possède
    INVENTAIRE "0,n" --> "0,n" CLASSEMENT : Contribue_au
    
    
    <img width="1143" height="6185" alt="End-to-End Encrypted-2026-11-13-091653" src="https://github.com/user-attachments/assets/270b6e07-768e-48b6-a9f5-0586fa357ef1" />



MLD (clé primaire soulignée, clé étrangère précédée de #):

JOUEUR (id, email, surnom, pays, connecte_le)

PERSONNAGE (id, nom, niveau, pointExp, pointDeVie, statut, #id_joueur)

INVENTAIRE (id, nom, espace, #id_personnage)

OBJET (id, nom, prix_unitaire)

CONTENIR (#id_inventaire, #id_objet, quantite)

CLASSEMENT (id, nom)

PARTICIPER (#id_personnage, #id_classement, score)
