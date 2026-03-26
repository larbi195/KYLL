## Politique Mobile
Objectif : protéger données et secrets, conformité RGPD/PSD2/PCI DSS, sécuriser communications et API.
### 1. Secrets et Endpoints
- Interdits dans le code (strings.xml, BuildConfig).
- Clés API et Firebase → stockées sur serveur sécurisé et Firebase App Check.
- URLs non exposées, certificate pinning obligatoire.
### 2. Communication
- Pas de HTTP (usesCleartextTraffic=false).
- TLS ≥1.2, pas de TrustManager personnalisé.
### 3. Debug et DevTools
- Supprimer DevSettings et debug JS en production.
- Strings de debug conditionnées à BuildConfig.DEBUG.
### 4. Permissions & Composants
- Moindre privilège.
- Composants exportés (android:exported=false) sauf justification.
- Validation des intents et signature des composants.
### 5. Stockage
- EncryptedSharedPreferences / AES-256.
- android:allowBackup=false.
### 6. Authentification & Sessions
- Timeout 5 min.
- Vérification appelant pour RN modules.
- Biometric prompt pour actions sensibles.
### 7. Tests et Correctifs
- MobSF score >80, 0 vulnérabilités critiques.
- Tests d’intrusion semestriels.
- Correctifs rapides selon criticité (critique <24h, élevé <7j).
### 8. Firebase & Notifications
- Firebase sécurisé, App Check activé, accès monitoré.
- Push notifications : FCM, identifiants sécurisés, pas de Pushwoosh exposé.
### 9. Usage Utilisateur
- Mises à jour immédiates.
- Appareil sécurisé (mot de passe, pas de root/jailbreak).
Wi-Fi public → VPN recommandé.
