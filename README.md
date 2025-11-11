# 🎓 Forstek - Plateforme de Stages pour Étudiants Tunisiens

Plateforme web moderne connectant les étudiants tunisiens avec des opportunités de stages et de mentorat.

## ✨ Fonctionnalités

- 🏠 **Page d'accueil** : Présentation de la plateforme
- 🔐 **Authentification** : Connexion et inscription (Étudiant/Entreprise)
- 💼 **Offres de stage** : Recherche et filtrage d'opportunités
- 📊 **Dashboard** : Suivi des candidatures et statistiques
- 👤 **Profil** : Gestion du profil et compétences
- 💬 **Forum** : Discussions communautaires
- 🎯 **Mentorat** : Connexion avec des mentors professionnels
- ℹ️ **À propos** : Histoire et équipe de Forstek
- 📞 **Contact** : Formulaire de contact et informations

## 🚀 Installation Rapide

### 1️⃣ Cloner le repository
```bash
git clone https://github.com/hazem02b/front-end.git
cd front-end
```

### 2️⃣ Installer les dépendances
```bash
npm install
```
⚠️ **IMPORTANT** : Cette étape est OBLIGATOIRE après chaque clonage !

### 3️⃣ Lancer le serveur
```bash
npm run dev
```

### 4️⃣ Ouvrir dans le navigateur
Visitez : **http://localhost:3000**



## 🛠️ Technologies

- **Next.js 16** (App Router + Turbopack)
- **TypeScript**
- **Tailwind CSS v4**
- **Lucide React** (Icônes)
- **Framer Motion** (Animations)
- **Radix UI** (Composants accessibles)

## 📁 Structure du Projet

```
front-end/
├── app/                    # Pages (Next.js App Router)
│   ├── page.tsx           # Accueil
│   ├── login/             # Connexion
│   ├── register/          # Inscription
│   ├── offres/            # Offres de stage
│   ├── dashboard/         # Tableau de bord
│   ├── profile/           # Profil
│   ├── forum/             # Forum
│   ├── mentorship/        # Mentorat
│   ├── about/             # À propos
│   └── contact/           # Contact
├── components/            # Composants réutilisables
│   ├── Navbar.tsx
│   ├── ModernBackground.tsx
│   └── ui/                # Composants UI
└── public/                # Assets statiques
```

## 📝 Commandes Disponibles

| Commande | Description |
|----------|-------------|
| `npm run dev` | Serveur de développement |
| `npm run build` | Build de production |
| `npm start` | Lancer la production |
| `npm run lint` | Vérifier le code |

## ⚠️ Pourquoi `npm install` est nécessaire ?

Le dossier **`node_modules`** (contenant ~428 packages) n'est **PAS** inclus dans Git car :
- Il pèse environ **500 MB**
- Il est listé dans `.gitignore`
- Il doit être généré localement via `npm install`

**Sans cette étape, le site ne fonctionnera pas !**

## 🐛 Problèmes Courants

### ❌ Le serveur ne démarre pas
```bash
# Solution 1 : Réinstaller les dépendances
rm -rf node_modules package-lock.json
npm install

# Solution 2 : Vérifier Node.js
node --version  # Doit être >= 18.0.0
```

### ❌ Port 3000 occupé
Next.js choisira automatiquement un port libre (3001, 3002...)

### ❌ Erreurs de compilation
Assurez-vous d'avoir bien exécuté `npm install`

## 📖 Documentation Complète

Pour plus de détails, consultez [INSTALLATION.md](./INSTALLATION.md)

## 🔐 Configuration Git (pour les contributeurs)

```bash
git config user.name "Votre Nom"
git config user.email "votre@email.com"
```
