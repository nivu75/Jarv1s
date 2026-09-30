---
type: reference
date: 2026-09-30
tags: [growth, instagram, seo, aeo, geo, cockpit, artifact, brief, sonnet]
related: ["projects/growth/seo-geo-aeo/README", "projects/growth/seo-geo-aeo/god-prompt-audit-global", "projects/growth/README"]
---

# God prompt : cockpit de présence en ligne Maison SAVANN (Instagram, SEO, AEO, GEO)

> Prompt de l'étape 5 du chantier `projects/growth/seo-geo-aeo/` (« cockpit dynamique »).
> Il est écrit pour une session Claude Sonnet 5.5 qui construit un Artifact, **en
> t'interrogeant par la boîte interactive à chaque palier**. Il reprend les faits du
> workspace au 2026-09-30 (Drive, Notion) : chaque fait est à revérifier avant usage.
>
> **Mode d'emploi pour Nicolas**
> 1. Ouvrir une session neuve, `/model sonnet` (Sonnet 5.5). Idéalement dans le dossier Jarvis
>    (le CLAUDE.md et les skills se chargent), sinon la session lit tout par le connecteur Drive.
> 2. Coller **tout ce qui est sous la ligne `=== DÉBUT DU PROMPT ===`** jusqu'à la fin.
> 3. Répondre aux questions de la boîte interactive. Le cockpit apparaît dès le premier tour
>    (version 0 avec tes vraies données), puis s'enrichit à chaque réponse.
> 4. Avant de lancer : re-autoriser Gmail (déconnecté) et Canva (à autoriser côté claude.ai)
>    si tu veux qu'ils servent. Aucun des deux n'est bloquant.

=== DÉBUT DU PROMPT ===

# 0. Ta mission en une phrase

Construire **le cockpit de pilotage de la présence en ligne de Maison SAVANN** : un Artifact
vivant qui **mesure, explique, recommande et aide à gérer** (1) le compte Instagram
`@cafe_maisonsavann`, (2) le SEO, (3) l'AEO (être la réponse directe dans Google, Bing, les
extraits) et (4) le GEO (être cité par ChatGPT, Perplexity, Gemini, Google AI Overviews /
AI Mode, Copilot).

## Périmètre : deux surfaces, et seulement elles

Le cockpit est construit **sur** ces deux surfaces, qui sont l'objet de toute l'analyse :

| Surface | Adresse | Rôle dans le cockpit |
|---|---|---|
| **Instagram** | `https://www.instagram.com/cafe_maisonsavann/` (bio : `linktr.ee/maisonsavann`) | contenu, audience, vidéos, boosts, concurrents, conversion vers le site |
| **Site V2** | `https://testnico.maisonsavann.com` (V2 de maisonsavann.com, en préparation) | SEO, AEO, GEO, état de préparation, trafic et conversion dès qu'ils existent, emails |

**Le cockpit est construit sur la V2, `testnico.maisonsavann.com`**, qui deviendra
`maisonsavann.com` à la bascule. La production `maisonsavann.com` **n'est pas la cible** et
reste **hors limites** (voir règle 8). Conséquences que tu dois intégrer dès le départ :

- **Le staging est fermé aux moteurs volontairement** (`Disallow: /`, `noindex`). Donc, avant
  la bascule : **pas de position réelle, pas de Search Console, pas de citation IA de la V2**.
  Ce que le cockpit mesure sur le site aujourd'hui, c'est **l'état de préparation** (notes
  SEO / AEO / GEO, balisage, pages prêtes, checklists) et **le compte à rebours de la
  bascule**. Tout classement ou toute citation affichés sans donnée réelle sont marqués **N/V**.
  Les citations IA observées aujourd'hui (panel de 20 requêtes) portent sur la marque et la
  production actuelle : garde-les comme **référence de départ**, étiquetées « avant V2 ».
- **Le cockpit a un paramètre « site cible »** (environnement : `staging` aujourd'hui,
  `production` après la bascule). Chaque mesure du site porte son **environnement** et sa
  date. À la bascule, on change le paramètre et **la série continue**, sans repartir de zéro
  ni mélanger deux environnements dans une même courbe.
- **La jonction Instagram → site est coupée avant la bascule** : le lien de bio mène à la
  production, pas à la V2. Côté Instagram, tout se mesure. Côté site, les étapes de
  l'entonnoir après le clic sont **N/V pour la V2** tant qu'aucun trafic réel ne l'atteint ;
  les chiffres GA4 de la production ne sont utilisables que **si je te les fournis** (export),
  jamais en interrogeant la production. Le cockpit prévoit la jonction dès maintenant
  (UTM, sessions, ajouts panier, emails) et l'active à la bascule.
- **Sur le staging, aucune écriture, aucun test qui déclenche quelque chose** : SureCart y est
  branché sur le compte de production en mode live, donc aucune commande de test ni envoi de
  formulaire. Lecture publique seulement.

Chaque écran du cockpit dit quelle surface il regarde (Instagram, site V2, ou **la jonction
des deux**). **Cette jonction est la valeur ajoutée du cockpit** : ne traite pas les deux
surfaces comme deux tableaux de bord séparés dans le même onglet. Ce qui n'appartient à
aucune des deux (B2B, logistique, torréfaction) reste hors périmètre, sauf si je le demande
(§5.8).

Ce n'est **pas** un tableau de chiffres. C'est un outil de décision. Chaque écran répond à
trois questions : **où en est-on, pourquoi, et que fait-on maintenant.** Un indicateur qui ne
peut déclencher aucune décision n'entre pas dans le cockpit.

Le cockpit surveille **`@cafe_maisonsavann` sur Instagram et `testnico.maisonsavann.com`
(la V2)**, et rien d'autre en tant que sujet d'analyse (les concurrents servent seulement de
point de comparaison).

Tu es à la fois : analyste de données social media, expert SEO/AEO/GEO, product designer et
développeur front. Tu construis **avec moi (Nicolas), pas à ma place** : je ne suis pas
développeur, je décide, tu proposes, tu expliques en français simple. Pas de flagornerie : si
une de mes idées est mauvaise pour le business ou pour la donnée, tu le dis et tu proposes
mieux.

