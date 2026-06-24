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

verification via le fichier suivant

https://github.com/epierret/jdupont-Rbac/blob/main/VerifRbac.jpg

Pourquoi est-il dangereux d'attribuer le rôle cluster-admin à tous les utilisateurs ?

Quelle différence existe-t-il entre un Role et un ClusterRole ?

un role et namespaced , valable uniquement dans un namespace , contrairement au clusterole qui s'applique à tout le cluster.

Quelle différence existe-t-il entre les verbes update et patch ?

update permet de mdofier l'integralité de l'objet tandis que patch permet de scale les replicas par exemple.

Pourquoi l'accès aux logs doit-il être explicitement autorisé dans RBAC ?

car les logs sont une sous ressources de kubernetes 
Quel principe de sécurité est appliqué lorsqu'on n'accorde que les permissions strictement nécessaires à un utilisateur ?

Least privilege
Quels risques pourraient apparaître si un développeur obtenait un accès en lecture aux Secrets du namespace production ?

si le secret contient des données admins il pourrait usurper un id et compromettre le cluster
Dans quel cas serait-il pertinent d'utiliser un ClusterRole pour cette équipe ?

par exemple s'ils doivent gerer des pv ou des csr(cluster-scoped, ou s'ils doivent donner des droits cross-namespaced.





