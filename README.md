\# TP – Optimisation d’une image Docker Node.js
Optimisation d’images Docker à partir d’une application Node.js existante.

\## Application

\- Application Node.js simple (`server.js`)

\- Dépendances gérées avec npm

\- Exposition du port 3000



\## Étape 1 – Image baseline

Une première image Docker a été construite à partir du Dockerfile initial.



\*\*Caractéristiques :\*\*

\- Image de base : `node:latest`

\- Copie du dossier `node\_modules`

\- Installation de dépendances système

\- Une seule image pour build et runtime



\*\*Taille :\*\*

\- `tp-node:baseline` → \*\*1.2 GB\*\*


\## Étape 2 – Suppression de `node\_modules`

Le Dockerfile a été modifié pour ne plus copier `node\_modules`.

Les dépendances sont installées directement dans l’image via `npm install`.



\*\*Taille :\*\*

\- `tp-node:no-node-modules` → \*\*1.16 GB\*\*


\## Étape 3 – Optimisation avancée

Optimisation via :

\- image `node:18-alpine`

\- multi-stage build

\- suppression des outils de build de l’image finale

\- utilisation de `npm ci`



\*\*Taille finale :\*\*

\- `tp-node:optimized` → \*\*138 MB\*\*


\## Comparaison des tailles



| Étape | Image | Taille |

|-----|------|-------|

| Baseline | tp-node:baseline | 1.2 GB |

| Sans node\_modules | tp-node:no-node-modules | 1.16 GB |

| Optimisée | tp-node:optimized | 138 MB |



\## Conclusion

L’utilisation des bonnes pratiques Docker permet de réduire fortement la taille des images

et d’améliorer la performance.



