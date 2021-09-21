---
title: Praca pobrania zablokowana z powodu niezakończonej pracy uzupełniania zapasów
description: Praca pobrania może być zablokowana z powodu zależnej pracy uzupełniania zapasów. Zakończ pracę uzupełniania zapasów, a następnie przetwórz pracę pobrania.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 53b50d1e3e2d7bb64e78514affe80076ddcb9052
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477354"
---
# <a name="picking-work-cant-be-unblocked-because-of-unfinished-replenishment-work"></a>Nie można odblokować pracy pobrania z powodu niezakończonej pracy uzupełniania zapasów

## <a name="symptoms"></a>Objawy

Podczas korzystania z uzupełniania zapasów dla grupy czynności można zablokować pracę pobrania z powodu zależnej pracy uzupełniania zapasów. Jeśli lokalizacja pobrania musi być uzupełniana w celu zrealizowania zapotrzebowania zamówienia źródłowego, system tworzy zarówno pracę uzupełniającą, jak i pracę pobrania. Praca pobrania jest jednak blokowana, dopóki nie zostanie zakończona praca uzupełniania zapasów i zostanie wyświetlony następujący komunikat o błędzie:

> Nie można odblokować pracy %1, ponieważ zawiera nieukończoną pracę uzupełnienia zapasów.

## <a name="resolution"></a>Rozwiązanie

To zachowanie jest celowe, ponieważ lokalizacja pobrania nie ma wystarczającej ilości zapasów, dopóki praca uzupełniania zapasów nie zostanie zakończona. Zakończ pracę uzupełniania zapasów, a następnie przetwórz pracę pobrania.
