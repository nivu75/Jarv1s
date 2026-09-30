---
type: reference
date: 2026-09-30
tags: [growth, seo, aeo, geo, passation, verification, site-v2, staging]
related: ["[[projects/growth/seo-geo-aeo/analyses/2026-09-30-termes-expressions-seo-aeo-geo]]", "[[projects/growth/seo-geo-aeo/analyses/2026-09-29-audit-global]]", "[[projects/site-v2/CLAUDE.md]]"]
---

# Passation : vérifier sur le site test ce qui n'a pas pu l'être (SEO, AEO, GEO)

> Écrite par une session Claude cloud (Sonnet 5.5) qui **n'a pas pu lire** `testnico.maisonsavann.com` (réseau
> bloqué, 403) ni son wp-admin. Elle a analysé le site à partir de ses **sources** et de documents de travail.
> **Toi, session qui a accès au site : ta mission est de vérifier, corriger mes erreurs et aller plus loin, en lecture
> seule.** Ce document est autonome : il ne suppose aucun contexte antérieur.
> Nature des chiffres : **(m)** mesuré, **(c)** calculé, **(t)** source tierce non vérifiée, **(h)** hypothèse,
> **N/V** non vérifié. Tout ce qui est marqué (h) ou N/V ci-dessous est à vérifier.

## 0. Ta mission en trois phrases

1. **Mesurer le site test tel qu'il est réellement en ligne** (pages, balises, textes, balisage, robots) et le comparer,
   ligne à ligne, à ce que je crois savoir (§3).
2. **Trancher mes hypothèses** (§3.B) et **confirmer ou infirmer les contradictions** (§3.C) avec des preuves.
3. **Rendre des données propres** (§6) : un rapport, quatre fichiers de données, un JSON de référence. Une session cloud
   les lira pour mettre à jour le cockpit de pilotage (Artifact) de Maison SAVANN.

Tu ne modifies rien. Tu ne publies rien. Tu n'envoies rien.

## 1. Contexte en dix lignes

- **Maison SAVANN** : cafés de spécialité d'Asie du Sud-Est (Laos, Thaïlande, Vietnam, Indonésie), projet familial,
  lancé en mai 2026. Une seule marque visible. Vente en ligne.
- **Le site** : WordPress (Blocksy, Spectra, SureCart, Rank Math, Complianz, LiteSpeed Cache), hébergé chez Hostinger.
  **`testnico.maisonsavann.com` est la V2** (staging) : elle remplacera `maisonsavann.com` (production, V1) à la **bascule**,
  geste de Nicolas qui exige l'accord de deux personnes le jour même.
- **Le staging est fermé aux moteurs volontairement** : `Disallow: /` et `noindex`. Donc aucune position réelle ni
  Search Console avant la bascule : on mesure une **préparation**.
- **Objectif du chantier** : que le site devienne la référence du café de spécialité asiatique en France et en Europe,
  dans les moteurs (SEO), les extraits (AEO) et les réponses d'IA (GEO). **Mesure de succès finale : les emails collectés.**
- **Échéance** : arrivage d'un conteneur de cafés des Bolovens (Laos) à la mi-octobre 2026, importé en direct.
- **Ce que la session cloud a produit** : un cockpit (Artifact), une analyse des termes à mettre sur le site
  (`projects/growth/seo-geo-aeo/analyses/2026-09-30-termes-expressions-seo-aeo-geo.md`), un audit externe du 29/09
  (`2026-09-29-audit-global.md`) et un panel de 20 requêtes IA. Lis ces trois fichiers si tu peux.

## 2. Règles non négociables (elles priment sur ce document)

Lis d'abord, dans l'ordre : `CLAUDE.md` racine, `projects/growth/CLAUDE.md`, **`projects/site-v2/CLAUDE.md`** (règles
production et staging). Points clés :

1. **Lecture seule sur le staging.** Aucune écriture : pas de page, pas de média, pas de réglage, pas de formulaire
   soumis, pas d'extension. **Aucune commande** : SureCart du staging est branché sur le compte de production en mode
   **live**, une commande serait réelle.
2. **`maisonsavann.com` (production) : hors limites**, en lecture comme en écriture, sauf amendements écrits explicites
   du `site-v2/CLAUDE.md`. Ne teste pas la production sans amendement couvrant ton usage. Si tu en as besoin, **demande à
   Nicolas** un amendement avec le texte exact.
