 PROJET API BLOG TAF 1 INF222
AUTEUR : HENGER FREDY LE ROI  
MATRICULE : 24G2214
DESCRIPTION :
Ce projet est une API Backend simple pour la gestion d'un blog, réalisée dans le cadre de l'UE INF222 (Développement Backend). L'objectif est de permettre la gestion complète des articles (CRUD) en suivant les bonnes pratiques de développement.
J'ai choisi d'utiliser SQLite pour sa légèreté, ce qui facilite les tests locaux sans configuration complexe de serveur de base de données.

🛠 Technologies utilisées
•	Runtime : Node.js 
•	Framework : Express.js 
•	Base de données : SQLite
•	Documentation : Swagger 
🚀 Installation et Lancement
1.	Cloner le dépôt :
Bash
git clone https://github.com/LEROIBLAST/TP-INF-222-TAF-1-UTILISATION-DE-CLEEROUTE.git 
cd TP-INF-222-TAF-1-UTILISATION-DE-CLEEROUTE
2.	Installer les dépendances :
Bash
npm install
3.	Lancer le serveur :
Bash
npm start
Le serveur sera accessible sur http://localhost:3000.
📌 Endpoints de l'API
L'API gère les ressources suivantes sous le préfixe /api/articles :
Méthode	Endpoint	Description
POST	/api/articles	Créer un nouvel article (titre, contenu, auteur, etc.).
GET	/api/articles	Récupérer tous les articles (filtres possibles par catégorie/auteur).
GET	/api/articles/:id	Récupérer un article spécifique via son ID.
PUT	/api/articles/:id	Modifier un article existant.
DELETE	/api/articles/:id	Supprimer un article.
GET	/api/articles/search?query=...	Rechercher dans les titres ou le contenu.
💡 Exemples de requêtes
Créer un article (POST)
Payload :
JSON
{
  "titre": "Introduction au Web",
  "contenu": "Contenu de l'article...",
  "auteur": "Charles",
  "categorie": "Technologie",
  "tags": ["web", "backend"]
}
Réponse attendue : 201 Created avec l'ID de l'article.

Recherche (GET)
GET /api/articles/search?query=Nodejs 

📂 Structure du projet
Le code est structuré de manière à séparer les responsabilités :
📂 src/
 ├── 📂 controllers/     # Logique métier (traitement des requêtes)
 ├── 📂 models/       # Schémas de données (Structure de l'article)
 ├── 📂 routes/       # Définition des points d'accès (Endpoints)
 ├── 📂 config/       # Connexion à la base de données
 └── app.js           # Point d'entrée

🔉 Validations et codes http
• Validation : "L'API vérifie que le titre n'est pas vide et que l'auteur est renseigné avant toute création d'article." 
• Codes HTTP : "L'application retourne un code 404 si l'ID d'un article n'existe pas et un code 400 si le format JSON est incorrect."

🎯 Améliorations futures
Pour la suite, j'aimerais ajouter une authentification JWT pour sécuriser la suppression des articles ou intégrer un système de commentaires.
