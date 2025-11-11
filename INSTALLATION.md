# 🚀 Guide d'Installation - Forstek Platform

## Prérequis
- Node.js version 18 ou supérieure
- npm ou yarn
- Git

## 📦 Installation après clonage

### 1. Cloner le repository
```bash
git clone https://github.com/hazem02b/front-end.git
cd front-end
```

### 2. Installer les dépendances
```bash
npm install
```
Cette commande va installer tous les packages nécessaires (Next.js, React, Tailwind, Lucide Icons, etc.)

### 3. Lancer le serveur de développement
```bash
npm run dev
```

### 4. Ouvrir dans le navigateur
Le site sera accessible sur : **http://localhost:3000**

---

## 🔧 Commandes disponibles

| Commande | Description |
|----------|-------------|
| `npm run dev` | Lance le serveur de développement |
| `npm run build` | Créer une version de production |
| `npm start` | Lance la version de production |
| `npm run lint` | Vérifier le code |

---

## 📁 Structure du projet

```
front-end/
├── app/                    # Pages Next.js (App Router)
│   ├── page.tsx           # Page d'accueil
│   ├── login/             # Page connexion
│   ├── register/          # Page inscription
│   ├── offres/            # Offres de stage
│   ├── dashboard/         # Tableau de bord
│   ├── profile/           # Profil utilisateur
│   ├── forum/             # Forum communautaire
│   ├── mentorship/        # Mentorat
│   ├── about/             # À propos
│   └── contact/           # Contact
├── components/            # Composants réutilisables
│   ├── Navbar.tsx
│   ├── ModernBackground.tsx
│   ├── FloatingParticles.tsx
│   └── ui/                # Composants UI
├── public/                # Assets statiques
├── package.json           # Dépendances
└── tailwind.config.ts     # Configuration Tailwind

```

---

## ⚠️ Problèmes courants

### Le serveur ne démarre pas
- Vérifiez que Node.js est installé : `node --version`
- Supprimez `node_modules` et réinstallez : `rm -rf node_modules && npm install`
- Vérifiez qu'aucun autre processus n'utilise le port 3000

### Erreurs de compilation
- Assurez-vous d'avoir lancé `npm install` 
- Vérifiez que toutes les dépendances sont installées

### Port 3000 déjà utilisé
Next.js choisira automatiquement un autre port (3001, 3002, etc.)

---

## 🎨 Technologies utilisées

- **Next.js 16** - Framework React
- **TypeScript** - Typage statique
- **Tailwind CSS v4** - Styling
- **Lucide React** - Icônes
- **Framer Motion** - Animations
- **Radix UI** - Composants accessibles

---

## 📝 Notes importantes

⚠️ **Le dossier `node_modules` n'est PAS inclus dans le repository Git** (il est dans `.gitignore`)

C'est pourquoi vous DEVEZ exécuter `npm install` après chaque clonage !

Ce dossier contient ~428 packages et pèse environ 500 MB.

---

## 🔐 Configuration Git (optionnel)

Si vous voulez contribuer :
```bash
git config user.name "Votre Nom"
git config user.email "votre.email@example.com"
```

---

## 📞 Support

Pour toute question : contact@forstek.tn
