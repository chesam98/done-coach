# done-coach

Lots de messages du coach de l'app Android **Done.** : citations, anecdotes et encouragements, en français.
Ce dépôt est public et ne contient **que** ces messages, sans code ni donnée personnelle.

L'app télécharge `lots/lot-{n}.json` (n = dernier lot chargé + 1) quand plus de 80 % des messages ont été vus.
Une réponse 404 signifie « pas encore de nouveau lot ». `lot-2.json` est la copie du fichier livré dans l'app
(version 2) : il n'est jamais téléchargé, il sert de référence pour éviter les doublons. Le premier lot téléchargé est
donc `lot-3.json`.

## Format

```json
{
  "version": 3,
  "messages": [
    {"id": "l3-q-auteur-mot", "category": "citation", "domain": "science", "text": "…", "author": "…", "source": "Œuvre, discours ou lettre, date"},
    {"id": "l3-a-sujet", "category": "anecdote", "domain": "invention", "text": "…"},
    {"id": "l3-e-sujet", "category": "encouragement", "domain": "general", "text": "…"}
  ]
}
```

- `version` = n du nom de fichier.
- `id` : unique dans **tous** les lots, préfixé `l{n}-q-` / `l{n}-a-` / `l{n}-e-`.
- `category` : `citation` (auteur **et** source obligatoires), `anecdote` ou `encouragement`.
- `domain` : `acoustique`, `musique`, `science`, `entreprise`, `reves`, `apprentissage` (ou `general`).

## Règles de rédaction (non négociables)

1. **Exactitude** : uniquement des citations à l'attribution solide, avec une source précise. Pas de citation apocryphe
   ou douteuse (beaucoup de phrases attribuées à Einstein, Twain, Churchill, Edison, Ford, Lincoln, Gandhi, Confucius
   sont fausses) : dans le doute, ne pas la mettre.
2. **Thèmes** (l'utilisateur crée **We Make Waves** : un bureau d'études en acoustique et un studio de production et
   de composition musicale, surtout de musique de film). Chaque lot couvre, à parts proches :
   - l'**acoustique** (histoire, acousticiens, salles, mesure, psychoacoustique, ingénierie du son) ;
   - la **musique**, en priorité la **musique de film** (compositeurs, méthodes, histoires de partitions) ;
   - la **science** en général ;
   - l'**entrepreneuriat** (créer un bureau d'études ou un studio, premiers clients, échecs surmontés) ;
   - les **rêves et comment les réussir** (objectifs, passage à l'acte, persévérance, résultats de la recherche) ;
   - les **biais cognitifs et l'apprentissage** (effet de test, répétition espacée, illusion de maîtrise, biais de
     planification…), chaque fois avec le conseil pratique qui en découle.
3. **Anecdotes** factuelles et vérifiables, réécrites avec ses propres mots, 2 ou 3 phrases, avec dates et chiffres
   exacts. Les études citées doivent exister (auteurs, année) ; pas de résultat dont la réplication est contestée.
4. **Encouragements** : ton bienveillant et exigeant, concrets (démarrer, se concentrer, reprendre après un retard,
   se reposer vraiment), souvent liés à We Make Waves, à la composition ou à l'acoustique, sans formules creuses.
5. **Aucun doublon** avec les lots existants (ni id, ni texte, ni même idée ou anecdote déjà racontée).
6. Environ 50 messages par lot : à peu près la moitié de citations, un tiers d'anecdotes, le reste d'encouragements.
7. Citations courtes : pas de longs extraits d'œuvres sous droits d'auteur, jamais de paroles de chansons.
