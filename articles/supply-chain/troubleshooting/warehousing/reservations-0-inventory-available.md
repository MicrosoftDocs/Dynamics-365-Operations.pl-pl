---
title: Nie można dokonać rezerwacji, ponieważ jest dostępnych 0,00
description: Wyświetlany jest błąd mówiący, że system nie może dokonać rezerwacji, ponieważ w magazynie jest dostępnych tylko 0,00. Ten problem jest prawdopodobnie spowodowany otwarta pracą.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 75d72f7ee1bdecca5a087b75b1de9907b9d244ab
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477339"
---
# <a name="system-cant-make-reservations-because-000-are-available-in-the-inventory"></a>System nie może dokonać rezerwacji, ponieważ w magazynie jest dostępnych 0,00

## <a name="symptoms"></a>Objawy

Ten problem może wystąpić, jeśli system nie może zaktualizować ilości zapasów, ponieważ nie ma wystarczającej liczby transakcji magazynowych o określonych wymiarach. Zostanie wyświetlony następujący komunikat o błędzie:

> Fizycznie dostępne w oddziale=%1, Magazyn=%2, Stan zapasów=dostępne, Numer partii=%3, Właściciel=%4: %5 nie może zostać zarezerwowane, ponieważ w magazynie jest dostępnych tylko 0,00.

## <a name="resolution"></a>Rozwiązanie

Ten problem jest prawdopodobnie spowodowany otwarta pracą. Ukończ pracę lub odbierz bez tworzenia pracy. Upewnij się, że żadne transakcje magazynowe nie rezerwują ilości fizycznie. Na przykład tymi transakcjami mogą być otwarte zlecenia kontroli jakości, rekordy blokowania zapasów lub zamówienia wyjścia.
