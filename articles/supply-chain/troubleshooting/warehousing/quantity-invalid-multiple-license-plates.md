---
title: Ilość jest nieprawidłowa dla pracy pobrania z wieloma numerami identyfikacyjnymi
description: Jeśli w jednej lokalizacji istnieje praca pobrania z wieloma numerami identyfikacyjnymi, ilość nie jest prawidłowa dla sztuki jednostki. Sprawdź, czy następujące pola są poprawne.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5b245f71e80339fee3e42cfffa0396078a56926e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477267"
---
# <a name="quantity-not-valid-when-theres-picking-work-with-multiple-lps-in-one-location"></a>Ilość jest nieprawidłowa, jeśli w jednej lokalizacji jest praca pobierania z wieloma numerami identyfikacyjnymi

## <a name="symptoms"></a>Objawy

Jeśli w jednej lokalizacji istnieje praca pobrania z wieloma numerami identyfikacyjnymi, ilość nie jest prawidłowa dla jednostki *sztuka* i pojawia się następujący komunikat o błędzie:

> Ilość jest nieprawidłowa dla jednostki 1%.

## <a name="resolution"></a>Rozwiązanie

Sprawdź, czy pola **Identyfikator grupy sekwencji jednostek** i **Konwersje jednostek** dla zwolnionego produktu lub wariantu produktu są poprawnie ustawione.

Należy zauważyć, że komunikat o błędzie został ulepszony w wersji 10.0.15, aby pokazać rozszerzoną ilość (zobacz [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)). Nowy komunikat o błędzie:

> Ilość jest nieprawidłowa. Oczekiwano %1 %2.
