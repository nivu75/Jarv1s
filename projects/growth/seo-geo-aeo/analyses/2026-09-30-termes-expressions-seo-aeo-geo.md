---
type: reference
date: 2026-09-30
tags: [growth, seo, aeo, geo, termes, expressions, contenu, site-v2]
related: ["[[projects/growth/seo-geo-aeo/analyses/2026-09-29-audit-global]]", "[[projects/growth/seo-geo-aeo/analyses/2026-09-29-panel-ia-complet]]", "[[projects/site-v2/analyses/2026-09-27-audit-geo-architecture-contenu]]", "[[projects/growth/seo-geo-aeo/data/requetes]]"]
---

# Termes et expressions à mettre sur le site V2 : analyse SEO, AEO, GEO

> Écrit par Claude (Sonnet 5.5, session cloud) le 2026-09-30. **(m)** mesuré, **(c)** calculé, **(t)** source
> tierce non vérifiée, **(h)** hypothèse, **N/V** non vérifié. Aucun texte n'est déposé sur le site : tout ce qui
> suit est une proposition que Nicolas valide.

## Base et limites, à lire d'abord

- **Je n'ai pas lu le staging ni le wp-admin.** Cette session est bloquée par la politique réseau (403 sur
  `testnico.maisonsavann.com`), et le wp-admin demande une connexion que je n'ai pas et ne dois pas avoir.
  L'audit du site repose donc sur les **sources des pages** du dépôt (`projects/site-v2/pages/`, source de vérité
  du contenu), les **brouillons des pages de terroir** (Drive, 29 et 30/09) et les audits du 27/09 au 30/09.
  Ce qui est en ligne sur le staging peut différer de quelques textes : à recouper.
- **Aucun volume de recherche** n'existe (manquant, Nicolas doit les relever). Je hiérarchise donc par
  **intention, concurrence et écart**, pas par volume. C'est plus sûr qu'un chiffre inventé.
