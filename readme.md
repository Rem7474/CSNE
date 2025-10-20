# 🛡️ CSNE - Quiz de Révision

Application web moderne de révision pour la certification **CSNE (Certified Stormshield Network Expert)**.

🌐 **Accès direct** : [csne.remcorp.fr](http://csne.remcorp.fr)

## 📋 Description

Application de quiz interactive permettant de réviser les connaissances nécessaires pour réussir l'examen de certification Stormshield Network Expert. L'application propose 94 questions couvrant tous les aspects de la sécurité réseau Stormshield.

## ✨ Fonctionnalités

- 🎯 **Quiz personnalisable** : Choisissez le nombre de questions (1 à 94)
- 🔀 **Questions aléatoires** : Ordre des questions mélangé à chaque session
- 📊 **Barre de progression** : Suivez votre avancement en temps réel
- ✅ **Validation instantanée** : Feedback immédiat sur vos réponses
- 📈 **Scores détaillés** : Statistiques complètes à la fin du quiz
- 🎨 **Design moderne** : Interface élégante avec animations fluides
- 📱 **Responsive** : Compatible mobile, tablette et desktop
- 🌐 **100% hors ligne** : Fonctionne sans connexion internet

## 🚀 Installation

1. **Clonez le dépôt** :
   ```bash
   git clone https://github.com/Rem7474/CSNE.git
   ```

2. **Accédez au répertoire** :
   ```bash
   cd CSNE
   ```

3. **Ouvrez le projet** :
   - Ouvrez simplement `index.html` dans votre navigateur
   - OU utilisez un serveur local (recommandé) :
     ```bash
     # Avec Python
     python -m http.server 8000
     
     # Avec PHP
     php -S localhost:8000
     
     # Avec VS Code
     # Installez l'extension "Live Server" et clic droit > "Open with Live Server"
     ```

## 🎮 Utilisation

1. **Lancez l'application** en ouvrant `index.html`
2. **Sélectionnez le nombre de questions** que vous souhaitez
3. **Cliquez sur "Commencer le quiz"**
4. **Répondez aux questions** en cliquant sur les réponses
5. **Validez** chaque réponse avec le bouton "Valider"
6. **Consultez vos résultats** à la fin du quiz
7. **Recommencez** autant de fois que nécessaire !

## 📁 Structure du projet

```
CSNE/
├── index.html              # Page principale
├── style.css               # Styles modernes avec CSS variables
├── script.js               # Logique JavaScript (ES6+)
├── questions.json          # Base de données de 94 questions
├── favicon.svg             # Icône du site
├── readme.md              # Documentation
└── .github/
    └── copilot-instructions.md  # Guide pour les agents IA
```

## 🛠️ Technologies utilisées

- **HTML5** : Structure sémantique moderne
- **CSS3** : 
  - CSS Variables (thématisation)
  - Flexbox (mise en page responsive)
  - Animations et transitions
  - Glassmorphism
  - Gradients
- **JavaScript (ES6+)** :
  - Async/await
  - Template literals
  - Arrow functions
  - Fetch API
  - Modern DOM manipulation
- **Google Fonts** : Police Inter (400, 600, 700, 800)

## 🎨 Caractéristiques du design

- **Palette de couleurs** : Dégradé bleu/violet moderne
- **Typographie** : Inter (Google Fonts)
- **Animations** : Transitions fluides et effets hover
- **Responsive** : Breakpoint à 768px pour mobile
- **Accessibilité** : Labels, contraste, navigation clavier

## 📊 Barème de notation

- 🏆 **≥ 90%** : Excellent !
- ⭐ **≥ 75%** : Très bien !
- ✅ **≥ 60%** : Bien joué !
- 💪 **< 60%** : Continuez à réviser !

## 🔧 Développement

### Ajouter des questions

Éditez le fichier `questions.json` :

```json
{
  "id": 95,
  "question": "Votre question ici ?",
  "type": "text",
  "answers": [
    "Réponse 1",
    "Réponse 2",
    "Réponse 3"
  ],
  "correctAnswers": [0, 2],
  "image": null
}
```

- `id` : Identifiant unique
- `question` : Texte de la question
- `type` : "text" (ou "image" si une image est incluse)
- `answers` : Tableau des réponses possibles
- `correctAnswers` : Indices des bonnes réponses (0-based)
- `image` : URL de l'image ou `null`

### Personnaliser le style

Modifiez les variables CSS dans `:root` (fichier `style.css`) :

```css
:root {
    --primary-color: #2563eb;
    --success-color: #10b981;
    --error-color: #ef4444;
    /* ... autres variables */
}
```

## 📝 Licence

Ce projet est libre d'utilisation pour la préparation à la certification CSNE.

## 👨‍💻 Auteur

**Rémy Cuvelier** - 2025

## 🤝 Contribution

Les contributions sont les bienvenues ! N'hésitez pas à :
1. Fork le projet
2. Créer une branche (`git checkout -b feature/amelioration`)
3. Commiter vos changements (`git commit -m 'Ajout d'une fonctionnalité'`)
4. Pusher vers la branche (`git push origin feature/amelioration`)
5. Ouvrir une Pull Request

## 📌 Notes

- **Aucune dépendance** : Le projet fonctionne avec du JavaScript vanilla
- **Pas de build** : Aucune compilation nécessaire
- **Hébergement simple** : Peut être déployé sur GitHub Pages, Netlify, Vercel, etc.
- **UTF-8** : Encodage moderne pour les caractères français

---

*Bonne révision pour votre certification CSNE ! 🎓*