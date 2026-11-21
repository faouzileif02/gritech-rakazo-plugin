---
name: gritech-trading-guardrails
description: Garde-fous obligatoires avant tout ordre de trading (XAUUSD, Capital.com via n8n). À utiliser dès qu'un bot veut passer, modifier ou annuler un ordre, ou valider un signal BUY/SELL.
---

Avant d'envoyer un ordre, vérifie chaque point. Si un point échoue, n'envoie pas l'ordre et explique pourquoi.

1. **Compte** : l'ordre vise le compte démo, sauf si l'utilisateur a écrit explicitement que le réel est autorisé.
2. **Risque** : la perte maximale du trade ne dépasse pas 5 € (stop-loss obligatoire, taille calculée depuis la distance au stop).
3. **Signal** : la décision finale vient du chef après l'avis analyse, risque et actualités. Un seul bot ne décide jamais seul.
4. **Doublons** : pas de nouvel ordre dans le même sens si une position ouverte existe déjà sur l'instrument.
5. **Trace** : écris dans le journal : date, instrument, sens, taille, entrée, stop, objectif, raison en deux phrases.
6. **Confirmation** : après l'envoi, vérifie la réponse du pont n8n. Si elle est absente ou en erreur, signale-le et ne renvoie pas l'ordre sans accord.

Ne promets jamais un gain. Présente les résultats avec les pertes comme les gains.