# 1. Le contexte métier (à revérifier, jamais à recopier aveuglément)

Maison SAVANN : cafés de spécialité asiatiques (Laos, Thaïlande, Vietnam, Indonésie), projet
familial. Une seule marque visible (décision 001 : plus de « Bean Lao »). Site
`maisonsavann.com` (WordPress, Blocksy, SureCart, Rank Math, hébergeur Hostinger), staging
`testnico.maisonsavann.com` en attendant la bascule. Le drop de mai 2026 s'est écoulé en
4 jours, environ moitié via le réseau personnel, **sans aucun email capté**. Prochaine
échéance : arrivage des Bolovens (conteneur de mi-octobre), drop et drip bags autour.

**Hiérarchie des objectifs (décidée, elle prime)** : 1) emails collectés, la seule mesure qui
survit à un drop ; 2) contenu qui transforme, pas seulement qui expose ; 3) l'audience est
une conséquence, pas un objectif ; 4) la visibilité (SEO/AEO/GEO) est un moyen au service du 1.
Le cockpit doit donc **toujours relier ses indicateurs au funnel qui mène à l'email et à la
vente.**

## 1.1 État de départ connu (tout est daté : il est peut-être périmé)

**Instagram `@cafe_maisonsavann`**
- Abonnés : 673 (18/07) → 965 (28/08, Apify) → « plus de 1 000 » (29/09, vu sur Google). 61 publications au 28/08.
- 30 jours au 18/07 : 17 279 vues, 4 010 comptes touchés, **22 clics vers le site**, taux profil→site 7 %, 0 email capté.
- Meilleurs contenus organiques (juillet) : carrousel packaging (86 interactions, 03/07), photo famille/équipe (66, 26/06). Le produit mis en scène et l'humain marchent.
- Paid : une campagne à 59,92 € a donné 1 027 visites (0,06 €/visite) **sans pixel Meta**, donc rien de mesuré après le clic.
- Top posts d'août (fichier `top-posts-2026-08-28.json`) : un reel « On a tous le droit d'avoir la flemme » (86 likes, 3 commentaires, ratio médiane 2,32) ; « Le secret pour sublimer notre café du Laos » (51 / 0) ; « NON, un bon café filtre ne demande pas d'être barista » (47 / 2). Les concurrents affichent des ratios de 4 à 30.
- Benchmark de 10 comptes (Coutume, Belleville, Ten Belles, L'Arbre à Café, KB, Anom, Momus, KAVA, etc.) : `benchmark-instagram-2026-08-28.csv`.
- **Anomalie à traiter en priorité** : le benchmark donne 166,9 likes moyens sur 12 posts (engagement 18,15 %) alors que les meilleurs posts organiques du même mois plafonnent à 37-86 likes. L'écart suggère que **les posts boostés gonflent la moyenne**. Séparer organique et boosté est le premier chantier analytique.
- Contraintes : **pas d'app Meta développeur** (décision du 26/09) donc aucune API Instagram, ni lecture ni publication. Les données arrivent par **export manuel** (Meta Business Suite, Ads Manager), par **veille publique** (Apify, via le skill `apify-toolkit`, coûts encadrés) ou par le connecteur Meta officiel de Claude s'il est actif (à vérifier, statut incertain).

**Site, SEO, AEO, GEO (staging, réévaluation du 30/09)**
- Note **14,8 / 20** (SEO 6,6/8, AEO 4,5/6, GEO 3,7/6) ; note de 100 : 86,4. Mesure de préparation : le staging est en `Disallow: /` volontaire, donc **pas de classement réel**.
- Panel de 20 requêtes témoins (formulation figée, fichier `panel-20-requetes.md`) : Maison SAVANN citée **1 fois sur 20** sur Perplexity, seulement quand on la nomme. **ChatGPT la cite en tête** sur « café asiatique » et sur 3 des 4 requêtes prioritaires testées. Google (AI Overview) et Perplexity désignent **Phin Mi** comme référence du café asiatique en France.
- HubSpot AI Search Grader (29/09) : ChatGPT 35, Perplexity 45, Gemini 43 sur 100 ; reconnaissance de marque et part de voix très faibles, sentiment plutôt bon quand elle est citée.
- Autorité : **zéro mention tierce**. 13 avis Google à 5,0 (relevé du 28/08). Page Facebook active. Wikidata jugé prématuré.
- Accès des robots IA : GPTBot en 429 sur la production (anti-bot Hostinger), Meta-ExternalAgent passé de 200 à 429 dans la journée. `llms.txt` servi sur le staging.
- Paysage concurrentiel (fichier `2026-09-29-resultats.md`) : Laos/Bolovens quasi libre sur la spécialité et l'histoire personnelle (aucun torréfacteur français ne documente une importation directe) ; Thaïlande tenue par Crack Cafés et deux boutiques à collection dédiée ; Vietnam : Phin Mi et Hanoi Corner sont de vrais concurrents produit ; Indonésie/Gayo : au moins 6 torréfacteurs, origine la plus disputée ; « café asiatique » : torrefaction.com a une catégorie dédiée ; drip bags : Terres de Café en tête, format ouvert.
- Outillage retenu, **0 €** (plafond growth < 50 €/mois) : Search Console, Bing Webmaster (AI Performance), Ahrefs Webmaster Tools, Google Alerts, GA4 (`G-4RD6Z9MM89` sur le staging ; la production porte Site Kit `GT-NNSLDHPK`), Merchant Center après bascule, Gemini gratuit pour le panel (clé absente à ce jour). ChatGPT, Perplexity et Google AI Overviews se remplissent **à la main** (grille mensuelle, environ 30 min).
- Faits de marque à ne jamais fausser : les quatre cafés actuels passent par un importateur, **jamais « sourcé directement »** (vrai pour les Bolovens seulement). Deux affirmations de la fiche Xieng Khouang sont non sourcées (« coopérative dirigée par des femmes », « meilleur café lavé du Laos 2021 »). ChatGPT a attribué au site, à tort, « coopérative de femmes » pour le Sumatra Gayo : **le cockpit doit avoir un journal des hallucinations des IA.**

## 1.2 Où lire (par ordre de priorité)

Détecte d'abord ton environnement : si le workspace Jarvis est présent en local
(`CLAUDE.md`, `projects/growth/`), lis les fichiers là. Sinon, lis-les par le connecteur Google
Drive avec ces identifiants (n'invente jamais un identifiant : cherche par titre au besoin).

| Fichier | ID Drive | Pourquoi |
|---|---|---|
| `projects/growth/CLAUDE.md` | `1ja6SncKES837d-yoL34nBI4Dne9s2y2h` | règles du growth, état des lieux, stack de connecteurs, priorités |
| `projects/growth/README.md` | `1HeGhAa75Xc-Q7wPTmhortT0pCgNWAE3O` | plan de bataille, décisions outillage du 26/09 |
| `seo-geo-aeo/README.md` | `1IhgyKmwbeiSWuf9JHXs9ZH4GdsdfS9Is` | **section « Cockpit dynamique » : les 5 questions de départ et les indicateurs candidats** |
| `top-posts-2026-08-28.json` | `19eczmFF0ntqi--kHKhn3GwcCob-s4ndL` | top posts de Maison SAVANN et des concurrents |
| `benchmark-instagram-2026-08-28.csv` | `1BjW8_ICpvonix1nt7IFQCn85WxV6uTmA` | benchmark des 10 comptes |
| `apify_instagram_2026-08-28.json` | `1oERoCJDNJlUyYIMD_TDlDXBWu8rP11FA` | données brutes de la veille Instagram |
| `benchmark_instagram.py` | `1Ab6_mHge4TPHGPVouYcUNy4pYEzwqEVv` | **définition exacte de `ratio_mediane` et de l'engagement** (à lire avant de les afficher) |
| `2026-07-18-audit-exhaustif-site-et-plan-conversion-instagram.md` | `1djtOfsvNw3F3oNvoJHxV-oG1Sllt5HZE` | diagnostic Instagram → site, plan de conversion |
| `guide-instagram.md`, `algorithme-instagram.md`, `strategie-contenu-instagram.md` | `1LTWTQGckXlvt2PXjQKuIYoF6N5TeWD9s`, `1UAf4pCBlmsCD2nSneINCmVY-dQJVD7yN`, `1PCcQ7_rQIUOBzGNvqSnY7d0o1OQGqV6b` | cadre théorique (algorithme, objectifs SMART, avatars) |
| `2026-09-30-reevaluation-seo-aeo-geo.md` | `1JDROfOUN-lN57rM3h68cL-t7iDbNwTnt` | **la grille de notation SEO/AEO/GEO à reprendre telle quelle** |
| `panel-20-requetes.md` | `1ElIfgQQ-3uKcHki-tYfiBayksF9WMfY7` | les 20 requêtes témoins, formulation figée |
| `2026-09-29-resultats.md` | `1DDkxccFU8Mn06PrF5IbbD50XQ8hh46RE` | paysage des résultats, concurrents par grappe |
| `hubspot-ai-search-grader-2026-09-29.md` | `1iYDdQwrU37QgPKr5Hzu01FwGkNnwBkt3` | référence de départ GEO |
| `reference-de-depart.json` | `1fWDbn-JC3bOoQ2qFpC2uy1TL-m8mnsGg` | valeurs mesurées le jour de l'audit |
| `god-prompt-audit-global.md` | `1c_FZA1jZybSBafVZFiBXxhSyTlsOm1MR` | le prompt de l'étape 1 : reprends sa **rigueur de méthode** (m/c/i/h, N/V) |
| `projects/site-v2/CLAUDE.md` | `1j1BqGULxRnYjMNTLDx-BuiyDHlSwj6UR` | charte visuelle V2, règles production/staging (elles priment) |
| Notion : « Prospects B2B », « Veille Maison Savanne » | (recherche par titre) | données candidates pour un module écosystème |
| Attio (companies, deals, people) | (connecteur) | pipeline B2B, à proposer en option seulement |

Ne lis pas plus que nécessaire : pas de pages web brutes dans la conversation, tu résumes.
Si un fichier contredit ce prompt, **le fichier gagne et tu me le signales.**

# 2. Règles non négociables

1. **Aucune donnée inventée.** Pas de chiffres « exemples » qui ressemblent à du réel. Une
   valeur inconnue s'affiche « manquant » avec la façon de la remplir. Les seules données du
   cockpit sont celles du workspace, celles que je te donne, ou celles que je téléverse.
2. **Chaque chiffre porte sa nature et sa date** : **(m)** mesuré, **(c)** calculé,
   **(i)** interpolé, **(h)** hypothèse, **N/V** non vérifié. Un badge de fraîcheur (« mesuré
   il y a 33 jours ») s'affiche partout ; au-delà d'un seuil, il passe à « à rafraîchir ».
   Les données Instagram du 28/08 ont déjà plus d'un mois : dis-le d'entrée.
3. **Corrélation n'est pas cause.** Avec ~60 posts, tu ne fais pas de régression : tu compares
   des médianes, tu affiches `n`, et tu classes chaque enseignement : **anecdote** (n < 5),
   **indice** (5 à 10), **signal** (> 10 et régulier). Toute recommandation dit son niveau de
   confiance et propose un test pour la confirmer.
4. **Tu ne prétends pas avoir vu ce que tu n'as pas vu.** Tu ne regardes pas les vidéos
   Instagram. L'analyse de contenu passe par des **fiches de tag** (que je remplis, ou qu'un
   outil de vidéo comme Gemini remplit et que je te confie) : voir §5.4. Tu n'affirmes jamais
   qu'une marque « est connue des IA » sans une citation observée.
5. **0 € par défaut.** Toute dépense (API payante, outil, Apify au-delà de l'existant) passe
   par une analyse coût / gain et mon feu vert.
6. **Rien ne sort du workspace.** Aucun envoi (email, message, publication, formulaire),
   aucune inscription, aucune écriture sur la production, le staging, SureCart, Attio, Google
   ou Instagram. Lecture seule sur tous les connecteurs. Le cockpit est une **page privée**.
   Tu me demandes avant tout partage.
7. **Pas de secret, pas de donnée personnelle dans le cockpit.** Aucune clé API, aucun mot de
   passe ; pour les emails collectés, **des comptes seulement**, jamais les adresses.
8. **Collecte polie** : jamais de collecte directe des pages de résultats Google ni
   d'Instagram connecté ; robots.txt respecté ; les sources publiques seulement.
   **Staging `testnico.maisonsavann.com` (cible du cockpit)** : lecture publique anonyme
   autorisée (pages, HTML, en-têtes, `robots.txt`, `llms.txt`, sitemaps, balisage, PageSpeed,
   test des robots IA). **Aucune connexion admin, aucune écriture, aucune commande ni
   formulaire soumis** (voir §0). Le mot de passe, la session admin et les identifiants ne
   te concernent jamais.
   **Production `maisonsavann.com` : hors limites**, la règle du `projects/site-v2/CLAUDE.md`
   prime et elle ne s'assouplit pas d'une session à l'autre. Les amendements existants
   (récupération de photos, audit SEO/GEO/AEO du 29/09) **ne couvrent pas le cockpit**. Tu ne
   lis donc pas la production. Les valeurs déjà mesurées sur la production (ex. GPTBot en 429
   au 29/09) restent affichées comme **historique daté, étiquetées « production, avant
   bascule »**, sans être remesurées. Si tu penses qu'une lecture de la production est
   indispensable, tu me le dis et **tu me proposes le texte exact d'un amendement écrit** :
   tu ne l'assumes pas.
   Même prudence pour Instagram : lecture publique et données que je te fournis seulement,
   jamais de connexion au compte.
9. **Faits de marque** : applique la section 1.1 (« jamais sourcé directement », affirmations
   non sourcées). Un texte que tu écris pour un client passe par le skill `ecriture-naturelle`
   s'il existe ; je valide tout avant publication.
10. **Style** : français, pas de tirets longs (utilise des virgules, deux-points, parenthèses),
    pas de superlatifs vides, pas de jargon non expliqué (explique CTR, LCP, GEO, AEO, la
    première fois, en une phrase).

# 3. Comment on travaille : la boîte interactive, pas de tunnel

Tu utilises l'outil **AskUserQuestion** pour me guider, **par paliers**, jamais en un mur de
questions ni en te lançant seul pendant une heure.

- **1 à 4 questions par tour**, chacune avec 2 à 4 options. Ta recommandation en **première
  option**, marquée « (Recommandé) », avec la raison en une phrase. J'ai toujours « Autre ».
- Utilise les **aperçus** (`preview`) quand je dois comparer des mises en page, des wireframes
  ou des cartes d'indicateurs. Je choisis mieux sur pièces que sur description.
- **Ne me demande jamais ce que tu peux vérifier toi-même** (fichiers, connecteurs, définitions
  d'une colonne, contenu d'un export). Tu vérifies, tu me dis ce que tu as trouvé, tu poses la
  question restante.
- **Chaque tour livre du concret** : après chaque réponse, tu mets à jour l'Artifact (même
  fichier, même URL), tu me dis en 3 lignes ce qui a changé, puis tu poses les questions du
  palier suivant. Pas de tour « je réfléchis ».
- Quand je réponds « go » ou « enchaîne », tu déroules sans t'arrêter jusqu'au prochain point
  qui exige vraiment une décision de ma part.
- Tu tiens un **journal des décisions** (dans le cockpit, onglet « Carnet », et dans un
  `journal.md` si tu as accès au workspace) : date, question, ma réponse, conséquence.
  Si ta session est compactée, tu reprends depuis ce journal.
- Suis l'avancement avec une liste de tâches (une par phase du §4).

# 4. Le déroulé (paliers, chacun se termine par des questions)

**Phase 0, inventaire (sans me déranger).** Lis les sources du §1.2. Vérifie ce qui est
réellement branché : Drive, Notion, Attio, Gmail (déconnecté), Canva (non autorisé), connecteur
Meta, GA4, Search Console. Vérifie aussi l'état **réel** du staging `testnico.maisonsavann.com`
(lecture publique : accessible ? `robots.txt` et `noindex` toujours en place ? `llms.txt` servi ?
nombre de pages au plan du site ?), sans rien écrire. Produis une **matrice de disponibilité des données** : pour chaque
indicateur candidat (§6) : source, état (dispo / manuel / manquant / bloqué), fraîcheur, effort
pour l'obtenir. Signale les anomalies (§1.1) et les définitions à confirmer.
*Sortie : 10 lignes de synthèse à moi, pas un rapport.*

**Phase 1, cadrage (premier tour de questions).** Reprends les 5 questions du README du
chantier et complète-les. Voir la banque de questions §9, tour A. Ne pose que celles dont la
réponse n'est pas déjà dans les fichiers.

**Phase 2, architecture (avant de coder).** Présente en peu de lignes : les modules retenus et
leur ordre, le modèle de données (§7), le dictionnaire d'indicateurs avec formules et seuils
(§6), le choix technique (§8), un wireframe de l'écran d'accueil en aperçu. J'approuve ou je
corrige. Une seule version d'architecture, pas trois.

**Phase 3, version 0 vivante.** Publie un Artifact **avec mes vraies données** dès que
l'architecture est validée : au minimum l'onglet Instagram (top posts, benchmark, séparation
organique / boosté à confirmer) et l'onglet GEO (panel 20 requêtes, HubSpot, accès des robots).
Vide propre là où la donnée manque, avec le geste pour la remplir. Je réagis sur pièces.

**Phase 4 et suivantes, tranches verticales.** Une tranche = un module complet (données,
visualisation, diagnostic, recommandations, gestion). Ordre recommandé, que tu me soumets :
Instagram Lab → GEO → SEO → AEO → moteur de recommandations transverse → écosystème (option).
Chaque tranche finit par un tour de questions (§9) et par une revue de qualité (§10).

**Phase finale, passation.** Mode d'emploi du cockpit (1 page), protocole de rafraîchissement
(qui met à jour quoi, quand, comment), liste de ce qui reste manuel, et les 3 premières
actions à lancer cette semaine.

# 5. Ce que le cockpit doit faire (les modules)

L'interface est **un seul Artifact à onglets** (navigation claire, utilisable sur téléphone).
Onglets proposés, à valider en phase 1 : **Cockpit · Instagram Lab · GEO · SEO · AEO · Actions ·
Carnet**. Chaque onglet suit le même gabarit : **1) verdict en une phrase, 2) indicateurs clés
avec référence de départ et tendance, 3) explication (pourquoi), 4) recommandations classées,
5) outils de gestion (saisie, checklists, journal).**

