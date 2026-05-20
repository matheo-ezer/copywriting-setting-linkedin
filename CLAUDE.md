# Instructions Claude Code — copywriting-setting-linkedin

## Contexte

Ce repo contient les skills (prompts structures) pour l'agent Setting LinkedIn de Cyclon GTM. Quand tu travailles sur ce repo, tu edites des prompts d'IA, pas du code applicatif.

## Conventions de redaction d'un skill

### Sections obligatoires

Chaque skill doit contenir :

1. **Frontmatter YAML** (`---`) : `name`, `version`, `agent`, `description`
2. **Role** : ce que fait le skill en une phrase
3. **Instructions** : contexte et consignes pour l'agent
4. **Donnees recues** : inputs attendus
5. **Structure des messages** : format precis de chaque output
6. **Regles de redaction** : interdictions, format, ton
7. **Auto-scoring** : criteres d'evaluation et seuils
8. **Output JSON** : schema exact de la sortie attendue

### Format et ton

- Ton direct, operationnel, sans fluff
- Phrases courtes, imperatives
- Utiliser des listes a puces, pas de paragraphes longs
- Les interdictions sont formulees avec "Jamais" ou "Ne jamais"
- Les exemples sont concrets et contextuels

### Longueur

- Un skill tient idealement en moins de 150 lignes
- Si un skill depasse 200 lignes, envisager de le decouper

## Regles d'evolution

### Versionning

- Le champ `version` dans le frontmatter suit le format semver : `MAJOR.MINOR.PATCH`
- PATCH : correction de formulation sans changement de logique
- MINOR : ajout d'une regle, d'un angle, d'un exemple
- MAJOR : refonte de la structure ou du schema JSON de sortie

### Avant de push un changement

1. Relire le skill modifie en entier
2. Verifier que le schema JSON de sortie est coherent avec les sections precedentes
3. Verifier que les sections obligatoires sont toutes presentes
4. Verifier que les exemples et l'auto-scoring n'ont pas ete supprimes par erreur

### Ce qui doit absolument etre preserve a chaque edition

- Les exemples concrets (ils servent de few-shot pour l'agent)
- La section auto-scoring (c'est le mecanisme de qualite)
- Le schema JSON de sortie (c'est le contrat d'interface avec n8n)
- Les interdictions de redaction (elles evitent les outputs generiques)

## Roadmap des skills

| Priorite | Skill | Description |
|----------|-------|-------------|
| 1 | `skill-copywriting.md` | Redaction des messages de setting (actif) |
| 2 | `skill-signal-context.md` | Analyse contextuelle du signal d'engagement |
| 3 | `skill-auto-evaluation.md` | Scoring et evaluation de la sequence generee |
| 4 | `skill-memory-powered.md` | Apprentissage des sequences gagnantes |
| 5 | `skill-prompt-optimizer.md` | Optimisation du prompt final |

## Commandes utiles

```bash
# Voir le diff avant commit
git diff

# Push un changement
git add skills/skill-<nom>.md && git commit -m "skill-<nom>: <description du changement>" && git push

# Verifier l'URL raw apres push
curl -s https://raw.githubusercontent.com/matheo-ezer/copywriting-setting-linkedin/main/skills/skill-copywriting.md | head -5
```
