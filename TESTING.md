# Plan de tests DataShare


| # | Fonctionnalité | Type de test | Outil   | Critère d'acceptation                          |
|---|----------------|--------------|-------  |------------------------------------------------|
| 1 | Inscription    | Unitaire     | JUnit   | Email unique, password hashé, 201 retourné     |
| 2 | Connexion      | Unitaire     | JUnit   | Token JWT valide retourné, 401 si mauvais mdp  |
| 3 | Upload fichier | Unitaire     | JUnit   | Fichier sauvegardé, métadonnées en BDD         |
| 4 | Téléchargement | Unitaire     | JUnit   | Fichier retourné, 404 si token invalide        |
| 5 | Suppression    | Unitaire     | JUnit   | Fichier supprimé physiquement et en BDD        |
| 6 | AuthService    | Unitaire     | Jest    | Token stocké, isAuthenticated() retourne true  |
| 7 | ErrorService   | Unitaire     | Jest    | Messages d'erreur corrects selon code HTTP     |
| 8 | FichierService | Unitaire     | Jest    | uploadFichier() appelle bien l'API             |
| 9 | Flux complet   | E2E          | Cypress | Inscription → Upload → Download → Suppression |
| 10 | Auth flux     | E2E          | Cypress | Login → Accès espace personnel → Déconnexion   |

## Seuil de couverture
Objectif : **70% minimum**

## Instructions d'exécution

### Tests unitaires backend (JUnit)
```bash
cd backend
./mvnw test
```

### Tests unitaires frontend (Jest)
```bash
cd frontend
npm test
```

### Tests E2E (Cypress)
```bash
cd frontend
npx cypress open
```

## Résultats
 