3. **wp-admin** : seulement si Nicolas t'a ouvert une session (lien hPanel, fenêtre pilotée). **Ne récupère, ne devine et ne
   stocke jamais d'identifiants.** Et **piège vécu** : le navigateur piloté injecte l'identifiant et le mot de passe dans des
   champs texte quelconques des réglages (ex. Rank Math « SEO local »). **N'enregistre aucun formulaire de réglages.** Pour
   lire une valeur stockée, préfère le HTML brut ou l'API REST de lecture.
4. **Aucun envoi vers l'extérieur** (email, message, publication, formulaire de contact). Aucune inscription.
5. **0 € de dépense.** Aucun service payant.
6. **Collecte polie** : une requête toutes les 2 secondes au plus, respect du `robots.txt` des sites tiers, jamais de
   collecte directe des pages de résultats Google. **Robots IA : voir §5.7, un seul passage.**
7. **Contexte propre** : pas de HTML brut dans la conversation. Collecte et filtrage en Python, résultats écrits dans
   `data/`, seul le résumé revient.
8. Pas de secret dans un fichier versionné. Français, pas de tirets longs, pas de flagornerie.
9. **Fichiers serveur** (mu-plugin, `.htaccess`, `robots.txt` de production) : tu ne les touches pas.

Si un outil t'est refusé, dis-le et arrête-toi sur ce point : ne contourne pas.

## 3. Ce que je sais, ce que je crois, ce que je n'ai pas pu vérifier

### 3.A Faits établis par des sources datées (à confirmer sur le site)

