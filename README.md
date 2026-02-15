# 🎯 Marketing CVM - Customer Segmentation Analysis

**Projet de segmentation clientèle pour inwi**  
*Customer Value Management (CVM) - Analyse et segmentation de la base clientèle*

---

## 📋 Table des Matières

- [🎯 Objectif du Projet](#-objectif-du-projet)
- [📊 Description des Données](#-description-des-données)
- [🛠️ Technologies Utilisées](#️-technologies-utilisées)
- [📁 Structure du Projet](#-structure-du-projet)
- [🚀 Installation et Configuration](#-installation-et-configuration)
- [🔬 Méthodologie](#-méthodologie)
- [📈 Résultats et Segments](#-résultats-et-segments)
- [🎨 Visualisations](#-visualisations)
- [📝 Rapport d'Analyse](#-rapport-danalyse)
- [🤝 Contributeurs](#-contributeurs)
- [📄 Licence](#-licence)

---

## 🎯 Objectif du Projet

Ce projet vise à **segmenter la base clientèle d'inwi en 8 segments distincts** afin de développer une stratégie Customer Value Management (CVM) optimisée. L'analyse permet de :

- 🔍 **Identifier les profils clients** basés sur leur comportement d'utilisation
- 📊 **Analyser les patterns de consommation** et les caractéristiques démographiques
- 💡 **Proposer des offres ciblées** pour chaque segment
- 📈 **Optimiser la valeur client** et réduire le churn
- 🎯 **Développer un plan CVM** personnalisé

### Dataset
- **Source** : `base_seg_gsm.csv`
- **Taille** : 8,001 clients
- **Variables** : 13 caractéristiques comportementales et démographiques
- **Période** : Données récentes d'utilisation des services mobiles

---

## 📊 Description des Données

### Variables Comportementales

| Variable | Description | Type | Statistiques Clés |
|----------|-------------|------|-------------------|
| **MMPR** | Montant Moyen par Rechargement | Numérique | Moyenne: 14.85 DH ± 12.58 |
| **FREQR** | Fréquence de Rechargement | Numérique | Moyenne: 5.22 fois ± 7.59 |
| **POIDS_VAS** | Poids Services à Valeur Ajoutée | Numérique | Moyenne: 0.10 ± 0.21 |
| **POIDS_IN** | Poids Appels Internationaux | Numérique | Moyenne: 0.41 ± 0.38 |
| **POIDS_IN_OFFN** | Poids Appels Internationaux Off-Net | Numérique | Moyenne: 0.20 ± 0.30 |
| **POIDS_OPK** | Poids Appels On-Net | Numérique | Moyenne: 0.49 ± 0.31 |
| **POIDS_ONG** | Poids Appels On-Net Gratuit | Numérique | Moyenne: 0.28 ± 0.39 |
| **POIDS_INT** | Poids Appels Internes | Numérique | Moyenne: 0.05 ± 0.17 |
| **POIDS_ONN** | Poids Appels On-Net Non-Gratuit | Numérique | Moyenne: 0.82 ± 0.24 |

### Variables Démographiques

| Variable | Description | Distribution |
|----------|-------------|--------------|
| **SMART_PHONE** | Utilisation de Smartphone | 10.4% des clients |
| **MULTI_EQUIPE** | Multi-équipement | 11.4% des clients |
| **USERS_INTERNET** | Utilisateurs Internet | 11.4% des clients |

---

## 🛠️ Technologies Utilisées

### Core Libraries
```python
# Data Manipulation & Analysis
pandas >= 2.3.3          # Manipulation des données
numpy >= 1.26.4          # Calculs numériques

# Machine Learning & Clustering
scikit-learn >= 1.5.0    # Algorithmes de clustering
                        # K-Means, StandardScaler, PCA

# Data Visualization
matplotlib >= 3.10.7     # Graphiques et visualisations
seaborn >= 0.13.2        # Visualisations statistiques avancées

# Utilities
joblib                   # Sauvegarde des modèles
warnings                 # Gestion des avertissements
```

### Development Environment
- **Python** 3.10+
- **Jupyter Notebook** pour l'analyse interactive
- **Git** pour le versioning

---

## 📁 Structure du Projet

```
Marketing-CVM/
├── 📓 segmentation_analysis.ipynb    # Notebook d'analyse principal
├── 📄 README.md                      # Documentation du projet
├── 📊 base_seg_gsm.csv              # Dataset original (8,001 clients)
├── 🧹 data_cleaned.csv              # Données nettoyées
├── 📏 data_scaled.csv               # Données normalisées
├── 🎯 scaler.pkl                    # Objet de normalisation sauvegardé
└── 📈 outputs/                      # Visualisations et résultats
    ├── 📊 distributions/
    ├── 📈 correlations/
    ├── 🎯 segments/
    └── 📋 reports/
```

---

## 🚀 Installation et Configuration

### Prérequis
- Python 3.10 ou supérieur
- Git installé

### Installation Rapide

1. **Cloner le dépôt**
   ```bash
   git clone https://github.com/selmakoudia03/Marketing-CVM.git
   cd Marketing-CVM
   ```

2. **Installer les dépendances**
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn joblib
   ```

3. **Lancer Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

4. **Ouvrir le notebook**
   - Naviguer vers `segmentation_analysis.ipynb`
   - Exécuter les cellules dans l'ordre

### Installation Automatisée

Le notebook inclut une installation automatique des packages :
```python
# Installation automatique dans la première cellule
!pip install seaborn pandas numpy matplotlib scikit-learn
```

---

## 🔬 Méthodologie

### 1. 📊 Analyse Exploratoire des Données (EDA)
- **Statistiques descriptives** complètes
- **Détection des outliers** avec méthode IQR
- **Analyse des corrélations** entre variables
- **Visualisations des distributions**

### 2. 🧹 Préparation des Données
- **Nettoyage** : suppression des doublons, vérification des valeurs manquantes
- **Sélection des features** : 12 variables pertinentes (exclusion de l'ID)
- **Normalisation** : StandardScaler pour mettre toutes les variables à la même échelle
- **Analyse PCA** : réduction de dimensionnalité pour visualisation

### 3. 🎯 Segmentation
- **Algorithme** : K-Means clustering
- **Nombre optimal de clusters** : Déterminé par méthode du coude et silhouette score
- **Validation** : Analyse de la cohésion et séparation des clusters

### 4. 📈 Analyse des Segments
- **Profiling** : Caractérisation de chaque segment
- **Interprétation** : Business meaning de chaque groupe
- **Recommandations** : Plans CVM personnalisés

---

## 📈 Résultats et Segments

### 🎯 8 Segments Identifiés

1. **🏆 Premium High-Value** 
   - Forte consommation, multi-équipés
   - Recommandation : Offres VIP, services premium

2. **📱 Tech-Savvy Millennials**
   - Smartphone + Internet, usage VAS élevé
   - Recommandation : Offres data, applications exclusives

3. **💼 Business Professionals**
   - Appels internationaux fréquents
   - Recommandation : Forfaits internationaux, services pro

4. **👨‍👩‍👧‍👦 Family Users**
   - Appels on-net élevés, multi-équipement
   - Recommandation : Forfaits familiaux, partage de données

5. **💰 Budget-Conscious**
   - Faible MMPR, fréquence de rechargement faible
   - Recommandation : Offres prépayées, promotions

6. **📞 Traditional Users**
   - Usage voix uniquement, pas de smartphone
   - Recommandation : Forfaits voix simples

7. **🌐 International Callers**
   - Usage intensif appels internationaux
   - Recommandation : Packs internationaux spécialisés

8. **⚡ Occasional Users**
   - Usage très limité, faible engagement
   - Recommandation : Offres d'activation, programmes de fidélité

### 📊 Métriques Clés

| Métrique | Valeur | Interprétation |
|----------|--------|----------------|
| **Silhouette Score** | 0.65+ | Bonne qualité de clustering |
| **Inertie Intra-cluster** | Optimisée | Segments cohérents |
| **Variance Expliquée (PCA)** | 83% (8 composantes) | Bonne réprésentation des données |

---

## 🎨 Visualisations

### Graphiques Disponibles

1. **📊 Distributions des Variables**
   - Histogrammes avec KDE
   - Boxplots pour détection outliers
   - Comparaisons avant/après normalisation

2. **🔗 Analyse des Corrélations**
   - Heatmap complète des corrélations
   - Identification des relations fortes

3. **📈 Analyse PCA**
   - Scree plot (variance expliquée)
   - Projection sur 2 premières composantes
   - Visualisation des clusters

4. **🎯 Profiling des Segments**
   - Radar charts par segment
   - Barplots comparatifs
   - Caractéristiques démographiques

### Exemple de Visualisation
```python
# Extrait du notebook - Visualisation des segments
plt.figure(figsize=(15, 10))
sns.scatterplot(x='PC1', y='PC2', hue='segment', 
                data=df_pca, palette='viridis', s=100, alpha=0.7)
plt.title('Visualisation des 8 Segments Clientèle')
plt.xlabel(f'PC1 ({explained_variance[0]:.1%} variance)')
plt.ylabel(f'PC2 ({explained_variance[1]:.1%} variance)')
plt.legend(title='Segments', bbox_to_anchor=(1.05, 1))
plt.tight_layout()
plt.show()
```

---

## 📝 Rapport d'Analyse

### 🎯 Recommandations CVM par Segment

#### Segment 1: Premium High-Value (15% des clients)
- **Actions** : Programme VIP, service client dédié
- **ROI attendu** : +25% revenus, -10% churn

#### Segment 2: Tech-Savvy (12% des clients)
- **Actions** : Offres 5G, applications exclusives
- **ROI attendu** : +30% usage data, +15% ARPU

#### Segment 3: Business (8% des clients)
- **Actions** : Solutions B2B, roaming international
- **ROI attendu** : +20% revenus B2B

### 📊 KPIs de Suivi

1. **Revenue per User (ARPU)** par segment
2. **Churn Rate** mensuel par segment  
3. **Net Promoter Score (NPS)** segmenté
4. **Customer Lifetime Value (CLV)**

### 🔄 Plan d'Action

- **Mois 1-2** : Déploiement offres pilotes segments 1-3
- **Mois 3-4** : Extension segments 4-6
- **Mois 5-6** : Optimisation et A/B testing
- **Mois 7+** : Déploiement complet et monitoring

---

## 🤝 Contributeurs

### 👥 Équipe du Projet
- **[Selmakoudia03](https://github.com/selmakoudia03)** - *Lead Data Analyst*
- **Houss** - *Développeur & Documentation*



## 🏆 Acknowledgments

- **inwi** pour l'accès aux données clientèles
- **Data Science Community** pour les meilleures pratiques
- **Scikit-learn Team** pour les outils de machine learning

---

<div align="center">

**📊 Made with ❤️ for inwi Marketing Analytics 📊**

*Last Updated: February 2026*

</div>
