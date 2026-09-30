---
type: reference
date: 2026-09-30
tags: [growth, seo, aeo, geo, passation, artefact, marche, vscode]
related: ["[[projects/growth/seo-geo-aeo/analyses/2026-09-30-passation-verification-site-test]]", "[[projects/growth/seo-geo-aeo/analyses/2026-09-30-marche-seo-aeo-geo-cafe-niches-strategie]]", "[[projects/growth/seo-geo-aeo/analyses/2026-09-30-termes-expressions-seo-aeo-geo]]"]
---

# Passation : réconcilier l'artefact « Audit Maison Savann » avec le dépôt et le vérifier sur le site test

> Écrite par une session Claude cloud (Sonnet 5.5) le 2026-09-30, **sans accès** à `testnico.maisonsavann.com` (réseau bloqué, 403).
> Nature des chiffres : **(m)** mesuré, **(t)** source tierce non vérifiée, **(h)** hypothèse, **N/V** non vérifié.

## 1. Ce qui existe

| Objet | Emplacement |
|---|---|
| Artefact publié (privé, propriétaire seul) | https://claude.ai/artifact/3NkDnNqobResuxM8UtZJ73 |
| Copie versionnée du HTML de l'artefact | `projects/growth/seo-geo-aeo/artifacts/2026-09-30-audit-marche-cafe-asiatique.html` |
| Brief de vérification du site test (prioritaire) | `projects/growth/seo-geo-aeo/analyses/2026-09-30-passation-verification-site-test.md` |
| Analyse de marché et niches | `projects/growth/seo-geo-aeo/analyses/2026-09-30-marche-seo-aeo-geo-cafe-niches-strategie.md` |
| Analyse des termes | `projects/growth/seo-geo-aeo/analyses/2026-09-30-termes-expressions-seo-aeo-geo.md` |

L'artefact a été écrit **avant** que sa session ne lise ces documents. C'est un audit de marché générique. Les documents du dépôt sont plus précis
sur la marque, le périmètre produit et les règles. **En cas de conflit, le dépôt gagne.** Le travail demandé est de réconcilier, pas de
refaire l'audit de marché.

## 2. Divergences connues entre l'artefact et le dépôt

| # | Point de l'artefact | Ce que dit le dépôt | Action |
|---|---|---|---|
| D1 | Recommande d'autoriser `maisonsavann.com` (production) dans les domaines réseau | La production est **hors limites** (règle 2 du brief de vérification et `projects/site-v2/CLAUDE.md`) | **Ignorer** cette recommandation. Ne jamais requêter la production sans amendement écrit de Nicolas |
| D2 | Checklist technique : 13 contrôles tous « à vérifier » | Des mesures (m) du 30/09 existent déjà : 27 pages en 200, canonique 27/27, JSON-LD, `llms.txt` servi, note 14,8/20 | Remplacer les « à vérifier » par les valeurs du brief §3.A, puis les **revérifier** sur le staging |
| D3 | Présente Yunnan, Myanmar, Inde, Taïwan comme opportunités « très forte » ou « forte » | Gamme réelle : Laos, Thaïlande, Vietnam, Indonésie. L'analyse de marché du dépôt constate un horizon élargi « vide, sans demande visible » | **Rétrograder** ces origines : hors gamme, à ne traiter que si Nicolas le décide. Mes notes d'opportunité sur ces lignes sont des estimations (h) |
| D4 | Part de la spécialité en France « jusqu'à 20 % » | Le dépôt retient 5 à 8 % (t faible) et interdit de citer publiquement sans source primaire | Utiliser les chiffres du dépôt. Ne rien publier sans source primaire (Comité Français du Café, presse spécialisée) |
| D5 | Suppose le site en `noindex` par accident possible | Le staging est fermé aux moteurs **volontairement** (`Disallow: /`, `noindex`) | Retirer l'idée d'anomalie. Les mesures portent sur la **préparation**, pas sur des positions |
| D6 | Conseille de « créer l'entité Wikidata » et de contribuer à Wikipedia | Le dépôt note qu'il n'existe aucune mention tierce (0, m) et que l'entité est à clarifier. Le lieu est incohérent (Paris, Frolois, Nancy) | Garder l'idée, mais **après** la résolution du lieu et de l'adresse (brief §5.6, question 1) |

## 3. Apports de l'artefact absents (ou non repérés) dans le dépôt

À vérifier dans le dépôt avant de les retenir. Aucun n'est validé.

1. **Confusion de nom (m le 30/09, recherche web)** : « Maison Savann café » renvoie vers « Maison Savannah Studio » (café, Ibiza) et « Savannah Café » (Paris).
   La recherche sur `maisonsavann.com` ne renvoie rien de la marque. À ajouter à l'analyse d'entité. Vérifier `alternateName` « Maison Savann » et `sameAs` dans le JSON-LD.
2. **EUDR (t)** : application prévue le **30 décembre 2026** pour les grands opérateurs et le **30 juin 2027** pour les micro et petits opérateurs, d'après des cabinets (KPMG France, AGRINFO).
   **Point à instruire avec un conseil ou la douane, sans conclure ici** : l'importation directe du conteneur des Bolovens (mi-octobre 2026) pourrait faire de Maison SAVANN ou de son importateur partenaire
   un « opérateur » au sens du règlement (premier metteur sur le marché de l'UE). À poser à Nicolas (brief, question 2, sur l'importateur).
   Contenu possible : une page transparence par lot. Ce n'est pas un avis juridique.