| Fait | Source | Date |
|---|---|---|
| 27 pages au plan du site, toutes en 200, canonique 27/27, titre ≤ 60, description 140 à 155, un H1 (m) | réévaluation SEO/AEO/GEO | 30/09 |
| 12 pages ajoutées : `/terroirs/`, 4 pages pays, 7 terroirs (Xieng Khouang, Bolovens, Gayo, Son La, Mae Jan Tai, Doi Chang, Nan) (m) | réévaluation | 30/09 |
| Balisage : Organization, Product ×6, BreadcrumbList ×26, FAQPage ×8 (45 questions), Place ×7 ; ni `sku` ni date sur les fiches (m) | réévaluation | 30/09 |
| `llms.txt` servi (généré par Rank Math, 27 pages) ; 404 le 29/09 (m) | réévaluation, référence de départ | 30/09 |
| Note de préparation **14,8 / 20** (SEO 6,6/8, AEO 4,5/6, GEO 3,7/6) ; note de 100 : 86,4 (m) | réévaluation | 30/09 |
| Robots IA sur le staging : GPTBot **429** (200 le matin), Meta-ExternalAgent 200, 8 autres 200 ; sur la production : GPTBot 429, Meta-ExternalAgent 429 (m) | audit global | 29/09 |
| Mentions tierces : 0 ; avis Google : 13 à 5,0 (28/08) (m) | audit global, veille | 29/09 |
| Panel de 20 requêtes IA : Maison SAVANN citée sur **1 sur 20** (Perplexity, requête nominale) ; ChatGPT la cite en tête sur « café asiatique » (m) | panel IA | 29/09 |
| Concurrents : Phin Mi et Hanoi Corner (Vietnam), Crack Cafés (Thaïlande, article), Malongo, Les Torréfacteurs, Cafés Dessertine, Cafés Miguel (Laos), Terres de Café (drip bags), torrefaction.com (catégorie « Cafés d'Asie ») (m, recherche orientée US) | SERP | 29/09 |
| `projects/site-v2/pages/` est la source de vérité du contenu des pages | CLAUDE.md du site | permanent |

### 3.B Hypothèses à tester (mes conclusions tirées des sources, pas du site)

| # | Hypothèse | Comment la trancher |
|---|---|---|
| H1 | Les termes absents des sources sont aussi absents du site en ligne : « café laotien », « café asiatique », « café du Vietnam », « café de Thaïlande », « arabica », « robusta », « fine robusta », « score SCA », « import direct », « importation directe », « Doi Chang », « Mae Jan Tai », « Caturra », « Bolaven », « honey », « altitude » | Comptage par page (§5.3). Les pages de terroir en ligne peuvent les porter : je ne les ai pas lues |
| H2 | « Meilleur café du Laos 2021 » figure sur l'accueil, « Notre histoire », la fiche Xieng Khouang et `llms.txt` | Recherche exacte dans le HTML, le JSON-LD, les `alt`, `llms.txt` (§5.4) |
| H3 | « Une coopérative de femmes au nord de Sumatra » figure dans « Notre histoire » (section Gayo) et explique l'erreur de ChatGPT, qui l'a attribuée au site | Idem, plus l'historique de la page si accessible |
| H4 | Le lieu est incohérent : Paris (atelier Altura, FAQ), Frolois (siège légal, mentions), Nancy (adresse du profil Instagram) | Recherche du lieu, de l'adresse et de `PostalAddress` sur toutes les pages et le JSON-LD (§5.6) |
| H5 | Les pages de terroir ont un H1 et une meta qui **désambiguïsent** (café, arabica, coopérative) contre restaurant et tourisme | Lecture des 12 pages (§5.2) |
| H6 | Les pages de terroir contiennent encore des marques de travail : « (source non relue) », « (résumé de recherche) », « (à confirmer) », crochets `[...]`, « Notes internes » | Recherche de motifs (§5.4) |
| H7 | Aucun nom de fournisseur ne fuit sur le site (contenu, `alt`, commentaires HTML, balisage, `llms.txt`) | Recherche de chaînes (§5.4) |
| H8 | L'ordre du DOM est correct : phrase citable et fiche technique au début de la fiche produit | Position des faits clés dans le HTML (§5.2) |
| H9 | La FAQ a maintenant des liens sortants (0 avant le 28/09) et ses fautes de frappe sont corrigées | Comptage de liens, lecture (§5.2) |
| H10 | `robots.txt` du staging est en `Disallow: /`, `noindex` présent, `llms.txt` liste 27 pages | Lecture (§5.1) |
| H11 | GPTBot est toujours en 429 sur le staging : un anti-bot réagit aux requêtes répétées | Un seul passage (§5.7) |
| H12 | Le réglage « slug » de la page Bolovens est `/terroirs/laos/bolovens/` alors que le plan dit `/plateau-des-bolovens/` | URL réelles au plan du site |

### 3.C Contradictions entre documents, à arbitrer par les faits ou par Nicolas

| # | Point | Valeurs en conflit |
|---|---|---|
| C1 | Altitude Xieng Khouang | 1 500 m (accueil, phrases citables), 1 500 à 1 600 m (proposition), 1 100 à 1 400 m (audit du 27/09) |
| C2 | Altitude Bolovens | 1 000 à 1 350 m (brouillon, Wikipédia) ou 800 à 1 350 m (autres sources) |
| C3 | Altitude Vad Si Tong | 1 300 m (brouillon Bolovens) ou 1 100 m (profil de torréfaction) |
| C4 | « Torréfié à Paris » pour les drip bags | à vérifier par Nicolas (D4) ; les autres cafés : atelier Altura, Paris |
| C5 | « Import direct » | vrai pour les quatre lots des Bolovens du conteneur (importateur partenaire, douane partagée) ; **faux pour les quatre cafés actuels** (passent par un fournisseur). La FAQ dit « approvisionnement direct » et « partenaire spécialisé » |
| C6 | Qui a noté les cafés | les scores affichés (83, 85, 84) sont ceux du **fournisseur**, pas de Maison SAVANN |
| C7 | Coopérative de Xieng Khouang | « 200 familles » (site) ; « dirigée par des femmes » (proposition non prouvée) |
| C8 | Moyens de paiement | FAQ « Visa, Mastercard, American Express via Mollie » ; fiches « Apple Pay, Google Pay » ; paiement staging « Carte, PayPal » |
| C9 | Zone de livraison | article 6 des CGV « France et Union européenne » ; SureCart n'ouvre que la France métropolitaine |

## 4. Outils et périmètre

- Lecture publique anonyme du staging : autorisée (pages, HTML, en-têtes, sitemaps, `robots.txt`, `llms.txt`).
- Scripts existants dans le dépôt : `projects/site-v2/scripts/check_site.py` (audit, lecture), `projects/growth/seo-geo-aeo/scripts/`
  (dont `check_robots_ia.py`). Lis leur `README.md` (classement lecture, écriture, consommation).
- Résultats : `projects/growth/seo-geo-aeo/data/site-v2-verification/2026-MM-JJ/`.
- Priorité des pages (30 URL au plus, 5 pages par domaine tiers) : accueil, boutique, 5 fiches café, drip bags, coffret,
  FAQ, notre histoire, pro, contact, mentions légales, `/terroirs/`, 4 pays, 7 terroirs.

## 5. Protocole de vérification

### 5.1 Inventaire et accès

1. `robots.txt`, `llms.txt`, tous les sitemaps déclarés (`page-sitemap`, `sc_product-sitemap`, sitemap des terroirs s'il existe),
   `sitemap_index`. Contenu exact du `robots.txt` (Disallow, Sitemap, blocs par robot).
2. Pour chaque URL du sitemap : code HTTP, redirections (chaîne complète), `canonical`, `meta robots`, `X-Robots-Tag`,
   taille du HTML, temps de réponse. Signaler les pages hors sitemap qui répondent 200 (collections SureCart).
3. Compter les URL du plan de site et comparer à 27 (H10, H12).

### 5.2 Balises et structure, page par page

Pour chaque URL prioritaire, relever et **écrire dans `urls-inventaire.csv`** :
`url, http, canonical, robots, title, len_title, meta, len_meta, h1_nb, h1, h2_liste, mots, images_nb, images_sans_alt, liens_int_sortants, liens_vers_noindex, part_texte_util_pct, position_1er_fait_pct`.
- Longueurs cibles du chantier : title ≤ 60, meta 140 à 155, un seul H1.
- `part_texte_util_pct` = texte visible ÷ HTML ; `position_1er_fait_pct` = position (en % du HTML) de la première occurrence de
  l'altitude, du score et du nom du producteur (H8). Référence du 27/09 : la fiche Laos affichait sa fiche technique à 62 % du
  fichier ; 4 % de texte utile.
- **Liens** : liste des liens internes par page avec leur ancre. Marquer les ancres génériques (« en savoir plus »), les liens vers
  des collections en `noindex`, les liens cassés. Calculer entrants et sortants par page, repérer les pages orphelines.
- **Pages de terroir** (12) : le H1 et la meta contiennent-ils « café » et deux mots de produit (arabica, coopérative, lot, grains,
  altitude) ? La page contient-elle une section « Questions fréquentes », « Notre dégustation », des tableaux ? (H5)

### 5.3 Présence des termes (le cœur de l'analyse)

Pour chaque page et chaque terme, compter les occurrences **dans le title, la meta, le H1, les H2, le corps, les `alt`, le JSON-LD**
(normaliser accents, casse, apostrophes ; limites de mot pour « SCA »). Écrire `termes-par-page.csv` :
`url, terme, n_total, dans_title, dans_meta, dans_h1, dans_h2, dans_corps, dans_alt, dans_jsonld`.

Liste des termes à mesurer (groupe : termes) :

- **Générique** : café de spécialité ; café d'Asie ; café d'Asie du Sud-Est ; Asie du Sud-Est ; café asiatique ; torréfacteur ; torréfaction ; score SCA ; SCA ; 80 points ; dégustation ; cupping.
- **Laos** : café du Laos ; café laotien ; Laos ; plateau des Bolovens ; Bolovens ; Bolaven ; Paksong ; Champassak ; Salavan ; Lao Ngam ; Nambeng ; Xieng Khouang ; Xiengkhouang ; Phonsavan ; Keoset ; Caturra ; Java ; Catimor ; Vad Si Tong.
- **Import** : import direct ; importation directe ; en direct ; approvisionnement direct ; conteneur ; importateur.
- **Thaïlande** : café de Thaïlande ; café thaïlandais ; Doi Chang ; Doi Chaang ; Mae Jan Tai ; Mae Chanan ; Chiang Rai ; Chiang Mai ; Nan ; Suchart ; Akha ; Lisu ; fermentation anaérobie.
- **Vietnam** : café du Vietnam ; café vietnamien ; Son La ; Kanang ; arabica ; robusta ; fine robusta ; robusta de spécialité ; indication géographique ; Rainforest Alliance.
- **Indonésie** : café d'Indonésie ; Sumatra ; Gayo ; Takengon ; Aceh ; wet-hulled ; giling basah.
- **Format et usage** : drip bag ; drip bags ; filtre individuel ; sachet filtre ; sans matériel ; café soluble ; V60 ; piston ; espresso ; expresso ; mouture ; en grains ; moulu.
- **Preuve** : lavé ; nature ; honey ; altitude ; Diedrich ; Ikawa ; Cropster ; densité ; humidité.
- **Lieu** : Paris ; Nancy ; Frolois ; Altura ; Savannakhet ; Lorraine.

Comparer aux comptes que j'ai obtenus sur les **sources** (accueil, boutique, notre histoire, pro, FAQ révisée) et **signaler les écarts**
(dérive entre source et staging). Rappel de mes comptes : Laos 25 ; drip bag(s) 20 ; Paris 16 ; Savannakhet 9 ; « SCA » 5 (seulement
comme étiquette « SCA 83 ») ; tout ce qui est en gras au groupe ci-dessus a 0 occurrence sur les sources statiques.

### 5.4 Audit des affirmations et des fuites

Écrire `affirmations.csv` : `url, emplacement (corps, title, meta, alt, jsonld, commentaire html, llms.txt), phrase exacte, contexte 100 caractères`.

- **Affirmations non prouvées** (H2, H3) : « Meilleur café du Laos 2021 », « meilleur café lavé du Laos », « coopérative de femmes »,
  « dirigée par des femmes », « élu meilleur », « 95 % du café laotien », « Bolaven Coffee » comme indication géographique protégée.
- **Formules que la charte interdit** : « sourcé directement », « importé en direct » (hors Bolovens), « exclusivement »,
  « relations privilégiées », « d'exception », « authentique », « 100 % arabica » (un lot est un robusta), « coopérative d'excellence ».
- **Marques de travail** (H6) : « (source non relue) », « (résumé de recherche) », « (à confirmer) », « À compléter par Nicolas »,
  « Notes internes », crochets `[...]`, `<!--` contenant des consignes, « lorem ».
- **Fuites de noms** (H7) : le fournisseur des cafés actuels (`Ayasen`), l'importateur partenaire (`CAFE 1700`, `Jordan`), le nom de
  l'ancienne marque (`Bean Lao` : décision 001, une seule marque visible). Chercher dans le HTML, les `alt`, les `title`, les
  commentaires, le JSON-LD, `llms.txt`, les noms de fichiers d'images.
- **Sujets à ne pas aborder** : `kopi luwak`, prix sur les pages de terroir non vendues, boutons d'achat sur les cafés « à torréfier si
  assez d'intéressés ».

### 5.5 Balisage structuré

Pour chaque page, extraire tout le JSON-LD, le valider (syntaxe, types, champs), écrire `jsonld.csv` :
`url, types, priceCurrency, aggregateRating (oui/non), sku, brand, description_egale_texte_visible (oui/non), sameAs, address, areaServed, faq_nb_questions, faq_texte_egal_page (oui/non)`.
- **`Product`** : `priceCurrency` = `EUR` majuscules ; **pas** d'`aggregateRating` ; `brand`, `sku`, `description` = texte affiché (le texte
  legacy de l'importateur avait été repéré le 27/09) ; **pas** de `Product` ni `Offer` sur les cafés non vendus des pages de terroir.
- **`Organization`** : `name`, `alternateName` (« Maison Savann »), `logo`, `founder` (Person), `address`, `areaServed`, `sameAs`
  (Instagram `cafe_maisonsavann`, Facebook, LinkedIn, Google Business), `knowsAbout`.
- **`FAQPage`** : le texte de chaque réponse est **mot pour mot** celui de la page ; une question n'est balisée que sur une page.
- **`Place`** sur les 7 terroirs (`containedInPlace` = pays), **jamais** `Restaurant` ni `TouristAttraction`.
- `BreadcrumbList` sur 26 pages ; `WebSite` + `SearchAction` ; `HowTo` (recettes) et `Article` (journal) : présents ou non.

### 5.6 Cohérence de l'entité (nom, adresse, lieu)

Relever **chaque occurrence** de : Paris, Nancy, Frolois, Altura, adresse postale, téléphone, email (`.com` contre `.fr` : une
incohérence de domaine avait été trouvée en juillet), SIREN, forme juridique, dans les pages, les mentions légales, le pied de page, le
JSON-LD et `llms.txt`. Dresser le tableau des valeurs distinctes par surface. Comparer à Instagram (profil `@cafe_maisonsavann` :
« 17 rue Stanislas, Nancy ») et, si tu peux l'ouvrir en lecture, à la fiche **Google Business Profile** (catégorie, adresse, nombre
d'avis, note). Objectif : **une seule identité** partout. Ne tranche pas : liste les conflits pour Nicolas.

### 5.7 Robots IA et lisibilité par les extracteurs

1. **Un seul passage**, sur le staging, pour les 10 robots (GPTBot, OAI-SearchBot, ChatGPT-User, ClaudeBot, PerplexityBot, Google-Extended,
   CCBot, Bingbot, Applebot-Extended, Meta-ExternalAgent) : code HTTP, taille, page de vérification anti-robots éventuelle. Le 29/09,
   des passages répétés semblent avoir **déclenché** un blocage : **ne relance pas** dans la journée. Note l'heure.
2. Lecture d'une page avec un extracteur simple (texte seulement) : les faits clés (altitude, producteur, score) apparaissent-ils dans les
   premiers 30 % du texte ?
3. Ne modifie aucun réglage Hostinger. Le geste (journaux de sécurité, AI Audit) revient à Nicolas.

### 5.8 Performance (facultatif, si le quota le permet)

PageSpeed mobile sur 5 URL (accueil, fiche Laos, fiche drip bags, pilier Laos, FAQ) : LCP, INP, CLS, poids du HTML, nombre de scripts
SureCart. Cibles : LCP < 2,5 s, INP < 200 ms, CLS < 0,1. La dernière mesure date du 28/09 ; le quota était épuisé le 30/09.

### 5.9 wp-admin, lecture seule (seulement si Nicolas a ouvert la session)

Lire, sans enregistrer : gabarits de titres et de descriptions Rank Math, réglages du sitemap et de `llms.txt`, schémas par type de contenu,
réglage « Visibilité pour les moteurs », titre de la page 404, redirections (Rank Math), liste des pages avec leur statut (publié, brouillon,
privé), pages de terroir non publiées. **Rappel : aucun formulaire de réglages n'est enregistré** (remplissage automatique).

### 5.10 Refaire la note avec la même grille

Refaire la note de préparation avec la grille de `2026-09-30-reevaluation-seo-aeo-geo.md` (dans le workspace du chantier ou sur Drive ; absent du dépôt cloné par la session cloud) (SEO 8 : technique, pages, balisage, vitesse ; AEO 6 :
réponses directes, structure, couverture ; GEO 6 : entité, accès aux IA, autorité). Comparer à 14,8 / 20 (m, 30/09) et **expliquer chaque écart**.

### 5.11 SERP et concurrents, en France (facultatif)

Mes recherches étaient orientées États-Unis. Si tu peux interroger avec un contexte français, relever pour les 10 requêtes prioritaires du panel
(Q1, Q2, Q4, Q5, Q6, Q7, Q9, Q10, Q12, Q17) les 10 premiers domaines, leur type et le format de page. Vérifier en particulier :
`torrefaction.com` (catégorie « Cafés d'Asie »), Phin Mi, Hanoi Corner, Cafés Miguel, Di Costanzo, Maison Deuza (revendique-t-elle le Laos ?).

## 6. Ce que tu dois rendre

1. **`rapport-verification.md`** : verdict en dix lignes, puis un tableau **« Hypothèse (H1 à H12) : verdict (confirmée, infirmée, partielle) : preuve »**, puis un
   tableau des **contradictions (C1 à C9)** avec la valeur constatée sur le site, puis les **découvertes que je n'avais pas vues**, puis les corrections proposées
   (prêtes à faire valider ligne par ligne), puis les questions à Nicolas.
2. Les quatre fichiers de données : `urls-inventaire.csv`, `termes-par-page.csv`, `affirmations.csv`, `jsonld.csv`.
3. **`reference-site-v2.json`** (lu par le cockpit) :
```json
{
  "date": "AAAA-MM-JJ", "environnement": "staging", "source": "lecture publique du staging",
  "pages_sitemap": 0, "pages_200": 0, "pages_noindex": 0, "canonique_ok": 0,
  "title_ok_60": 0, "meta_ok_140_155": 0, "h1_unique": 0,
  "jsonld": {"Organization": 0, "Product": 0, "FAQPage": 0, "Place": 0, "BreadcrumbList": 0, "HowTo": 0, "Article": 0,
             "product_priceCurrency_EUR": 0, "product_aggregateRating": 0},
  "faq": {"questions_balisees": 0, "liens_sortants": 0},
  "llms_txt": {"statut": 0, "pages_listees": 0},
  "robots_txt": {"disallow_tout": true},
  "robots_ia": {"GPTBot": 0, "OAI-SearchBot": 0, "ChatGPT-User": 0, "ClaudeBot": 0, "PerplexityBot": 0,
                "Google-Extended": 0, "CCBot": 0, "Bingbot": 0, "Applebot-Extended": 0, "Meta-ExternalAgent": 0},
  "termes_absents": [], "affirmations_non_prouvees": [], "marques_de_travail": [], "fuites_de_noms": [],
  "lieux_distincts": [], "note_20": {"seo": 0, "aeo": 0, "geo": 0}
}
```
4. **Les règles de rendu** : chaque chiffre porte sa nature (m, c, h, N/V) et sa date ; une valeur non mesurée s'écrit N/V, jamais estimée ;
   tu dis **ce que tu as fait toi-même** (script, navigateur) et ce que tu n'as pas pu faire, et pourquoi.

## 7. Questions à poser à Nicolas si les faits ne suffisent pas

1. **Lieu** : quelle adresse et quelle ville veut-il afficher partout (Paris, Frolois, Nancy) ? Le « torréfié à Paris » est-il vrai pour les drip bags ?
2. **Import direct** : formulation exacte autorisée pour les Bolovens ; nom de l'importateur public ou non.
3. **Affirmations** : d'où vient « Meilleur café du Laos 2021 » (concours, année, lot) ? Retire-t-il « coopérative de femmes » pour le Gayo ?
4. **Altitudes** : valeurs exactes de Xieng Khouang, Bolovens, Vad Si Tong.
5. **Scores** : quels cafés a-t-il goûtés lui-même (cupping daté) ? Les autres scores sont-ils mentionnés comme ceux du fournisseur ?
6. **Volumes de recherche** : peut-il relever ceux des 44 requêtes (Keyword Surfer, outil gratuit d'Ahrefs) ?
7. **Publication des données de torréfaction** mesurées : oui ou non (contenu que personne d'autre ne publie en France).

## 8. Fichiers à connaître (dépôt de travail, chemins relatifs)

| Fichier | Contenu |
|---|---|
| `projects/site-v2/CLAUDE.md` | règles staging et production, charte, faits techniques, pièges |
| `projects/site-v2/pages/` | sources des pages, `seo-geo/` (textes du lot 100, `llms.txt`, phrases citables, `robots-production.txt`) |
| `projects/site-v2/analyses/2026-09-27-audit-geo-architecture-contenu.md` | architecture cible, gabarits, balisage, off-site |
| `projects/site-v2/analyses/2026-09-28-audit-final-avant-bascule.md` | note globale avant bascule |
| `projects/growth/seo-geo-aeo/data/requetes.csv` | 44 requêtes, intention, grappe, page cible (volumes manquants) |
| `projects/growth/seo-geo-aeo/data/suggestions-google.json` | suggestions Google du 29/09 |
| `projects/growth/seo-geo-aeo/data/panel-ia/panel-20-requetes.md` | les 20 questions du panel (formulation figée) |
| `projects/growth/seo-geo-aeo/data/robots-ia-2026-09-29.json` | accès des robots IA du 29/09 |
| `projects/growth/seo-geo-aeo/analyses/2026-09-30-termes-expressions-seo-aeo-geo.md` | mon analyse (à corriger avec tes preuves) |
| Drive, dossier `projects/site-v2/pages/terroirs/` | brouillons des pages de terroir (README, une page par terroir) |
| Drive (ou workspace) `2026-09-30-reevaluation-seo-aeo-geo.md`, `2026-09-30-textes-etape-1-a-valider.md` | note 14,8/20 et sa grille ; textes de titres et metas D1 à D14 en attente de validation |

## Ce que je fais maintenant (session cloud)

Je n'ai rien déposé sur le site. J'attends ton rapport et ton JSON, puis j'ajusterai l'analyse des termes, je mettrai à jour les onglets SEO, AEO et
GEO du cockpit avec les valeurs mesurées, et je préparerai les textes à valider avec Nicolas.
