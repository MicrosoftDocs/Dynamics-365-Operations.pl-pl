---
title: Odbieranie mieszanego numeru identyfikacyjnego nie działa dla wszystkich kodów dyspozycji
description: Jeśli pole Akcja dla kodu dyspozycji ma wartość Kredyt lub Odpadki, do przetwarzania zwróconych towarów można używać tylko elementu menu Odbieranie mieszanych numerów identyfikacyjnych.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b762255bc5ef6a1e15688a9c635940e92e67db3c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477333"
---
# <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-but-credit"></a>Odbieranie mieszanego numeru identyfikacyjnego nie działa dla kodu dyspozycji z wyjątkiem kredytu

## <a name="symptoms"></a>Objawy

Jeśli pole **Akcja** dla kodu dyspozycji ma wartość *Kredyt* lub *Odpadki*, do przetwarzania zwróconych towarów można używać tylko elementu menu [Odbieranie mieszanych numerów identyfikacyjnych](/dynamics365/supply-chain/warehousing/mixed-license-plate-receiving).

## <a name="resolution"></a>Rozwiązanie

Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji. Obecnie tylko [kody dyspozycji](/dynamics365/supply-chain/service-management/set-up-disposition-codes), w których pole **Akcja** ma wartość *Kredyt* lub *Odpadki*, są obsługiwane w przypadku otrzymywania mieszanego numeru identyfikacyjnego.