- La mesure de présence des termes (§2) porte sur les sources statiques : accueil, à propos, pro, contact, FAQ
  révisée. Elle **ne couvre pas** les fiches SureCart (contenu dynamique) ni les 7 pages de terroir déjà en ligne
  sur le staging (je n'ai lu que le brouillon Bolovens).
- Recherches web faites avec un moteur orienté États-Unis : à recouper sur Google France.

## 1. Verdict

Le site parle bien de **produits et de faits** (Laos 25 occurrences, drip bags 20, Savannakhet 9, Paris 16) mais il
lui manque le **vocabulaire que les gens et les IA emploient pour chercher**. Sept manques pèsent le plus :

1. **« Café laotien », « café asiatique », « café du Vietnam », « café de Thaïlande »** : 0 occurrence dans les
   pages statiques (m). Ce sont les requêtes du panel, et elles sont polluées par des restaurants : le mot seul ne
   suffit pas, il faut l'accompagner de mots de produit (voir §3.1).
2. **« Arabica » et « robusta »** : 0 occurrence (m), alors qu'un lot de la gamme est un robusta et que le panel
   pose deux questions sur le robusta de spécialité. « Fine robusta » : 0.
3. **« Import direct » / « importation directe »** : 0 (m). C'est **la phrase qu'aucune autre source ne peut
   prononcer** : Perplexity a cherché et conclu qu'aucun torréfacteur français ne le documente (m, 29/09). Elle
   doit apparaître en toutes lettres, sur les pages Laos, pour les Bolovens seulement.
4. **« Score SCA »** : 0 (m) ; « SCA » seul apparaît 5 fois. Le panel pose « comment lire un score SCA » et « café
   du Laos noté 85 ou plus ».
5. **Doi Chang, Mae Jan Tai, Caturra, Paksong, Phonsavan, altitude** : 0 dans les pages statiques (m). À vérifier
   dans les pages de terroir en ligne : ce sont elles qui doivent les porter.
6. **Variantes d'orthographe** : « Bolaven » (0), « Xiengkhouang » écrit sans espace une fois (m). Les moteurs
   traitent ces formes comme des requêtes différentes.
7. **Lieu incohérent entre les surfaces** : Paris (atelier Altura, FAQ), Frolois (siège légal, mentions), Nancy
   (adresse du profil Instagram, 9,8 % de l'audience) (m). Pour le GEO, c'est le **défaut d'entité** à corriger en
   premier : voir §6.

Les formules interdites par la charte (« sourcé directement », « exclusivement », « d'exception », « authentique »,
« 100 % arabica ») sont absentes de ces sources (m). **Mais deux affirmations non prouvées y figurent** :
« **Meilleur café du Laos 2021** » (accueil et notre histoire) et « **Une coopérative de femmes** au nord de Sumatra »
(notre histoire, section Gayo) (m). La seconde contredit la correction du 29/09 (le Sumatra Gayo n'est pas produit par une
coopérative de femmes) et explique très probablement pourquoi ChatGPT l'a attribuée au site (h). Détail au §6.3.

## 2. Ce que les sources actuelles contiennent, terme par terme (m, 30/09)

Occurrences dans : accueil, boutique, gabarit fiche, FAQ, notre histoire, pro, contact, FAQ révisée du lot 100,
texte « histoire et pro » révisé. Total, tous fichiers confondus.

| Groupe | Bien couvert (≥ 5) | Faible (1 à 4) | Absent (0) |
|---|---|---|---|
| Générique | café de spécialité 6, Asie du Sud-Est 6, torréfaction 6 | café d'Asie 2, torréfacteur 1, SCA 5 (seulement comme étiquette « SCA 83 », jamais expliqué) | **café asiatique, score SCA** |
| Laos | Laos 25, Xieng Khouang 6, Bolovens 5 | plateau des Bolovens 4, café du Laos 3, Nambeng 3, Catimor 3, Keoset 1 | **café laotien, Bolaven, Paksong, Phonsavan, Caturra** |
| Import | | en direct 4, conteneur 1, approvisionnement direct 1 | **import direct, importation directe** |
| Thaïlande | Thaïlande 10 | Chiang Rai 3, Suchart 1 | **café de Thaïlande, Doi Chang, Mae Jan Tai, Akha** |
| Vietnam | Vietnam 9 | Son La 3, Kanang 1 | **café du Vietnam, arabica, robusta, fine robusta** |
| Indonésie | Indonésie 10 | Gayo 3, Sumatra 2, Takengon 2, wet-hulled 2 | giling basah |
| Format | drip bag(s) 20, en grains 10 | filtre individuel 1, V60 2, piston 1, mouture 2, espresso 4 | **sachet filtre, expresso** |
| Preuve | | lavé 4, nature 4, cupping 2, dégustation 1 | **Diedrich, Cropster, honey, altitude** |
| Lieu | Paris 16, Savannakhet 9 | Frolois 2, Altura 2 | **Nancy** |

Attention : le compte de « drip bag(s) » est gonflé par le fichier de textes révisés (13 sur 20, 2 600 mots) ; sur les pages
elles-mêmes : accueil 2, boutique 1, pro 4.

## 3. Règles de vocabulaire

### 3.1 Désambiguïser avec des mots de produit, pas de lieu

Les suggestions Google (m, 29/09) montrent que quatre termes centraux sont captés par un autre sens :

| Terme | Ce que Google propose (m) | Mots à mettre à côté pour garder le sens « café » |
|---|---|---|
| café asiatique | 10 suggestions sur 10 : restaurants | café de spécialité, **grains**, **arabica**, torréfié, **torréfacteur**, tasse, origine |
| café laotien | 9 sur 10 : restaurants laotiens | café du Laos de spécialité, **lot**, **coopérative**, **altitude**, variété (Caturra, Java, Catimor), **torréfié** |
| plateau des Bolovens | 8 sur 10 : tourisme (scooter, combien de jours) | **café** du plateau des Bolovens, **récolte**, **caféiers**, **coopérative Nambeng**, arabica, Paksong |
| café d'Inde | 80 % « cochon d'Inde » | à ne pas viser (horizon prospectif) |

Règle : le **H1**, la **meta description** et le **balisage** de chaque page pays ou terroir contiennent le mot « café »
**et** deux mots de produit. Le balisage dit `Product` ou `Place`, jamais `Restaurant` ni `TouristAttraction`.

### 3.2 Un terme, une page

Pour éviter que deux pages se concurrencent sur la même requête :

| Requête | Page qui la porte | Pages qui la mentionnent seulement |
|---|---|---|
| café du Laos, café laotien | pilier `/terroirs/laos/` | accueil, fiches Laos, FAQ |
| plateau des Bolovens (avec « café ») | page Bolovens | pilier Laos, offre des Bolovens |
| Xieng Khouang, Keoset | page Xieng Khouang | pilier Laos, fiche produit |
| café de Thaïlande, Doi Chang | pilier Thaïlande | pages Doi Chang, Mae Jan Tai, Nan |
| café du Vietnam, arabica vietnamien | pilier Vietnam | page Son La |
| robusta de spécialité, fine robusta | article `/journal/` dédié | fiche du Robusta des Bolovens |
| drip bag, café filtre individuel | fiche drip bags | FAQ, accueil, page Pro |
| café de spécialité (définition) | article « qu'est-ce que » | tout le site, en lien |

### 3.3 Variantes et orthographes à couvrir dans le texte (une fois, en contexte)

| Forme principale | Variantes à écrire au moins une fois sur la page |
|---|---|
| plateau des Bolovens | Bolaven, « plateau des Bolaven », Paksong, Champassak |
| Xieng Khouang | Xiengkhouang, Phonsavan |
| Doi Chang | Doi Chaang (ce que taperont les anglophones), Chiang Rai |
| Sumatra Gayo | Takengon, Aceh, « Gayo Mountain » (concurrent, ne pas reprendre) |
| drip bag | drip bags, filtre individuel, sachet filtre, café filtre en sachet |
| espresso | expresso (forme française courante) |
| lavé / nature | washed, natural, honey (une ligne d'explication, pas de jargon seul) |
| café de spécialité | specialty coffee, café de spécialité noté 80 ou plus (SCA) |

### 3.4 Réponse d'abord (AEO)

Chaque page qui répond à une question ouvre par **une phrase de 40 à 60 mots qui se comprend seule**, sujet nommé,
un fait vérifiable (nom, chiffre, date, lieu). Les questions sont posées **comme les gens les posent**, avec la
formulation du panel (§5), pas avec un titre littéraire. Modèle :

> **Où acheter du café de spécialité du Laos en France ?** Maison SAVANN vend en ligne des cafés de spécialité du
> Laos, torréfiés à Paris : un Xieng Khouang lavé et le Vad Si Tong, et, dès la mi-octobre 2026, quatre lots de la
> coopérative Nambeng (plateau des Bolovens) importés en direct.

La phrase ci-dessus est un **modèle** : chaque fait qu'elle contient doit être confirmé par Nicolas avant usage (§6).

### 3.5 Formule de la phrase citable (GEO)

`[Café] + [terroir précis] + [altitude] + [qui le cultive] + [variété et process] + [score et qui l'a noté] + [torréfié où, par qui]`

Exemple valable si les faits sont confirmés : « Le Vad Si Tong est un Catimor lavé du plateau des Bolovens, cultivé à
[altitude à confirmer] par une plantation familiale, noté 82 par le fournisseur, torréfié à Paris par Maison SAVANN. »
Une phrase sans nom de personne, de lieu ou de chiffre est décorative : on la coupe.

## 4. Fiche de termes, page par page

Pour chaque page : **S**EO (ce qu'on cherche à ranker), **A**EO (la question à laquelle elle répond en tête), **G**EO
(entités et preuves qui la rendent citable). Les longueurs sont comptées (c).

### 4.1 Accueil `/`

| | |
|---|---|
| **Rôle** | Poser l'entité : qui, quoi, où, pour qui. |
| **Title** (52) | `Maison SAVANN \| Café de spécialité d’Asie du Sud-Est` |
| **Meta** (147) | `Maison SAVANN, torréfacteur de cafés de spécialité d’Asie du Sud-Est : Laos, Thaïlande, Vietnam, Indonésie. Grains et drip bags, torréfiés à Paris.` |
| **S** | café de spécialité d'Asie du Sud-Est ; torréfacteur ; Laos, Thaïlande, Vietnam, Indonésie ; drip bags ; café en grains |
| **A** | « Qui est Maison SAVANN ? » (Q20 du panel) : une phrase d'ouverture qui répond seule |
| **G** | nom exact « Maison SAVANN » (variante « Maison Savann » dans `alternateName`), fondateurs nommés, date (lancement mai 2026), lieu, `sameAs` (Instagram, Facebook, LinkedIn, Google Business) |
| **Ne pas écrire** | « sourcé directement » (faux pour 4 cafés sur 5), « exclusivement », « d'exception » |
| **État** | terroirs et drip bags présents ; **manquent** « torréfacteur » en position forte, la nature de l'offre en une phrase, le lieu cohérent (§6.1) |

### 4.2 Pilier Laos `/terroirs/laos/`

| | |
|---|---|
| **Rôle** | Gagner « le café du Laos en France » : grappe la plus ouverte (m). |
| **Title** (53) | `Café du Laos de spécialité : terroirs, variétés, lots` |
| **Meta** (153) | `Café du Laos de spécialité : plateau des Bolovens et Xieng Khouang, altitudes, variétés, process. Nos lots en grains, dont un conteneur en import direct.` |
| **H1** | Le café du Laos de spécialité : terroirs, variétés, ce qu'il donne en tasse |
| **S** | café du Laos ; café laotien de spécialité (avec « arabica », « lot », « coopérative ») ; café de spécialité du Laos ; café du Laos en France ; meilleur café du Laos (seulement si le classement est sourcé) ; Bolovens, Bolaven ; Xieng Khouang |
| **A** | Q1 « Où acheter du café de spécialité du Laos en France ? » ; Q3 « Qui vend du café laotien de spécialité en ligne ? » ; Q14 « Quelle est l'histoire du café au Laos ? » ; Q17 « Un torréfacteur français importe-t-il directement du café du Laos ? » ; Q18 « Quel café du Laos a un score SCA de 85 ou plus ? » |
| **G** | importation directe (Bolovens seulement) ; coopérative Nambeng (Lao Ngam, Salavan) ; Lao Green Coffee Competition 2025, 1re place arabica, 87,68 ; premiers caféiers plantés par les Français vers 1915 ; variétés Caturra jaune, Java, Catimor, Robusta ; famille à Savannakhet, voyage sur le plateau |
| **Ne pas écrire** | « la première exportation » de Nambeng (probablement faux : vente aux enchères en 2022), « 95 % du café laotien » (non daté), « importé en direct » pour Xieng Khouang |
| **Panel** | Q1, Q3, Q14, Q17, Q18 : Maison SAVANN **non citée** aujourd'hui (m, Perplexity) |

### 4.3 Page Bolovens `/terroirs/laos/plateau-des-bolovens/`

Slug à trancher : le brouillon dit `/bolovens/`, le plan de requêtes dit `/plateau-des-bolovens/`. Je recommande le second
(c'est la requête réellement tapée), avec « café » dans le title et le H1 pour écarter le sens touristique.

| | |
|---|---|
| **Title** (51, existant) | `Café des Bolovens (Laos) : histoire, chiffres, lots` |
| **Meta** (149, existante) | `Plateau des Bolovens, sud du Laos : café planté vers 1915, 1 000 à 1 350 m. Coopérative Nambeng, arabica primé en 2025, et nos lots en import direct.` |
| **H1** (existant) | Café du plateau des Bolovens (Laos) |
| **S** | café Bolovens ; café du plateau des Bolovens ; café laos bolaven ; café Paksong ; café Nambeng |
| **A** | Q2 « Quel est le meilleur café du plateau des Bolovens ? » (répondre avec le lot primé et son score, sans superlatif) ; « Où est le plateau des Bolovens ? » ; « Le café des Bolovens est-il de l'arabica ? » |
| **G** | Nambeng Coffee Cooperative (fondée le 3 novembre 2021, 17 familles, village vers 1 000 à 1 100 m) ; distinctions 2022, 2023, 2025 ; 120 kg par lot ; conteneur mi-octobre 2026 ; mesures de Maison SAVANN (Vad Si Tong : 685 g/L, 11,0 %) |
| **Ne pas écrire** | « Bolaven Coffee » comme indication géographique protégée (statut non relu), le nom de l'importateur (décision ouverte), des prix |
| **À ajouter** | l'orthographe « Bolaven » une fois ; la phrase « importation directe » ; « Notre dégustation » (encore vide dans le brouillon) |

### 4.4 Page Xieng Khouang `/terroirs/laos/xieng-khouang/`

| | |
|---|---|
| **Title** (52) | `Café Xieng Khouang (Laos) : coopérative Keoset, lavé` |
| **Meta** (155) | `Café de Xieng Khouang, nord du Laos : le projet Keoset et ses familles de producteurs, Catimor lavé, altitude et tasse. Torréfié à Paris par Maison SAVANN.` |
| **S** | café Xieng Khouang ; Keoset ; Phonsavan ; Catimor lavé ; café du Laos lavé |
| **A** | « Qu'est-ce que le café de Xieng Khouang ? » ; « Qu'est-ce qu'un café lavé ? » |
| **G** | projet Keoset (200 familles autour de Phonsavan) ; altitude **à vérifier** (1 500 à 1 600 m dans une proposition, 1 100 à 1 400 m dans une autre) ; score et **qui l'a noté** |
| **Ne pas écrire** | « dirigée par des femmes » et « meilleur café (lavé) du Laos en 2021 » tant que non sourcés (§6.3) ; l'accueil et « notre histoire » portent déjà « Meilleur café du Laos 2021 » |

### 4.5 Pilier Thaïlande `/terroirs/thailande/`

Concurrence : Crack Cafés (article, en tête), Cafés Dessertine, Le Panier à Café et KKO Thailand (collections dédiées) (m).
Il faut une **vraie page pilier avec plusieurs références**, pas un article seul.

| | |
|---|---|
| **Title** (56) | `Café de Thaïlande de spécialité : Doi Chang, Mae Jan Tai` |
| **Meta** (140) | `Café de Thaïlande de spécialité : Doi Chang, Mae Jan Tai et Nan, dans le nord du pays. Variétés, fermentations, altitudes et cafés à goûter.` |
| **S** | café de Thaïlande ; café thaïlandais de spécialité (avec « arabica », « grains », « Chiang Rai ») ; Doi Chang café ; Mae Jan Tai ; Nan ; fermentation anaérobie |
| **A** | Q4 « Où trouver du café de Thaïlande, Doi Chang, en France ? » ; « Où pousse le café en Thaïlande ? » ; « Qu'est-ce qu'une fermentation anaérobie ? » |
| **G** | Suchart (Mae Jan Tai, Chiang Rai, 1 300 m, fermentation de 72 h) ; Doi Chang **dans la province de Chiang Rai** (et non Chiang Mai, corrigé le 29/09) ; village fondé par des Lisu en 1915, Akha depuis 1983 (Lovethailand, lu) ; Kenneth Davids, Coffee Review, 10/02/2014 (cité) |
| **Anglais utile (h)** | les suggestions de « Doi Chang café » sont surtout anglaises (« coffee farm », « estate », « village ») : une ligne « Doi Chang coffee (Doi Chaang) » suffit |
| **Article associé** | `/journal/` « Café de Thaïlande : Doi Chang, Mae Jan Tai et Nan » (49) |

### 4.6 Pilier Vietnam `/terroirs/vietnam/` et page Son La

Concurrence : Phin Mi (arabica Lâm Đồng nommé) et Hanoi Corner (**single origin Son La déjà pris**) (m).
**Éviter Son La comme angle principal du pilier** ; l'utiliser comme page fille avec l'indication géographique et
Kanang.

| | |
|---|---|
| **Title** (49) | `Café du Vietnam de spécialité : arabica de Son La` |
| **Meta** (150) | `Café du Vietnam de spécialité : l’arabica de Son La, dans le nord du pays. Variété Catimor, indication géographique, notes en tasse, torréfié à Paris.` |
| **S** | café du Vietnam ; arabica vietnamien de spécialité ; café vietnamien arabica ou robusta ; café de spécialité Vietnam ; Son La |
| **A** | Q5 « Quel torréfacteur français propose un arabica vietnamien de spécialité ? » ; Q6 « Où acheter du café du Vietnam, région de Son La ? » ; Q19 « Quelle différence entre le café vietnamien et le café laotien de spécialité ? » ; « Le café vietnamien est-il du robusta ? » (le Vietnam produit surtout du robusta : Kanang est un arabica Catimor) |
| **G** | Kanang, Son La, 1 200 m, nature, noté 84 (à préciser : par qui) ; indication géographique ; Rainforest Alliance ; Leo Van Bun (CARE, 2020) et La Pham Quang An (Vietnam News, 2018) cités |
| **Ne pas écrire** | « fine robusta du Vietnam » pour Kanang (c'est un arabica) |

### 4.7 Pilier Indonésie `/terroirs/indonesie/` et page Gayo

Origine la plus disputée (6 torréfacteurs et plus) : ne viser que ce qui est spécifique.

| | |
|---|---|
| **Title** (45) | `Café d’Indonésie de spécialité : Sumatra Gayo` |
| **Meta** (150) | `Café d’Indonésie de spécialité : le Sumatra Gayo de Takengon, sur sol volcanique. Process wet-hulled (giling basah), notes en tasse, torréfié à Paris.` |
| **S** | Sumatra Gayo café ; café d'Indonésie de spécialité ; wet-hulled ; giling basah ; Takengon |
| **A** | Q7 « Quel est le meilleur café de Sumatra Gayo en France ? » ; « Qu'est-ce qu'un café wet-hulled ? » |
| **G** | Garuda G1, Takengon, sol volcanique, process wet-hulled ; **aucune altitude** (la fiche n'en donne pas : ne pas en inventer) |
| **Ne pas écrire** | « coopérative de femmes » : c'est écrit aujourd'hui dans `notre-histoire.html` (« Une coopérative de femmes au nord de Sumatra ») et ChatGPT l'a repris le 29/09 ; à corriger. Pas de **kopi luwak** (controverse, Maison SAVANN n'en vend pas) |

### 4.8 Fiches produit café (5 fiches)

Motif du title : `Café du [pays] [terroir] [process], [format] | Maison SAVANN`. Motif du H1 : `[Pays], [terroir], [process]`.

- **Ouverture** : la phrase citable (§3.5), sous le H1, avant le tableau technique (l'ordre du DOM décide de ce qui est lu).
- **S** : café du [pays] ; café [terroir] ; [variété] ; « en grains 250 g » ; « lavé » ou « nature » avec une ligne d'explication.
- **A** : « Quel goût a ce café ? » (notes), « Comment le préparer ? » (lien V60/espresso).
- **G** : `Product` avec `brand`, `sku`, `priceCurrency: EUR`, sans `aggregateRating` tant qu'il n'y a pas d'avis produit.
- **À écrire** : quel est le lot, qui l'a noté (le score du producteur n'est pas celui de Maison SAVANN), la date de torréfaction affichée.
- **À ne pas écrire** : « 100 % arabica » (un lot est un robusta).

### 4.9 Fiche drip bags

| | |
|---|---|
| **Title** (47) | `Drip bags café de spécialité : boîte de 8 ou 12` |
| **Meta** (148, existante D4) | `Drip bags Maison Savann : café de spécialité d'Asie du Sud-Est en filtres individuels, sans matériel. Boîtes de 8 ou 12, dès 20 €, torréfié à Paris.` |
| **S** | drip bag café ; café filtre individuel ; café en sachet filtre ; café de spécialité sans machine ; drip bags France |
| **A** | Q12 « Où acheter des drip bags de café de spécialité en France ? » ; « Comment préparer un drip bag ? » (`HowTo`, 4 étapes chiffrées : eau à 90 à 95 °C à confirmer par Nicolas) ; « Un drip bag est-il aussi bon qu'un café moulu ? » |
| **G** | Terres de Café tient la place avec la gamme la plus large (m) : Maison SAVANN se distingue par les origines nommées et la torréfaction à Paris |
| **Expressions issues d'Instagram (h)** | le reel du 20/08 (34,1 K vues, en partie payé) parlait de « café soluble », « crash-test », « sans machine », « en pleine montagne », « voyage ». Ces mots correspondent à des intentions de recherche (« alternative au café soluble », « café de voyage », « café de randonnée ») : à intégrer sur la fiche, à valider par les volumes et la Search Console après la bascule |

### 4.10 Notre histoire `/notre-histoire/`

Page d'autorité : les IA cherchent **qui parle**.

- **S** : « Maison SAVANN », projet familial, café du Laos, Savannakhet.
- **A** : « Qui est Maison SAVANN ? », « Qui sont les fondateurs ? ».
- **G** : les prénoms des fondateurs et leur rôle, les dates (voyage au Laos août-septembre 2025, lancement mai 2026, premier conteneur mi-octobre 2026), le lieu **cohérent** (§6.1), la structure (SAS), `Person` relié à `Organization` par `founder`. Aujourd'hui la page dit « nous » du début à la fin : une IA ne peut rattacher aucune expertise à un « nous ».
- **Ne pas écrire** : « relations privilégiées avec les coopératives locales » (formule de la V1, non autorisée par la charte).

### 4.11 Page Pro `/pro/`

- **Title** (54) `Café de spécialité pour professionnels | Maison SAVANN` ; **meta** (140, D14) : `Café de spécialité d’Asie du Sud-Est pour coffee shops, restaurants et hôtels : grains, drip bags, échantillons et tarifs selon vos volumes.`
- **S** : café de spécialité pour coffee shop ; fournisseur de café pour restaurant ; café pour hôtel (drip bags en chambre) ; torréfacteur pour professionnels ; échantillons.
- **A** : « Comment commander du café en volume ? », « Proposez-vous des échantillons ? »
- **G** : clients réels nommés avec leur accord (une mention tierce : voir §7), formulaire unique. La page ne reçoit qu'**un** lien sortant aujourd'hui (m) : à relier depuis la FAQ.

### 4.12 FAQ `/foire-aux-questions/`

Les 14 réponses révisées (lot 100) suivent le bon format (réponse d'abord). **Questions à ajouter**, formulées comme le panel :

| Question | Pourquoi |
|---|---|
| Le robusta peut-il être un café de spécialité ? (Q9) | question de panel, un robusta arrive mi-octobre |
| Qu'est-ce que le fine robusta ? (Q10) | terme d'initié, suggestions riches |
| Comment lire un score SCA ? (Q15) | « SCA » absent des réponses, 0 occurrence de « score SCA » |
| Quelle différence entre lavé, nature et honey ? | 0 occurrence de « honey » ; utile en AEO |
| Comment préparer un drip bag ? | 4 étapes, `HowTo` |
| Combien de temps se conserve un café torréfié ? | question fréquente, réponse simple |
| Livrez-vous en Belgique ou dans l'Union européenne ? | le texte proposé D8 dit la vérité : France métropolitaine, autres pays sur demande |

Règle : chaque réponse **contient un lien** vers la page qui développe (la FAQ avait 0 lien sortant, m 27/09).

### 4.13 Articles `/journal/` et guides `/preparer/`, dans l'ordre

| # | Page | Requête | Pourquoi | Quand |
|---|---|---|---|---|
| 1 | Robusta de spécialité : qu'est-ce que le fine robusta ? (title 55) | Q9, Q10 | sujet éditorial : les médias gagnent, un seul produit concurrent (Café In Fine) ; le Robusta des Bolovens sert d'exemple | avant mi-octobre |
| 2 | Café de Thaïlande : Doi Chang, Mae Jan Tai et Nan (49) | Q4 | Crack Cafés tient la place avec un article | après le pilier |
| 3 | Histoire du café au Laos : des Français à nos jours (51) | Q14 | pas de marque citée par les IA (page d'autorité) | après le pilier Laos |
| 4 | Comment lire un score SCA : 80, 85, 87 sur 100 (46) | Q15, Q18 | terme absent du site | rapide |
| 5 | Comment faire un V60 : ratio, température, mouture (50) | « comment faire un V60 » | requêtes de préparation, `HowTo` | rapide |
| 6 | Comment préparer un drip bag : eau, temps, gestes (49) | drip bag | complète la fiche | rapide |
| 7 | Qu'est-ce que le café de spécialité ? | définition | page d'autorité secondaire (terrain très occupé) | plus tard |
| 8 | Café laotien ou vietnamien de spécialité : les différences | Q19 | comparaison, 2 pays de la gamme | plus tard |

Metas proposées : robusta `Le robusta peut-il être un café de spécialité ? Ce qu’est le fine robusta, comment il est noté selon le protocole SCA et ce qu’il donne en tasse.` (145) ;
SCA `Que veut dire un score SCA de 85 sur 100 ? Le seuil de 80 points, ce que note un dégustateur et comment lire l’étiquette d’un café de spécialité.` (145) ;
histoire du Laos `Histoire du café au Laos : les premiers caféiers plantés vers 1915 sur le plateau des Bolovens, la place du robusta et l’essor de l’arabica de spécialité.` (154).

## 5. Le panel des 20 requêtes, relié aux pages

Formulation figée. Ce tableau dit **quelle page doit répondre** à chaque question. Résultat du 29/09 : Maison SAVANN
citée sur **1 requête sur 20** (Q20, quand on la nomme), sur Perplexity (m).

| # | Question du panel | Page cible | Intention |
|---|---|---|---|
| 1 | Où acheter du café de spécialité du Laos en France ? | pilier Laos | achat |
| 2 | Quel est le meilleur café du plateau des Bolovens ? | page Bolovens | comparaison |
| 3 | Qui vend du café laotien de spécialité en ligne ? | pilier Laos, boutique | achat |
| 4 | Où trouver du café de Thaïlande, Doi Chang, en France ? | pilier Thaïlande | achat |
| 5 | Quel torréfacteur français propose un arabica vietnamien de spécialité ? | pilier Vietnam | achat |
| 6 | Où acheter du café du Vietnam, région de Son La ? | page Son La | achat |
| 7 | Quel est le meilleur café de Sumatra Gayo en France ? | page Gayo | comparaison |
| 8 | Quelle est la meilleure marque de café de spécialité asiatique en France ? | accueil, `/terroirs/` | comparaison |
| 9 | Le robusta peut-il être un café de spécialité ? | article robusta, FAQ | info |
| 10 | Qu'est-ce que le fine robusta ? | article robusta, FAQ | info |
| 11 | Quel torréfacteur français est spécialisé dans le café asiatique ? | accueil, à propos | marque |
| 12 | Où acheter des drip bags de café de spécialité en France ? | fiche drip bags | achat |
| 13 | Quel est le meilleur torréfacteur de café de spécialité à Paris ? | fiche Google Business | local |
| 14 | Quelle est l'histoire du café au Laos ? | article histoire | info |
| 15 | Qu'est-ce qu'un café de spécialité, et comment lire un score SCA ? | article SCA, FAQ | info |
| 16 | Quel café choisir pour découvrir les cafés d'Asie ? | coffret découverte, `/terroirs/` | conseil |
| 17 | Y a-t-il un torréfacteur français qui importe directement du café du Laos ? | pilier Laos, page Bolovens | GEO stratégique |
| 18 | Quel café du Laos a un score SCA élevé, autour de 85 ou plus ? | fiches Laos, pilier Laos | comparaison |
| 19 | Quelle différence entre le café vietnamien et le café laotien de spécialité ? | article comparaison | info |
| 20 | Qui est Maison SAVANN ? | accueil, notre histoire | entité |

Quatre requêtes valent le plus : **Q17** (aucune source concurrente ne peut y répondre), **Q11 et Q8** (la bannière
« café asiatique » a un titulaire partiel, Phin Mi, mais mono-origine), **Q1**.

## 6. Contradictions et faits à trancher avant d'écrire

| # | Point | Pourquoi ça compte | Qui |
|---|---|---|---|
| 6.1 | **Lieu** : Paris (atelier Altura), Frolois (siège légal), Nancy (adresse Instagram, 9,8 % de l'audience) | Nom, adresse et lieu doivent être identiques sur le site, Google Business, Instagram et les mentions légales. Le title « torréfacteur à Paris » suppose que c'est vrai partout | Nicolas |
| 6.2 | **« Import direct »** : les Bolovens seulement ; le conteneur est partagé avec un importateur partenaire qui gère la douane | Le terme est l'atout n°1 : il doit être exact. Le nommer pour les 4 cafés actuels est faux (charte) | Nicolas |
| 6.3 | Deux affirmations non prouvées : « Meilleur café du Laos 2021 » (accueil, notre histoire, fiche Xieng Khouang, `llms.txt`) et « coopérative de femmes » (notre histoire pour le Gayo ; « dirigée par des femmes » pour Keoset dans une proposition) | La seconde est **fausse** pour le Gayo (correction du 29/09) et ChatGPT l'a reprise. Une IA cite ce qui est écrit : il faut corriger la source | Nicolas |
| 6.4 | Altitudes divergentes : Xieng Khouang (1 500 m sur l'accueil, 1 500 à 1 600 m dans une proposition, 1 100 à 1 400 m dans l'audit du 27/09), Bolovens (800 ou 1 000 à 1 350 m), Vad Si Tong (1 300 ou 1 100 m) | Une IA cite la valeur la plus visible : elle doit être juste | Nicolas |
| 6.5 | **Qui a noté chaque café** : les scores viennent du fournisseur, pas de Maison SAVANN | Écrire « noté 85 » sans dire par qui est trompeur. Idéal : la fiche de cupping de Nicolas, datée | Nicolas |
| 6.6 | « Torréfié à Paris » pour les **drip bags** (D4 à vérifier) | Une claim par produit doit être exacte | Nicolas |
| 6.7 | Slug de la page Bolovens | `/bolovens/` ou `/plateau-des-bolovens/` : une seule forme, avec 301 depuis l'autre | Claude, Nicolas |
| 6.8 | Publication des données de torréfaction mesurées | Contenu que personne d'autre ne publie en France, mais décision de Nicolas | Nicolas |

## 7. Plan d'action, par ordre

Effet : **S** = SEO, **A** = AEO, **G** = GEO. Effort : F faible, M moyen. Avant ou après la bascule (le staging est fermé aux
moteurs : rien de ce qui suit ne sera lu avant).

| # | Action | Effet | Effort | Quand | Qui |
|---|---|---|---|---|---|
| 1 | Trancher §6.1 à §6.6 (lieu, import direct, affirmations, altitudes, scores) | S A G | F | maintenant | Nicolas |
| 2 | Corriger « coopérative de femmes » (notre histoire, Gayo) et retirer ou sourcer « Meilleur café du Laos 2021 » (accueil, notre histoire, fiche, `llms.txt`) | G | F | avant bascule | Nicolas |
| 3 | Poser les 6 titles et metas proposés (accueil, Laos, Xieng Khouang, Thaïlande, Vietnam, Indonésie) | S | F | avant bascule | Claude prépare, Nicolas valide |
| 4 | Écrire la phrase « importation directe » sur le pilier Laos et la page Bolovens | G | F | avant bascule | Nicolas confirme les faits |
| 5 | Compléter la FAQ : 7 questions du §4.12, chacune avec un lien | A | F | avant bascule | Claude |
| 6 | Ajouter les variantes du §3.3 (Bolaven, Doi Chaang, sachet filtre, expresso, honey) | S | F | avant bascule | Claude |
| 7 | Article robusta de spécialité, avec le robusta des Bolovens | S A G | M | avant mi-octobre | Claude rédige, Nicolas valide |
| 8 | Page d'autorité « notre histoire » avec fondateurs nommés, dates, lieu, `Person` | G | F | avant bascule | Nicolas fournit les faits |
| 9 | Pilier Thaïlande avec plusieurs références, puis l'article Doi Chang | S A | M | après bascule | Claude |
| 10 | Guides V60, drip bag, score SCA | A | M | après le pilier Laos | Claude |
| 11 | Off-site autour du conteneur (presse café, annuaire `lestorrefacteurs.fr`, Google Business, un client B2B qui écrit sur nous) | G | M | mi-octobre | Nicolas |
| 12 | Relever les volumes de recherche des 44 requêtes et refaire ce classement avec eux | S | F | avec l'étape outillage | Nicolas |

## 8. Comment saura-t-on que ça marche

1. **Panel des 20 requêtes**, mêmes formulations, une fois par mois, sur ChatGPT, Perplexity, Google, Gemini, Copilot : cité
   oui ou non, rang, sources concurrentes. Référence de départ : **1 sur 20** (Perplexity, 29/09). L'onglet GEO du cockpit
   sert à les saisir.
2. **Présence des termes** : relancer la mesure du §2 après chaque dépôt (script à écrire, lecture seule sur le staging une
   fois le domaine autorisé). Objectif : les termes en gras du §2 passent de 0 à au moins 1 sur la bonne page.
3. **Search Console et Bing** après la bascule : impressions et clics par grappe de requêtes.
4. **Accès des robots IA** : 10 sur 10 en 200 (GPTBot en 429 le 29/09) : sans cela, aucun texte n'est lu par ChatGPT Search.

## 9. Ce qu'il me faut de toi

1. Les faits des §6.1 à §6.6 (lieu, import direct, femmes et 2021, altitudes, qui note les cafés, drip bags torréfiés où).
2. Ton accord sur les 6 titles et metas du §4, ou tes corrections.
3. L'autorisation du domaine `testnico.maisonsavann.com` dans les réglages réseau de la session, pour que je mesure le site réel
   au lieu de ses sources, puis relève les titles, H1 et balisages en ligne.
4. Les volumes de recherche des requêtes (Keyword Surfer ou l'outil gratuit d'Ahrefs), pour hiérarchiser sans deviner.

## Ce que je fais maintenant

1. Analyse déposée dans ce fichier. Rien n'est écrit sur le site.
2. Dès que tu me donnes le feu vert sur le §9.1 et §9.2, je prépare les textes des pages (titres, metas, phrases d'ouverture, questions
   de la FAQ) au format « à valider ligne par ligne », comme le lot 100.
3. Si tu autorises le domaine du staging, je relance la mesure de présence sur le site réel et je complète les pages de terroir
   déjà en ligne, que je n'ai pas pu lire.
