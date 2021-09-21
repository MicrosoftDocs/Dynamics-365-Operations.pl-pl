---
title: Nie można przetworzyć korekty dokumentu dostawy
description: W przypadku próby skorygowania dokumentu dostawy po zaksięgowaniu zostanie wyświetlony błąd. Na tej stronie opisano sposób korygowania zaksięgowanych dokumentów dostawy dla pozycji, dla których włączono obsługę aplikacji WMS.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bb0d827adff8abd8762bf2de844cad5574628e4b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477334"
---
# <a name="delivery-note-correction-cant-be-processed"></a>Nie można przetworzyć korekty dokumentu dostawy

## <a name="symptoms"></a>Objawy

Po zaksięgowaniu dokumentu dostawy nie można go anulować, ponieważ przycisk **Anuluj** jest niedostępny. Nie można również poprawić dokumentu dostawy. Jeśli spróbujesz to zrobić, zostanie wyświetlony następujący komunikat o błędzie:

> Nie można przetworzyć korekty dokumentu dostawy. Dokument dostawy zawiera tylko pozycje, które podlegają procesom zarządzania magazynem, ponieważ nie są one obsługiwane przez korektę dokumentu dostawy.

## <a name="resolution"></a>Rozwiązanie

Aby skorygować zaksięgowane dokumenty dostawy dla towarów, dla których włączono funkcję zaawansowanego zarządzania magazynem (WMS), należy wykonać księgowanie z ładunku, a nie bezpośrednio w zamówieniu.
