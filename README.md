# 🎓 SmartSuivi Étudiant

Application web intelligente de suivi des étudiants, développée en **Java/Jakarta EE** et intégrant un service de **Machine Learning (Python/Flask)** pour la prédiction du niveau académique des étudiants.

---

## 📋 Description du projet

SmartSuivi permet aux enseignants et aux établissements de suivre le profil des étudiants
(temps d'étude, absences, moyenne, sommeil, participation, utilisation du téléphone)
et d'obtenir automatiquement une **prédiction du niveau de l'étudiant** grâce à un modèle
d'apprentissage automatique entraîné sur un dataset réel.

Le projet combine une **application web Java EE (MVC)** avec un **microservice Flask**
exposant une API REST de prédiction.

---

## 🚀 Fonctionnalités

- 🔐 Système d'authentification complet (inscription / connexion, gestion des sessions)
- 📊 Tableau de bord étudiant
- 👤 Consultation et modification du profil étudiant
- 🤖 **Prédiction intelligente du niveau académique** via un modèle Random Forest
- 🗄️ Persistance des données dans une base MySQL
- 🔗 Communication Java ↔ Python via une **API REST (JSON)**

---

## 🛠️ Technologies utilisées

| Composant | Technologies |
| --- | --- |
| Backend Web | Java / Jakarta EE (Servlets, JSP, MVC, JDBC) |
| Base de données | MySQL |
| Machine Learning | Python, scikit-learn, pandas, numpy |
| API ML | Flask (REST API) |
| Modèle ML | Random Forest Classifier (100 arbres) |
| Conception | UML (cas d'utilisation, classes, séquence, activité) |

---

## 🧠 Partie Machine Learning

- **Dataset** : profils étudiants (temps d'étude, absences, moyenne, sommeil, participation, utilisation du téléphone)
- **Algorithme** : Random Forest Classifier
- **Évaluation** : accuracy, precision, recall, F1-score, matrice de confusion
- **Pipeline** : `train_model.py` → entraînement + sauvegarde du modèle (`joblib`)
- **API de prédiction** : `POST /predict` (Flask) retournant le niveau prédit en JSON

```python
# Exemple d'appel à l'API
POST http://localhost:5000/predict
{
  "TempsEtude": 5.5,
  "Absences": 2,
  "MoyenneSemestre": 14.0,
  "Sommeil": 7.5,
  "Participation": 8.0,
  "UtilisationTelephone": 3.0
}
# Réponse : {"niveau": "..."}
```

---

## ⚙️ Installation & Exécution

### 1. Base de données

```bash
mysql -u root -p < smartsuivi_db.sql
```

### 2. Microservice ML (Flask)

```bash
cd machine_learning
pip install -r requirements.txt
python train_model.py   # entraîne le modèle
python app.py           # lance l'API sur le port 5000
```

### 3. Application Java EE

- Déployer le projet sur **Apache Tomcat**
- Configurer le connecteur **MySQL JDBC**

---

## 📐 Conception UML

- Diagramme de cas d'utilisation
- Diagramme de classes
- Diagramme de séquence
- Diagramme d'activité

---

## 👩‍💻 Auteur

**Zineb DABDAB** — Licence MIACSD (Mathématiques, Informatique Appliquée, Cybersécurité et Données)
Université Sultan Moulay Slimane, Béni Mellal

---

*Mini-projet académique — Licence MIACSD*
