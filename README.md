# copywriting-setting-linkedin

Source de verite des skills de copywriting pour l'agent **Setting LinkedIn** de Cyclon GTM.

## A quoi sert ce repo

Cyclon GTM est une structure de conseil GTM B2B. L'agent Setting LinkedIn recoit en input un profil prospect, une entreprise, un signal d'engagement (visite/like/comment/lead magnet) et un contexte ICP. Il genere en output 3 messages de setting LinkedIn personnalises au format JSON.

Ce repo centralise les skills (prompts structures) qui pilotent cet agent.

## Audiences

| Audience | Usage |
|----------|-------|
| **Agent n8n** | Lit les skills via HTTP raw URL GitHub pour les injecter dans les prompts |
| **Claude Code** | Itere, ameliore et versionne les skills depuis le terminal |

## Skills disponibles

| Fichier | Description | Statut |
|---------|-------------|--------|
| `skills/skill-copywriting.md` | Redaction des 3 messages de setting LinkedIn personnalises | Actif |

## Roadmap des futurs skills

| Fichier prevu | Description |
|---------------|-------------|
| `skills/skill-signal-context.md` | Analyse contextuelle du signal pour guider le copywriting |
| `skills/skill-auto-evaluation.md` | Auto-evaluation et scoring de la sequence generee |
| `skills/skill-memory-powered.md` | Apprentissage des sequences gagnantes |
| `skills/skill-prompt-optimizer.md` | Optimisation du prompt final |

## Convention de nommage

- Tous les skills sont dans le dossier `/skills/`
- Format : `skill-<nom>.md`
- Un skill = un fichier = une responsabilite unique
- Chaque skill contient un frontmatter YAML (`---`) avec les metadonnees

## URL raw pour n8n

Pattern pour acceder au contenu brut d'un skill :

```
https://raw.githubusercontent.com/matheo-ezer/copywriting-setting-linkedin/main/skills/<nom-du-fichier>.md
```

Exemple :
```
https://raw.githubusercontent.com/matheo-ezer/copywriting-setting-linkedin/main/skills/skill-copywriting.md
```

## Comment ajouter un nouveau skill

1. Creer un fichier `skills/skill-<nom>.md`
2. Inclure le frontmatter YAML avec : `name`, `version`, `agent`, `description`
3. Structurer le contenu avec les sections obligatoires (voir `CLAUDE.md`)
4. Mettre a jour le tableau "Skills disponibles" dans ce README
5. Commit + push sur `main`
