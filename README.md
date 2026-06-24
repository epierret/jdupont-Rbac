# jdupont-Rbac

# RBAC - jdupont

Pour ce lab la solution recommandée est de créer un Role (définissant les autorisations) et un RoleBinding (liant ce rôle à l'utilisateur) au sein du namespace production.

Ce dépôt contient les fichiers de configuration RBAC pour l'utilisateur `jdupont` dans le namespace `production`.
 
## Fichiers

- `role.yaml` : Définition du Role `jdupont-role`
- `rolebinding.yaml` : RoleBinding liant `jdupont` au rôle
- `csr.yaml` : CertificateSigningRequest pour la génération du certificat

## Utilisation

```bash
kubectl apply -f role.yaml
kubectl apply -f rolebinding.yaml

verification

<img width="539" height="241" alt="image" src="https://github.com/user-attachments/assets/14e9659f-cf97-4008-aa47-21e064c3d6dd" />