## 5.1 Cockpit (accueil)
- **Étoile polaire** : emails collectés (compte, jamais les adresses), avec son entonnoir :
  portée → visites de profil → clics lien en bio → sessions site (GA4, UTM) → ajouts panier →
  emails / commandes. Chaque marche affiche son taux et **la marche qui fuit le plus**.
  Référence de départ : 22 clics sur 30 jours, 0 email. Avant la bascule, les marches situées
  après le clic sont **N/V pour la V2** (voir §0) et le cockpit le dit sans détour.
- Tableau de bord des 4 disciplines (Instagram, SEO, AEO, GEO) : une note, une tendance, une
  fraîcheur, un feu (vert / orange / rouge) selon les seuils validés.
- **Compte à rebours** de l'échéance (arrivage des Bolovens, mi-octobre, date exacte à me
  demander) et ce qui doit être prêt avant.
- **Les 3 décisions de la semaine** (issues du moteur de recommandations §5.7), et une zone
  « alertes » (chute de citation IA, robot IA bloqué, position perdue, post à booster).

## 5.2 Instagram Lab (le plus attendu)
- **Compte** : croissance des abonnés (courbe dans le temps, gains par post), portée abonnés vs
  non-abonnés, vues par format, meilleurs créneaux **calculés sur les données du compte**
  (jamais une règle générale), régularité de publication, mix de formats.
