---
title: Nie można odnaleźć profilu grupy
description: Podczas pracy z przychodzącymi magazynami może być wyświetlany błąd oznaczający, że nie można odnaleźć profilu grupy. Upewnij się, że profile grup są poprawnie skonfigurowane.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bbf9c5bc70c8f3ba1fa26db425249e65e82c0518
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477352"
---
# <a name="cluster-profile-cant-be-found"></a>Nie można odnaleźć profilu grupy

## <a name="symptoms"></a>Objawy

Podczas pracy z przychodzącymi operacjami magazynowymi może zostać wyświetlony następujący komunikat o błędzie:

> „Zlecenie kontroli jakości %1 zostało wygenerowane. Nie można odnaleźć profilu grupy. Sprawdź swoją konfigurację”.

Ten komunikat o błędzie jest związany z procesem odbierania, w którym jest włączona funkcja zarządzania jakością (QMS). W zależności od konfiguracji w danym środowisku dodatkowe szczegóły dotyczące transakcji, która generuje komunikat o błędzie, mogą pomóc w rozwiązaniu problemu.

## <a name="resolution"></a>Rozwiązanie

Najpierw przejrzyj ustawienia pobierania dla grupy i upewnij się, że profile grup są skonfigurowane poprawnie. Nie można skorzystać z elementu menu urządzenia przenośnego do pobierania grup, dopóki nie zostaną skonfigurowane Profile grup. W zależności od środowiska konieczne może być również przejrzenie innych pokrewnych konfiguracji.
