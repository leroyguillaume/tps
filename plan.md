# Part 1
- Modifier le code
- Ouvrir une PR
- Vérifier que la CI run pre-commit
- Vérifier que la CI build l'image Docker
- Vérifier que la CI run les tests
- Vérifier que la CI passe trivy
- Modifier le code qui introduit un bug pas visible par les tests et push 
- Vérifier que le build de l'image Docker est cached
- Merger la PR
- Vérifier que le build de l'image Docker est cached
- Faire un commit (et push) pour modifier la version de l'app
- Vérifier que le build de l'image Docker est cached
- Pusher un tag v0.1.0
- Vérifier que la release GitHub est créé
- Vérifier que l'image est dispo sur GHCR (amd + arm)

# Part 2
- Modifier le code et faire une nouvelle release 0.2.0
- Corriger le bug et le backporter en 0.1.1

# Part 3
- Modifier le code pour downgrade une dépendance
- Lancer le workflow Renovate pour vérifier qu'il met à jour les dépendances