- **Contenus** : une table de tous les posts, filtrable (format, pilier, boosté / organique,
  période), triable sur chaque mesure. Chaque ligne ouvre une **fiche post** (§5.4).
- **Vidéos / reels** : accroche (texte et 3 premières secondes, via tags), rétention (vues à
  3 s, temps moyen / durée, part de fin), taux d'envoi et de sauvegarde sur la portée, gain
  d'abonnés par reel. Les envois en message privé et les sauvegardes pèsent plus que les
  likes : le cockpit les met en avant, sans en faire une vérité si la donnée manque.
- **Organique vs boosté** (§5.5) : séparation stricte partout. Les moyennes se calculent
  **hors boost** par défaut, avec bascule visible.
- **Benchmark** des 9 comptes concurrents (ratio à la médiane, formats, accroches gagnantes,
  cadence), avec **ce qui est transposable à SAVANN** et ce qui ne l'est pas (un compte de
  28 000 abonnés ne se compare pas à 1 000 sans normaliser).
- **Cohérence bio / lien / site** : la bio, le lien (linktr.ee/maisonsavann) et les clics
  mesurés. Le lien en bio est-il le maillon faible ? Recommandation chiffrée.
- **Brief hebdomadaire de contenu** (pour la personne qui produit le contenu, la sœur de
  Nicolas) : 3 idées ancrées sur les patterns qui marchent, avec accroche, format, appel à
  l'action et l'objectif (email, clic, envoi). Voir le script `top_posts_concurrents.py` et la
  commande `/contenu` du workspace : réutilise leur logique, ne la réécris pas.

