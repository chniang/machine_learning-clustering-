📊 Segmentation de Clients - Clustering sur Données de Cartes de Crédit
Ce projet applique des techniques de machine learning non supervisé (clustering) pour segmenter les détenteurs de cartes de crédit à partir d’un jeu de données issu de Kaggle. Il s'agit de regrouper les clients selon leurs comportements d'utilisation (achats, paiements, limites de crédit, etc.) afin d'aider à définir une stratégie marketing ciblée.

📁 Contexte du Projet
L'objectif est de développer une segmentation client en exploitant les données comportementales de 9000 utilisateurs actifs de cartes de crédit sur une période de 6 mois. Le projet suit une approche pas à pas :

Exploration de données

Prétraitement (nettoyage, normalisation…)

Clustering hiérarchique (2 features)

Clustering K-means

Choix optimal du nombre de clusters (méthode du coude)

Interprétation des résultats

📌 Source du Dataset
Dataset original : Kaggle
Aperçu du dataset :


🧾 Description des colonnes principales
Colonne	Description
CUST_ID	ID client unique (catégorique, à supprimer pour le clustering)
BALANCE_FREQUENCY	Fréquence de mise à jour du solde (0 à 1)
PURCHASES	Montant total des achats
CASH_ADVANCE	Avances d’argent obtenues par le client
CREDIT_LIMIT	Limite de crédit autorisée
PAYMENTS	Montant total des paiements effectués

🧪 Librairies utilisées
pandas, numpy : Manipulation des données

matplotlib, seaborn : Visualisation

sklearn.preprocessing.StandardScaler : Normalisation

sklearn.cluster.KMeans, AgglomerativeClustering : Clustering

scipy.cluster.hierarchy : Dendrogramme pour hiérarchique

⚙️ Étapes de traitement
1. 💾 Chargement et exploration des données
Chargement avec pandas

Inspection des types, valeurs nulles, statistiques descriptives

Suppression de la colonne CUST_ID

2. 🧹 Nettoyage
Détection de valeurs manquantes

Remplacement de la seule valeur manquante (CREDIT_LIMIT) par la moyenne

3. 📏 Normalisation
Utilisation de StandardScaler pour standardiser toutes les colonnes (moyenne 0, écart-type 1)

4. 🔗 Clustering hiérarchique
Sélection de deux features : PURCHASES et CREDIT_LIMIT

Visualisation du dendrogramme (méthode ward)

Application de AgglomerativeClustering avec 4 clusters

Visualisation finale sur un nuage de points

5. 🎯 K-Means Clustering
Application de l’algorithme KMeans sur les données normalisées

Visualisation avec un scatterplot

Détermination du meilleur K via la méthode du coude (distorsion vs nombre de clusters)

📈 Résultats & Interprétation
Les clusters montrent des groupes de clients avec des comportements distincts en termes d’achats, d’avances, de paiements et de limite de crédit.

Le modèle peut servir à cibler des offres marketing spécifiques : clients très actifs, clients prudents, utilisateurs de crédits fréquents…

📂 Structure du Projet
bash
Copier
Modifier
credit-card-clustering/
│
├── README.md
├── credit_card_clustering.ipynb  # Notebook complet
├── data/
│   └── CC_GENERAL.csv            # Dataset (à télécharger depuis Kaggle)
├── images/
│   ├── dendrogram.png
│   └── elbow_curve.png
🚀 Pour commencer
Télécharger le dataset ici

Placer le fichier CC_GENERAL.csv dans le dossier data/

Lancer le notebook credit_card_clustering.ipynb

📚 Mots clés
Clustering, KMeans, Hierarchical Clustering, Standardisation, Segmentation client, Machine Learning, Python, scikit-learn, Credit Card Dataset

🙌 Auteur
Projet réalisé par [Cheikh Niang] dans le cadre d’un exercice de machine learning non supervisé.
