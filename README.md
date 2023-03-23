# Kubernetes Productions Best Practices
## Pre-requist after deploy your production kubernetes cluster
1. Faire un capacity planing
2. Faire le choix de réseau de votre cluster kubernetes: CNI
3. Faire le sizing de vos nodes qui composeront votre cluster

## Grande étapes pour mettre en place une archicture d'un cluster de production
1. Haute Disponibilité
2. Résiliance
3. Sécurité

## Bonne pratiques pour déployer un cluster de production 
1. Utiliser les taint/toleration pour s’assurer que les pods applications seront deployer uniquement dans les worker nodes et non master nodes.
2. Utiliser les pods Anti Affinity pour s’assurer que les replicas d’un pod seront déployer dans différents worker nodes du cluster
3. Utiliser les pod disruption budgets pour s’assurer d’avoir au moins un pod disponible (pour les application critique)
4. Utiliser les QoS pour que le pod n’aura pas un problème de ressources (pour les applications critiques).
5. Utiliser HPA Keda par exemple pour faire un auto scaling des applications.
6. Utiliser Kubernetes audit logs pour retracer toutes les appels/communications des utilisateurs et applications avec kube api-server
7. Utiliser les livenessProbe et readnessProbe pour faire des testes de vie des containers d’applications
8. Utiliser des stratégies de tagging sur les pods pour mieux identifier et isoler les ressources. 
9. Utiliser les Network Policy pour assurer la segmentation des ressources.
10. Utiliser un Load Balancer pour exposer votre cluster déployer dans un sous-réseau privée. 
11. Utiliser les rbac pour assurer le contrôle des accès des utilisateurs et applications sur les ressources. 
12. Utiliser les limites/requeste pour la limitation des ressources sur les containers
13. Utiliser un gestionnaire de secret pour stocker les secret utiliser dans votre cluster.
14. Utiliser des stratégies de backup/restore pour la sauvegarde de votre cluster.
15. Utiliser des policy en tant que code pour la gouvernance de votre cluster, OPA ou kyverno par exemple
16. Utiliser un quorum de 3 master nodes pour assurer la haute disponibilité de votre cluster.
17. Utiliser un registre privé d’image pour éviter de récupérer des images sur internet mode airgap. 
18. Utiliser au moins deux datacenter pour placer vos nodes, assurer que les replicas des pods se déploient dans des datacenter différents en utilisants les pod Anti Affinity
19. Utiliser le node health check pour faire des testes de vie des nodes.
20. Utiliser un gestionnaire d’utilisateurs comme AD ou LDAP pour authentifier les utilisateurs.
21. Utiliser un nginx ingress controller pour exposer les applications clientes.
22. Utiliser un waf pour protéger ton cluster contre les attaques web.
23. Utiliser les pod Admission Controller et pod security standard pour limiter les actions des containers, mode non privilégiés.
24. Utiliser cis benchmark pour assurer la conformité en terme de sécurité de votre cluster.
25. Utiliser des images non vulnérable avec de très petites tailles.
26. Utiliser prometheus et créer des régles pour le monitoring de votre cluster prometheus + graffana + alertManager.
27. Utiliser fluentbit, fluentd, elasticsearch pour le loggining des applications déployer dans votre cluster.
28. Utiliser un endroit de stockage des logs Splunk par exemple et définir des périodes de retention des logs.
29. Utiliser metricbeat pour récupérer les metric des nodes et applications et créer des tableau de board sur kibana.
30. Utiliser le auto scaling cluster pour ajouter de façon automatique des nodes sur votre cluster(simple avec les cloud provider).
31. Utiliser Terraform pour automatiser le provisionnement de votre infrastructure.
32. Utiliser Helm pour déployer vos applications: Respecter les bonnes pratiques (hooks pre-install, pre-upgrade)
33. Utiliser un storage class (NFS Storage système de stockage) pour pouvoir provisionner des volumes: provisionner des volumes utiliser par Prometheus monitoring exemple 


## Liens utils
https://learnk8s.io/production-best-practices/ 