## 5.3 GEO (visibilité dans les IA) et AEO (réponse directe)
- **Panel des 20 requêtes témoins** : grille par requête × moteur (ChatGPT, Perplexity, Gemini,
  Google AI Overviews / AI Mode, Copilot) : cité oui / non, rang, sources citées à notre place,
  ton. **Interface de saisie** qui remplace le CSV manuel (30 minutes par mois). La
  formulation des 20 requêtes est **figée** (on ne la modifie pas, sinon la série n'est plus
  comparable) ; les requêtes nouvelles vont dans un panel B séparé.
- **Part de citation** par moteur et dans le temps ; **part de voix** face à Phin Mi, Malongo,
  Crack Cafés, torrefaction.com, etc. ; les sources que les IA citent à notre place, comme
  liste d'objectifs de relations presse / annuaires.
- **Accès des robots IA** : matrice des 10 robots (GPTBot, OAI-SearchBot, ChatGPT-User,
  ClaudeBot, PerplexityBot, Google-Extended, CCBot, Bingbot, Applebot-Extended,
  Meta-ExternalAgent) × code HTTP × date de mesure × **environnement**, historique, alerte sur
  429/403. Le test se fait par un script à lancer en session **sur le staging seulement** ;
  le résultat est déposé dans le cockpit. La colonne « production » reste sur les valeurs
  historiques du 29/09 (GPTBot 429) tant que je n'ai pas ouvert la production par écrit :
  à la bascule, ce test devient la **vérification prioritaire du jour J**.
- **Entité et autorité** : fiche Google Business Profile (nombre d'avis, note), `sameAs`,
  mentions tierces (compteur et liste), Wikidata (admissible oui / non, avec la règle), Google
  Alerts, liens entrants (Ahrefs Webmaster Tools). Objectif : sortir du **plafond GEO** dû à
  l'absence de mentions externes.
- **Journal des hallucinations** : ce que les IA affirment de faux sur SAVANN (ex. coopérative
  de femmes), moteur, date, capture, action corrective.
- **AEO** : par page, un **score de préparation à la réponse** (question posée en tête,
  résumé de 45 à 60 mots, tableau, `FAQPage`, `HowTo` si pertinent, date de mise à jour
  visible, sources citées) ; couverture des questions « autres questions posées » par grappe ;
  présence en extrait ou en Aperçu IA quand on peut la mesurer.

## 5.4 La fiche post et le moteur « pourquoi ça a marché »
Chaque post a une fiche avec :
1. **Mesures** (portée, vues, likes, commentaires, sauvegardes, envois, visites de profil,
   abonnés gagnés, clics, rétention si reel), chacune avec sa nature (m).
2. **Tags de contenu**, saisis par moi ou importés (liste fermée pour rester comparables) :
   pilier (origine / producteurs / famille / méthode de préparation / produit / coulisses /
   humour), type d'accroche (question, affirmation choc, « NON, ... », tutoriel, histoire,
   chiffre), durée, visage à l'écran oui/non, produit à l'image oui/non, origine citée,
   texte à l'écran, son (voix, musique, tendance), appel à l'action et type (commenter,
   envoyer, lien, sauvegarder), heure et jour, boosté oui/non.
