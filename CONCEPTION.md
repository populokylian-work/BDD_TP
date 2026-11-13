Règles:





Mcd: 

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


