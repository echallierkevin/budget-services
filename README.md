# 📊 Budget Services / Projets

Une mini-application **HTML + JS** pour suivre les **budgets** par **service** et **projets**, et y saisir des **dépenses**.  
Elle permet de visualiser en temps réel :

- Le **budget global** et par service  
- Les **dépenses cumulées**  
- Le **reste disponible**  
- Le **% utilisé** avec statut (✅ OK · ⚠️ À surveiller · ❌ Dépassement)

---

## 🚀 Fonctionnalités principales
- **Vue globale** (`index.html`) : aperçu des services + panneau détail.  
- **Vue service** (`dsi.html`, `rh.html`, …) : création/modification de projets et saisie de dépenses.  
- **Historique filtrable** : voir toutes les dépenses d’un service avec tri et recherche.  
- **Export / Import JSON** : sauvegarde ou restauration manuelle des données.

---

## 🗂️ Où sont stockées les données ?
Toutes les données sont centralisées dans un **fichier JSON** (`budgets.json`).  
Cela permet à **tous les utilisateurs** de partager la même base de données.

> ⚠️ Avec **GitHub Pages**, l’écriture n’est pas permise (`PUT` bloqué).  
> - En mode **lecture seule**, vous pouvez quand même afficher les budgets.  
> - Pour mettre à jour : utilisez le menu **⋯ Outils → Exporter JSON**, puis remplacez manuellement le fichier sur votre hébergement.  
> - Pour une vraie écriture partagée, utilisez un serveur acceptant `PUT` (ex. S3, backend léger, etc.).

---

## 🔧 Configuration
Dans chaque page (`index.html`, `dsi.html`, etc.), ajustez l’URL du JSON :

```js
const STORE_URL = "https://votre-domaine.tld/chemin/budgets.json";
```

---

## 📄 Exemple de structure JSON
```json
{
  "years": {
    "2025": {
      "year": 2025,
      "services": {
        "DSI": {
          "projects": [
            {
              "id": "uuid-123",
              "name": "Projet ERP",
              "budget": 10000,
              "expenses": [
                { "amount": 2500, "date": "2025-02-10", "createdAt": "2025-02-10T09:30:00Z" }
              ]
            }
          ]
        }
      }
    }
  }
}
```

---

✦ Développé pour un usage simple, moderne et sans dépendances externes.