3. **Score normalisé** : performance divisée par la médiane du compte **pour le même format,
   hors boost**, en tenant compte du nombre d'abonnés à la date du post.
4. **Autopsie** : 3 hypothèses classées (accroche, sujet, format, timing, boost, effet réseau
   personnel), chacune avec son niveau de preuve et **ce qui la confirmerait ou l'infirmerait**.
5. **Verdict** : à refaire / à décliner / à abandonner / à booster / inclassable.

Au niveau du compte : un **tableau des enseignements** (caractéristique → écart de médiane,
`n`, niveau de confiance) et un **carnet d'expériences** (« on teste l'accroche « NON, ... »
sur 4 posts, seuil de succès, date de revue »). Pour les vidéos, propose-moi un **protocole
d'extraction structurée** (mes vidéos passées dans Gemini ou l'outil habituel du workspace, qui
remplit les tags) plutôt que d'improviser. Ne juge jamais une vidéo que tu n'as pas.

## 5.5 Boost : ce qui a payé et ce qui mérite de l'être
- Registre des boosts : post, dates, budget, objectif choisi, audience, résultats plateforme
  (ceux d'Ads Manager, à importer ou saisir). Référence : 59,92 € → 1 027 visites.
- Indicateurs : coût par mille personnes touchées, par visite de profil, par clic lien, par
  abonné, **par session mesurée côté site** (UTM), et surtout **le résidu organique** : ce que
  le post aurait fait sans boost. Un boost qui n'apporte que des likes de gens hors cible est
  un échec, même à bas coût.
- Avertis clairement : **sans pixel Meta, la conversion après le clic n'est pas mesurée.**
  C'est un bloquant à lever avant tout budget (déjà listé dans le growth).
- **Score de « mérite de boost »** pour les posts organiques récents (fort taux d'envoi et de
  sauvegarde, bonne rétention, sujet aligné avec l'objectif emails) et **liste d'arrêt** pour
  ceux qui ne le méritent pas.

## 5.6 SEO
- **Sur la V2, l'onglet montre l'état de préparation** (staging fermé aux moteurs) : note
  /8 et sous-notes, pages prêtes sur 27, balisage, canoniques, plan du site, vitesse mesurée
  sur le staging. C'est **la préparation de la bascule** qui est suivie, pas un classement.
- Search Console (quand la propriété est branchée, après la bascule) : impressions, clics, CTR
  et position **par grappe de requêtes** (Laos, Thaïlande, Vietnam, Indonésie, Asie générique,
  spécialité, robusta, drip bags, marque) ; requêtes gagnées et perdues ; pages qui piquent
  du nez. Tant que la donnée manque, l'onglet affiche l'état de préparation (note /20 et
  sous-notes de la réévaluation du 30/09) et le geste pour brancher la source.
- **Carte des grappes** : requête, intention, page cible existante ou à créer, concurrents
  qui tiennent la place, écart. Volumes : « manquant » tant qu'ils ne sont pas relevés
  (Keyword Surfer, outil gratuit d'Ahrefs), **jamais estimés en silence**.
- Santé technique : pages indexées / pages du plan du site (27), canoniques, balisage
  (`Organization`, `Product`, `FAQPage`, `Place`), Core Web Vitals mobile (LCP < 2,5 s,
  INP < 200 ms, CLS < 0,1) avec date de mesure, et la **définition du « terminé »** d'une page
  (les 9 cases du CLAUDE.md du site) sous forme de checklist par page.
- **Bascule** (V2 → maisonsavann.com, geste de Nicolas avec l'accord de son cousin, jamais
  le tien) : checklist et compte à rebours des gestes (indexation à rétablir, Search Console,
  IndexNow, tag Site Kit de la production à retrouver, `robots.txt` de production, robots IA
  autorisés, redirections). Le cockpit **prépare le basculement de son propre paramètre
  « site cible »** (§0) et liste ce qu'il faudra remesurer le jour J. Pendant que le site est
  fermé, tout classement affiché est marqué **N/V**.

## 5.7 Moteur de recommandations et de gestion (transverse)
Le cœur de l'outil. Deux couches :
1. **Règles explicites** (si / alors), lisibles et modifiables. Exemples : si le taux
   profil → clic < 5 % sur 4 semaines alors action « lien en bio » ; si un robot IA passe en
   429 alors alerte GEO critique ; si une grappe a un écart concurrentiel et aucune page
   cible alors « page à créer » ; si un post organique dépasse 2 fois la médiane de son
   format et que le taux d'envoi est fort alors « candidat au boost ».
2. **Analyse de fond par Claude** (par le mécanisme le plus adapté de l'Artifact, voir §8) :
   synthèse hebdomadaire, hypothèses, contradictions entre sources, questions à me poser.
Chaque recommandation a **le même format** : **Constat** (chiffre + nature + date) →
**Pourquoi c'est important** (lien avec l'étoile polaire) → **Action** (concrète, qui, où) →
**Preuve attendue** (indicateur, seuil de succès, date de revue) → **Confiance**
(anecdote / indice / signal) → **Coût** (0 € attendu) → **Impact × Effort × Confiance**.
Elles alimentent un **backlog d'actions** que je peux faire avancer (à faire / en cours /
fait / mesuré / abandonné), assigner (Nicolas, sa sœur, Claude), dater, et qui garde
**l'avant / après** de chaque action pour apprendre ce qui a marché.
Le backlog couvre aussi la **gestion** : pipeline éditorial (idée → brief → brouillon →
validation → publié → mesuré), gestes hors site (Google Business Profile, annuaires, presse
autour du conteneur, clients B2B), gestes du « paquet de Nicolas ».

## 5.8 Écosystème (option, à me proposer sans l'imposer)
Données du workspace qui pourraient valoir un onglet : pipeline B2B (Attio, Notion
« Prospects B2B »), veille marché (Notion), ventes SureCart et emails collectés, avis Google,
calendrier des arrivages. Pour chacune : ce que ça déclencherait comme décision. Si la
réponse est « rien », tu l'écartes et tu me le dis. Le B2B est hors périmètre du chantier
growth : ne l'ajoute que si je dis oui.

# 6. Dictionnaire d'indicateurs (à figer en phase 2, avec mes seuils)

Pour chaque indicateur : nom, formule, source, nature (m/c), fréquence, référence de départ,
seuil d'alerte, décision déclenchée. Formules par défaut à confirmer :

- **Taux d'engagement sur la portée** = (likes + commentaires + sauvegardes + envois) / portée. Ne pas confondre avec l'engagement rapporté aux abonnés du benchmark : lis `benchmark_instagram.py` avant d'afficher l'un ou l'autre, et affiche la formule.
- **Taux d'envoi**, **taux de sauvegarde** = envois ou sauvegardes / portée.
- **Accroche tenue** = vues à 3 s / lectures ; **complétion** = temps moyen / durée.
- **Portée non-abonnés** (part) ; **gain d'abonnés par post** ; **conversion abonné** = abonnés gagnés / portée non-abonnés.
- **Ratio à la médiane** : reprends la définition exacte du script du workspace.
- **Entonnoir** : portée → visites de profil → clics lien → sessions GA4 (UTM) → ajouts panier → emails / commandes.
- **Boost** : CPM, coût par visite de profil, par clic, par abonné, par session, résidu organique.
- **SEO** : impressions, clics, CTR, position moyenne par grappe ; pages indexées ; note /8 ; Core Web Vitals.
- **AEO** : score de préparation par page (/6 dans la grille existante), questions couvertes / questions de la grappe.
- **GEO** : taux de citation par moteur (cité / 20), rang moyen, part de voix face aux 5 concurrents, accès robots IA (x/10 en 200), mentions tierces (nombre), avis Google (nombre, note), score HubSpot par moteur.
- **Note globale /20 et /100** : reprends la grille de la réévaluation du 30/09 pour la continuité de la série.

# 7. Modèle de données (à proposer, à faire valider)

Entités minimales : `post` (id, url, date, format, légende, accroche, durée, tags, boosté, mesures),
`snapshot_compte` (date, abonnés, abonnements, publications, vues, portée), `boost` (post,
dates, budget, objectif, résultats), `tag_definition`, `concurrent` et `post_concurrent`,
`requete_panel` (numéro, texte figé, grappe, panel A ou B), `mesure_panel` (requête, moteur,
date, cité, rang, sources, ton, capture), `acces_robot` (robot, date, environnement, code),
`mention` (source, type, date, lien), `hallucination`, `page` (URL, note SEO/AEO, cases du
« terminé »), `grappe` (requêtes, intention, page cible, concurrents), `mesure_seo` (date,
grappe, impressions, clics, position), `indicateur_valeur` (indicateur, date, valeur, nature,
source), `action` (statut, propriétaire, dates, avant / après), `experience`, `decision`.
Chaque enregistrement garde sa **source**, sa **date de mesure** et, pour tout ce qui touche au site, son **environnement** (`staging` ou `production`), pour que la série survive à la bascule sans mélange. Les imports (CSV Meta
Business Suite, Ads Manager, Search Console, fichiers du workspace) passent par une
**couche d'import** qui valide les colonnes, signale les lignes rejetées et ne remplace jamais
silencieusement une valeur.

# 8. Choix techniques (Artifact)

1. **Avant d'écrire quoi que ce soit** : appelle l'outil Artifact avec `action: "quickstart"`
   (intention « other »), puis **charge les skills `artifact-design`, `artifact-capabilities` et
   `dataviz`** (et `artifact-diagramming` seulement si un schéma apporte quelque chose). Suis
   leur contrat de page (titre de 2 à 4 mots, jetons de couleur sur `:root`, mode sombre,
   fond explicite, bibliothèques uniquement depuis les CDN autorisés, mise en page téléphone
   avec gouttière de 16 px sans défilement horizontal).
2. **Données persistantes** : ce cockpit garde des enregistrements qui s'ajoutent dans le
   temps (mesures du panel, tags, actions, boosts). Vérifie dans le catalogue de capacités
   (`artifact-capabilities`) ce qui est réellement disponible pour ce compte : base de
   données partagée (`db`), stockage de fichiers, question à Claude depuis la page, connexion
   à des données. **Préfère une capacité qui garde l'état plutôt que le stockage du
   navigateur.** Ne déclare que les capacités dont tu as besoin, et dis-moi celles qui
   manquent.
3. **Rafraîchissement** : deux voies, décrites dans le mode d'emploi final. (a) **Import
   depuis la page** : je dépose un export (CSV/JSON) que la page valide et range ; (b) **mise à
   jour par toi en session** : « mets à jour le cockpit » lit les sources autorisées, écrit
   les données dans la base par l'outil de données de l'Artifact (`ArtifactData`), sans
   republier la page. Aucune connexion sortante de la page vers des services tiers avec
   secret.
4. **Un seul fichier HTML** tant que c'est lisible ; découpe en fichiers (`files`) seulement si
   la taille l'exige. Bibliothèques : seulement celles justifiées (un parseur CSV, un
   graphique) et chargées depuis un CDN autorisé.
5. **Graphiques** : chaque graphique répond à une question précise ; annotations des
   événements (drop de mai, boost, bascule du site) ; pas de courbe sur moins de 4 points ;
   pas de camembert pour comparer ; échelles honnêtes (pas d'axe tronqué qui exagère).
6. **Publication** : l'Artifact reste **privé** ; tu ne le partages pas. Mets à jour la même
   URL à chaque tour (même chemin de fichier).

# 9. Banque de questions (à poser par tours, dans la boîte interactive)

Ne pose pas une question dont tu as déjà la réponse dans les fichiers. Reformule-les
en options concrètes avec ta recommandation.

**Tour A, cadrage (phase 1)**
1. Qui lit le cockpit et à quelle fréquence : moi seul, ma sœur qui produit le contenu, un
   associé ? Chaque jour, chaque semaine (`/semaine`), chaque mois ?
2. Quelle est la décision n°1 que le cockpit doit m'aider à prendre chaque semaine ?
3. Étoile polaire : confirmes-tu « emails collectés » ? Quel objectif chiffré à 3 mois
   (emails, abonnés, clics), au format SMART ?
4. Quels onglets, dans quel ordre de construction ? (Recommandé : Instagram → GEO → SEO → AEO →
   Actions.) L'écosystème (B2B, SureCart) : oui ou plus tard ?
5. Cible et bascule : le cockpit démarre sur `testnico.maisonsavann.com` (état de préparation,
   pas de classement réel). Confirmes-tu que la production reste fermée jusqu'à la bascule ?
   Quelle est la date visée de bascule, et veux-tu que le cockpit prévoie dès maintenant le
   passage au site de production (paramètre « site cible ») ? Peux-tu me fournir un export
   GA4 de la production pour avoir une référence avant V2 ?
6. Sources réellement disponibles aujourd'hui : accès à Meta Business Suite (export par post,
   par reel) ? à Ads Manager ? Search Console (propriété, compte) ? GA4 (achat vérifié) ?
   Bing Webmaster ? Sais-tu où trouver chaque export ?

**Tour B, Instagram**
7. Quels posts ont été boostés, quand, pour combien, avec quel objectif (trafic, engagement,
   notoriété) ? Si tu ne t'en souviens pas : où le retrouver dans Ads Manager ?
8. Qui produit le contenu, à quelle cadence, avec quel temps hebdomadaire ? (Cela borne la
   taille du brief hebdomadaire.)
9. Piliers de contenu et avatars retenus (D2C sensible au terroir, B2B coffee shop) : lesquels
   suit-on dans le cockpit ?
10. Le lien en bio (linktr.ee) : garde-t-on ce dispositif ou passe-t-on à un lien avec UTM
   direct vers le site ?
11. Tags de contenu : validation de la liste fermée (§5.4) et qui les saisit (toi, ta sœur, un
    outil vidéo) ?

**Tour C, SEO / AEO / GEO**
12. Date de l'arrivage des Bolovens et du drop (pour le compte à rebours ; la date de bascule est déjà demandée en 5) ?
13. Le panel de 20 requêtes reste-t-il figé ? Qui remplit la grille chaque mois (30 min) ?
14. Moteurs à suivre : ChatGPT, Perplexity, Gemini, AI Overviews, AI Mode, Copilot : tous, ou
    on commence par lesquels ? Clé Gemini gratuite disponible ou non ?
15. Concurrents à suivre dans le cockpit : les 5 GEO/SEO (Phin Mi, Malongo, Crack Cafés,
    torrefaction.com, Cafés Dessertine ?) et les 9 comptes Instagram : on garde ou on change ?
16. Arbitrage ouvert du chantier : « référence du café asiatique » ou « tête de pont Laos
    d'abord » : le cockpit doit-il suivre les deux périmètres en parallèle ?

**Tour D, forme et seuils**
17. Direction visuelle (avec aperçus) : carnet éditorial fidèle à la charte V2 (crème,
    bordeaux, marine, Playfair Display et Lato), sobre « salle de contrôle », ou mix ?
18. Densité : vue d'ensemble aérée et détail dense, ou tout dense ? Téléphone d'abord ?
19. Seuils d'alerte : valides-tu les propositions du dictionnaire (§6) ? Lesquels veux-tu
    voir en rouge ?
20. Ton des recommandations : directif (« fais ceci ») ou nuancé (« voici trois options et
    mon avis ») ?

**Tour E, après chaque tranche** : ce que j'ai compris de ton retour, ce que je change, ce
que je propose ensuite, et une seule question de fond.

# 10. Contrôle qualité (avant de me dire « c'est prêt »)

Tu **testes réellement** l'Artifact : ouvre-le dans un navigateur (Playwright et Chromium sont
préinstallés dans les environnements distants, n'exécute pas `playwright install`), vérifie :
aucune erreur en console ; rendu à 390 px et à 1280 px sans défilement horizontal ; mode
sombre lisible ; contrastes WCAG AA ; navigation au clavier ; états vides et états d'erreur
propres ; import d'un fichier valide **et** d'un fichier cassé ; chaque chiffre a sa nature,
sa date et sa source ; aucun chiffre sans origine ; les seuils déclenchent bien les alertes ;
les recommandations citent leur constat. Tu me donnes le résultat des tests, pas une
affirmation.

Chaque tour, tu clos ton message ainsi : **ce qui est fait** (avec le lien de l'Artifact) ·
**ce qui est mesuré et ce qui ne l'est pas (N/V)** · **ce que j'ai décidé de ne pas faire et
pourquoi** · **la ou les questions du palier suivant**.

# 11. Ce que je veux voir au premier tour

1. Un rapport d'inventaire de **10 lignes maximum** (phase 0) : ce que tu as lu, ce qui est
   branché, ce qui manque, les anomalies repérées (dont l'écart de likes moyens et la
   fraîcheur des données Instagram).
2. La **matrice de disponibilité des données** (tableau court).
3. Le **premier tour de questions** de la boîte interactive (tour A, adapté à ce que tu as
   déjà trouvé), en 4 questions maximum.

Ne construis rien avant mes réponses au tour A, sauf si tu estimes qu'un wireframe en aperçu
m'aide à répondre.

=== FIN DU PROMPT ===
