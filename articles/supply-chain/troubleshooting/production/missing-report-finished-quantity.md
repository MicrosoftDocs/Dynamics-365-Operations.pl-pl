---
title: Aktualizacja zgłoszenia jako gotowego nie powiedzie się z błędem brakującej ilości
description: Jeśli próbujesz zakończyć zlecenie produkcyjne podczas zgłaszania ilość błędów, ale nie podczas zgłaszania czasu lub ilości materiału, aktualizacja zgłoszenia jako gotowego zakończy się błędem.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7785549c47063727f2749749940c1a96a351e70f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477279"
---
# <a name="report-as-finished-update-fails-with-a-missing-quantity-error"></a>Aktualizacja zgłoszenia jako gotowego nie powiedzie się z błędem brakującej ilości

## <a name="symptoms"></a>Objawy

Próbujesz zgłosić zlecenie produkcyjne jako zakończone podczas zgłaszania ilość błędów, ale nie podczas zgłaszania czasu lub ilości materiału. Aktualizacja zgłoszenia jako gotowego zakończy się niepowodzeniem podczas próby zakończenia zlecenia produkcyjnego i pojawi się następujący komunikat o błędzie:

> Brak raportu zakończonych ilości.

## <a name="resolution"></a>Rozwiązanie

Jeśli zgłaszasz błędną ilość w zleceniu produkcyjnym, musisz zgłosisz również prawidłową ilość.
