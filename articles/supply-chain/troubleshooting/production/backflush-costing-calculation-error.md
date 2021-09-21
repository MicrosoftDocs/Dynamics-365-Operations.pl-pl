---
title: Błąd obliczania wyceny wstecznej podczas zamykania magazynu
description: We wcześniejszych wersjach wystąpił błąd obliczania wyceny wstecznej podczas zamykania magazynu. Ten problem został rozwiązany.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ae92b7121998d6b1ba2f08ea5736c55637867fbf
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477293"
---
# <a name="backflush-costing-calculation-error-during-inventory-closing"></a>Błąd obliczania wyceny wstecznej podczas zamykania magazynu

## <a name="symptoms"></a>Objawy

W zwolnieniach przed wydaniem 10.0.13, jeśli nie jest używany przepływ kosztów produkcji oszczędnej, podczas zamykania magazynu jest wyświetlany następujący błędny komunikat ostrzegawczy:

> Zamierzasz wykonać zamknięcie zapasów z datą %1. Nie zarejestrowano wykonania obliczania wyceny wstecznej z datą %1 pasującą do zakończenia okresu. Należy pamiętać o wykonaniu obliczania wyceny wstecznej z datą %1 pasującą do zakończenia okresu. Wycena zapasów, koszt własny sprzedaży i odchylenia mogą być niewłaściwe w księdze podrzędnej lub księdze głównej do momentu wykonania tej operacji.

## <a name="resolution"></a>Rozwiązanie

Ten błąd został rozwiązany w wersji wydania 10.0.13 lub nowszej. Aby uzyskać więcej informacji, zobacz [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).
