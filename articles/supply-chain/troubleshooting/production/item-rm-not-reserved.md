---
title: Nie można zarezerwować RM towaru podczas zwalniania zlecenia produkcyjnego
description: 'Podczas zwalniania zlecenia produkcyjnego może wystąpić błąd: „Nie można w pełni zarezerwować RM towaru”. Upewnij się, że pełna ilość jest dostępna lub rezerwuj pozycje ręcznie.'
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 528895252d661bb012f49190c15853989833064d
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477335"
---
# <a name="item-rm-cant-be-fully-reserved-when-a-production-order-is-released"></a>Nie można w pełni zarezerwować RM towaru podczas zwalniania zlecenia produkcyjnego

## <a name="symptoms"></a>Objawy

Jeśli nie wszystkie pozycje wierszy BOM są fizycznie dostępne, gdy zlecenie produkcyjne jest zwalniane do magazynu, a zasady **Zwolnij do magazynu** są ustawione na *Wymagaj pełnej rezerwacji*, pojawi się następujący komunikat o błędzie:

> Nie można w pełni zarezerwować elementu RM pozycji. Upewnij się, że dostępna jest pełna ilość, lub zarezerwuj towary ręcznie, jeśli pole Rezerwacja w wierszu BOM jest ustawione na Ręcznie lub Rozpoczęto. Nie można zwolnić zamówienia do magazynu, ponieważ nie zarezerwowano pewnych materiałów.

## <a name="resolution"></a>Rozwiązanie

Zachowanie to zgodnie z projektem i działa zgodnie z oczekiwaniami. Rozwiąż ten problem, postępując zgodnie z wytycznymi wyświetlonymi w komunikacie o błędzie: „Upewnij się, że pełna ilość jest dostępna, lub zarezerwuj pozycje ręcznie, jeśli pole Rezerwacja w wierszu BOM jest ustawione jako Ręcznie lub Rozpoczęto”.
