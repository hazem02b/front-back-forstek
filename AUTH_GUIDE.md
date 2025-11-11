# 🔐 Système d'Authentification - Guide de Test

## ✅ Fonctionnalités Implémentées

### 1. **Inscription (Register)**
- Choix du type de compte (Étudiant / Entreprise)
- Validation du mot de passe (minimum 6 caractères)
- Vérification de correspondance des mots de passe
- Détection des emails déjà utilisés
- Stockage sécurisé dans localStorage
- Connexion automatique après inscription

### 2. **Connexion (Login)**
- Authentification par email/mot de passe
- Option "Se souvenir de moi"
- Messages d'erreur clairs
- Redirection automatique vers le dashboard

### 3. **Gestion de Session**
- État d'authentification persistant (survit au rechargement)
- Context React global (AuthContext)
- Protection des routes (ProtectedRoute component)
- Déconnexion fonctionnelle

---

## 🧪 Comment Tester

### Test 1 : Inscription d'un nouvel utilisateur

1. Allez sur http://localhost:3000
2. Cliquez sur "Commencer" ou "S'inscrire"
3. Sélectionnez "Étudiant" ou "Entreprise"
4. Remplissez le formulaire :
   - **Nom** : Votre nom
   - **Email** : test@example.com
   - **Mot de passe** : test123
   - **Confirmation** : test123
5. Cochez "J'accepte les conditions"
6. Cliquez sur "Créer mon compte"

**Résultat attendu** : Redirection vers /dashboard avec l'utilisateur connecté

---

### Test 2 : Connexion avec un compte existant

1. Allez sur http://localhost:3000/login
2. Utilisez les mêmes identifiants créés avant :
   - **Email** : test@example.com
   - **Mot de passe** : test123
3. Cliquez sur "Se connecter"

**Résultat attendu** : Connexion réussie et accès au dashboard

---

### Test 3 : Erreurs d'authentification

**Test 3a - Mauvais mot de passe :**
1. Allez sur /login
2. Email correct + mauvais mot de passe
3. **Résultat** : Message d'erreur "Email ou mot de passe incorrect"

**Test 3b - Email déjà utilisé :**
1. Allez sur /register
2. Utilisez un email déjà enregistré
3. **Résultat** : Message "Cet email est déjà utilisé"

**Test 3c - Mots de passe non correspondants :**
1. Allez sur /register
2. Entrez des mots de passe différents
3. **Résultat** : Message "Les mots de passe ne correspondent pas"

---

### Test 4 : Persistance de session

1. Connectez-vous
2. Rechargez la page (F5)

**Résultat attendu** : Vous restez connecté

---

### Test 5 : Protection des routes

1. **Sans être connecté**, essayez d'accéder à :
   - http://localhost:3000/dashboard
   - http://localhost:3000/profile
   - http://localhost:3000/offres

**Résultat actuel** : Pages accessibles (protection à ajouter)
**Résultat futur** : Redirection vers /login

---

## 💾 Données Stockées

Les données sont stockées dans **localStorage** :

- `users` : Liste de tous les utilisateurs inscrits
- `user` : Utilisateur actuellement connecté
- `isAuthenticated` : État de connexion

### Voir les données stockées

Ouvrez la console du navigateur (F12) et tapez :

```javascript
// Voir tous les utilisateurs
JSON.parse(localStorage.getItem('users'))

// Voir l'utilisateur connecté
JSON.parse(localStorage.getItem('user'))

// Vérifier l'état de connexion
localStorage.getItem('isAuthenticated')
```

### Réinitialiser les données

```javascript
localStorage.clear()
```

---

## 📦 Composants Créés

### 1. `contexts/AuthContext.tsx`
Context React pour la gestion globale de l'authentification :
- `login(email, password)` : Connexion
- `register(email, password, name, type)` : Inscription
- `logout()` : Déconnexion
- `updateProfile(data)` : Mise à jour du profil
- `user` : Utilisateur connecté
- `isAuthenticated` : État de connexion

### 2. `components/ProtectedRoute.tsx`
Composant pour protéger les routes (à implémenter dans les pages)

### 3. Pages Mises à Jour
- `app/login/page.tsx` : Connexion fonctionnelle
- `app/register/page.tsx` : Inscription fonctionnelle
- `app/layout.tsx` : Intégration de l'AuthProvider

---

## 🔄 Prochaines Étapes

- [ ] Ajouter ProtectedRoute au Dashboard et autres pages
- [ ] Implémenter l'authentification 2FA
- [ ] Ajouter un bouton de déconnexion dans la navigation
- [ ] Mettre à jour la page d'accueil avec le design complet
- [ ] Créer la page Roadmaps
- [ ] Améliorer les pages existantes avec des données réelles

---

## 🐛 Débug

Si vous rencontrez des problèmes :

1. **Ouvrez la console** (F12)
2. **Vérifiez localStorage** : `localStorage.getItem('users')`
3. **Vérifiez les erreurs** dans l'onglet Console
4. **Réinitialisez** : `localStorage.clear()` puis rechargez

---

## 📝 Notes Techniques

- **Pas de base de données** : Utilise localStorage (données perdues si cache vidé)
- **Pas de cryptage** : Mots de passe en clair (OK pour développement)
- **Production** : Remplacer par une vraie API (Firebase, Supabase, etc.)
