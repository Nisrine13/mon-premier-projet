# Diagramme de Cas d'Utilisation - PhoboApp  
*Documentation détaillée des rôles et fonctionnalités*  

---

## **1. Apprenant non connecté (Visiteur)**  
| **Description sommaire**       |                                                                 |
|-------------------------------|-----------------------------------------------------------------|
| **Titre**                     | E-learning (Actions Visiteur)                                   |
| **But**                       | Explorer la plateforme sans compte utilisateur.                 |
| **Acteurs**                   | Apprenant non connecté                                          |

| **Enchaînements**             |                                                                 |
|-------------------------------|-----------------------------------------------------------------|
| **Nominal**                   | 1. Le visiteur consulte la liste des cours. <br>2. Le système affiche les extraits disponibles. <br>3. Le visiteur lit un extrait. |
| **Alternatif**                | Tentative d'accès à une fonction restreinte (ex : QCM). <br>→ Le système redirige vers la page de connexion. |
| **Erreur**                    | Contenu introuvable. <br>→ Le système affiche un message d'erreur. |

---

## **2. Apprenant connecté**  
| **Description sommaire**       |                                                                 |
|-------------------------------|-----------------------------------------------------------------|
| **Titre**                     | E-learning (Actions Utilisateur)                                |
| **But**                       | Interagir avec les cours et suivre sa progression.              |
| **Acteurs**                   | Apprenant connecté                                              |

| **Enchaînements**             |                                                                 |
|-------------------------------|-----------------------------------------------------------------|
| **Nominal**                   | 1. L'utilisateur répond à un QCM. <br>2. Le système calcule le score. <br>3. Le score est enregistré dans son profil. |
| **Alternatif**                | Échec au QCM. <br>→ Le système propose de refaire les questions ratées. |
| **Erreur**                    | Problème de sauvegarde. <br>→ Le système notifie l'utilisateur.  |

---

## **3. Formateur**  
| **Description sommaire**       |                                                                 |
|-------------------------------|-----------------------------------------------------------------|
| **Titre**                     | E-learning (Gestion Cours)                                      |
| **But**                       | Créer et gérer des cours, interagir avec les apprenants.        |
| **Acteurs**                   | Formateur                                                       |

| **Enchaînements**             |                                                                 |
|-------------------------------|-----------------------------------------------------------------|
| **Nominal**                   | 1. Le formateur crée un chapitre. <br>2. Le système valide le format. <br>3. Le chapitre est publié. |
| **Alternatif**                | Champ obligatoire manquant. <br>→ Le système bloque la publication. |
| **Erreur**                    | Conflit de version. <br>→ Le système demande une résolution manuelle. |

---

## **4. Administrateur**  
| **Description sommaire**       |                                                                 |
|-------------------------------|-----------------------------------------------------------------|
| **Titre**                     | E-learning (Administration)                                     |
| **But**                       | Superviser la plateforme et gérer les comptes/cours.            |
| **Acteurs**                   | Administrateur                                                  |

| **Enchaînements**             |                                                                 |
|-------------------------------|-----------------------------------------------------------------|
| **Nominal**                   | 1. L'admin désactive un compte. <br>2. Le système met à jour la base de données. <br>3. Un email est envoyé à l'utilisateur. |
| **Alternatif**                | Compte inexistant. <br>→ Le système affiche un avertissement.   |
| **Erreur**                    | Permission refusée. <br>→ Le système journalise l'incident.    |

---

### **Annotations**  
- `<<include>>` : "S'inscrire" inclut la vérification par email.  
- `<<extend>>` : "Voir son score" étend "Répondre à un QCM".  
