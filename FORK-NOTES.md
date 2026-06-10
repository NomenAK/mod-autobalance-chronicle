# FORK-NOTES — mod-autobalance-chronicle

Fork de [`azerothcore/mod-autobalance`](https://github.com/azerothcore/mod-autobalance).

## Constat : delta fonctionnel nul

À ce jour, ce fork ne porte **aucune modification fonctionnelle** par rapport à
l'upstream. Les seuls commits locaux sont d'ordre documentaire / hygiène :

- `docs(capy)` : contexte Captain fork-local + `CAPY-PLATFORM` canonique ;
- `chore` : quarantaine de la config `.capy/` dans `setup_archive/*.bak`.

Tout le reste de l'historique (`git log`) est constitué de PR upstream.

## Pourquoi ce fork existe quand même

1. **Reproductibilité du build Docker AzerothCore.** Le fork épingle une révision
   stable consommée par le build Chronicle. L'upstream peut casser ou bouger ;
   le fork garantit une supply chain reproductible.
2. **Point d'atterrissage pour un patch Chronicle éventuel.** Si un correctif
   spécifique devient nécessaire, il a déjà un endroit où vivre — même modèle que
   [`mod-ale-chronicle`](https://github.com/NomenAK/mod-ale-chronicle) (qui porte
   un fix httplib).

## Politique

- **Pas de patch local sans ADR Chronicle.**
- **Sync upstream manuel et délibéré** — jamais automatique.
- **En cas de patch futur : le proposer upstream d'abord.**

Voir la fork policy : Chronicle `docs/modules-catalogue.md` (§ *Submodule + fork policy*).
