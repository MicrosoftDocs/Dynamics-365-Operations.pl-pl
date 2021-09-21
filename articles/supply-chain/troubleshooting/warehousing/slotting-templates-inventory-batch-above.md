---
title: Dostępne zapasy nie są uwzględniane dla pozycji powyżej partii
description: W niektórych szablonach rozpisywania nie są uwzględniane bieżące dostępne zapasy dla pozycji powyżej partii. Numer partii lub numer seryjny musi być określony w zamówieniu popytu.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: df5642b32f5e053144230eab3dbcf633f526279a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477308"
---
# <a name="slotting-templates-dont-consider-on-hand-inventory-for-batch-above-items"></a>W szablonach rozpisywania nie są uwzględniane dostępne zapasy dla pozycji powyżej partii

## <a name="symptoms"></a>Objawy

Szablony gniazda, dla których kryterium *Uwzględnianie dostępnych zapasów* nie są uwzględniane bieżące dostępne zapasy dla towarów *partii powyżej*. Są one rozważane tylko wtedy, gdy numer partii jest określony w wierszu zamówienia sprzedaży.

Jednak w przypadku towarów stanu *partii poniżej* aktualny stan dostępnych zapasów jest traktowany zgodnie z oczekiwaniami.

Aby uzyskać więcej informacji, zajrzyj do [Rozpisywanie na przedziały w magazynie](/dynamics365/supply-chain/warehousing/warehouse-slotting).

## <a name="resolution"></a>Rozwiązanie

Nagłówek szablonu schowania można zdefiniować dla strategii *Zamówione*, *Zarezerwowane* lub *Zwolniony popyt*. W strategii *Zamówiono* popytu obowiązują te same wymagania hierarchii rezerwacji, które dotyczą rezerwacji lub zwalniania do procesów magazynowych. Dlatego w przypadku towarów, które mają hierarchie rezerwacji *partia powyżej* i *seria poniżej*, numer partii lub numer seryjny musi być określony w zamówieniu popytu (sprzedaż lub przeniesienie).

Strategii *Zarezerwowanego* popytu można również użyć w celu wybrania numeru partii lub numeru seryjnego przed wygenerowaniem popytu gniazda magazynowego.