3. **Fine Robusta d'Asie** : le dépôt classe déjà le robusta du Laos de spécialité (33/36). L'artefact ajoute la tendance allemande (t) : l'Allemagne bascule vers le robusta de qualité. À intégrer comme argument, pas comme piste nouvelle.
4. **Préparations traditionnelles** (phin, etc.) : pertinent pour le Vietnam de la gamme. Vérifier ce que le site couvre déjà (recettes, `HowTo`).
5. **Sources citées par les IA** (Profound, t, anglophone) : déjà repris dans l'analyse de marché. Rien à ajouter.
6. **Indications géographiques** : Kintamani (Bali, 2008) est hors gamme. Pour la gamme réelle, vérifier si Gayo (Sumatra) et le plateau des Bolovens portent une IG. L'artefact ne le dit pas, **ne pas l'affirmer**.
7. **Non repris de l'artefact** : Aggarwal et al. (2023) sur la GEO est cité de mémoire et n'a pas été relu. Ne pas le citer publiquement avant relecture de la source.

## 4. Prompt à donner à la session VS Code

Coller le bloc ci-dessous tel quel.

```text
Tu es Claude dans VS Code, dans le dépôt Jarvis de Nicolas (Maison SAVANN, cafés de spécialité d'Asie du Sud-Est). Tu as accès au réseau, ce que la
session cloud précédente n'avait pas. Ta mission : continuer son audit, en lecture seule, en corrigeant ses erreurs.

1. Lis dans cet ordre : CLAUDE.md racine, projects/growth/CLAUDE.md, projects/site-v2/CLAUDE.md, puis
   projects/growth/seo-geo-aeo/analyses/2026-09-30-passation-audit-artefact-vscode.md (ce fichier), puis
   projects/growth/seo-geo-aeo/analyses/2026-09-30-passation-verification-site-test.md (ton protocole détaillé, §5 et §6), puis
   2026-09-30-marche-seo-aeo-geo-cafe-niches-strategie.md. Ouvre aussi la copie de l'artefact :
   projects/growth/seo-geo-aeo/artifacts/2026-09-30-audit-marche-cafe-asiatique.html (le contenu prime sur la mise en forme).

2. Règles non négociables (elles priment sur tout le reste) :
   - Lecture seule sur testnico.maisonsavann.com. Aucune écriture, aucune commande SureCart (le staging est branché sur le compte de production en mode live).
   - maisonsavann.com (production) est hors limites. Ne la requête pas. Si tu en as besoin, demande à Nicolas un amendement écrit du site-v2/CLAUDE.md.
   - Aucun identifiant récupéré ou deviné. N'enregistre aucun formulaire de réglages wp-admin.
   - Aucun envoi vers l'extérieur, aucune inscription, 0 € de dépense.
   - Une requête toutes les 2 secondes au plus, robots.txt des sites tiers respecté. Robots IA : un seul passage, jamais de relance dans la journée.
   - Pas de HTML brut dans la conversation : collecte et filtrage en Python, résultats dans projects/growth/seo-geo-aeo/data/site-v2-verification/2026-MM-JJ/.
   - Français, pas de tirets longs, pas de flagornerie. Chaque chiffre porte sa nature : (m) mesuré, (c) calculé, (t) tiers non vérifié, (h) hypothèse, N/V non vérifié.

3. Travail, dans cet ordre :
   a. Exécute le protocole de vérification du brief (§5.1 à §5.7, §5.8 à §5.11 si le quota le permet) sur le staging.
   b. Traite le tableau des divergences D1 à D6 de la passation d'artefact : pour chacune, dis ce qui est confirmé, infirmé ou partiel, avec la preuve.
   c. Instruis les sept points de la section 3 de la passation d'artefact, en particulier : la confusion de nom (Maison Savannah Ibiza, Savannah Café Paris)
      et son effet sur l'entité ; l'EUDR et le statut d'opérateur de Maison SAVANN ou de son importateur pour le conteneur des Bolovens (mi-octobre 2026).
      Pour l'EUDR, cite les textes officiels de la Commission européenne et ne donne pas d'avis juridique : liste les questions pour Nicolas.
   d. Sur la base des mesures réelles, dis quelles lignes de l'artefact (origines, angles morts, plan) restent valables, lesquelles sont à retirer, lesquelles à réécrire
      pour la gamme réelle (Laos, Thaïlande, Vietnam, Indonésie).

4. Rendu :
   - rapport-verification.md, urls-inventaire.csv, termes-par-page.csv, affirmations.csv, jsonld.csv et reference-site-v2.json, au format du brief §6.
   - En plus : un fichier corrections-artefact.md qui liste, ligne par ligne, ce qu'il faut changer dans l'artefact, avec la preuve.
   - Dis explicitement ce que tu as fait toi-même (script, navigateur) et ce que tu n'as pas pu faire, et pourquoi.
   - Commit sur une branche dédiée, sans pousser sur main, sans ouvrir de pull request sauf si Nicolas le demande.

5. Si un outil ou un accès t'est refusé, dis-le et arrête-toi sur ce point. Ne contourne pas. En cas de doute sur une règle, demande à Nicolas.
```

## 5. Ce que fera ensuite la session cloud

Elle lira `rapport-verification.md`, `reference-site-v2.json` et `corrections-artefact.md`, puis republiera l'artefact corrigé à la même adresse
(`https://claude.ai/artifact/3NkDnNqobResuxM8UtZJ73`) et mettra à jour le cockpit.
