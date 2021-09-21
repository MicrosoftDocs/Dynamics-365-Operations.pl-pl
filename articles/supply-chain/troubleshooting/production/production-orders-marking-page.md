---
title: Zlecenia produkcyjne niewyświetlane na stronie Zaznaczanie
description: Niektóre zlecenia produkcyjne nie są wyświetlane na stronie Zaznaczanie. W tym temacie wyjaśniono trzy konfiguracje produktów, których nie można zaznaczać.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 87507e91d3feb2557e7ba771b8e34ff7ca105749
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477254"
---
# <a name="production-orders-arent-shown-on-the-marking-page"></a>Zlecenia produkcyjne nie są wyświetlane na stronie Zaznaczanie

## <a name="symptoms"></a>Objawy

Podczas pracy z produkcją dyskretną niektóre zlecenia produkcyjne nie są wyświetlane na stronie **Zaznaczanie**.

## <a name="resolution"></a>Rozwiązanie

Produkty, które mają poniższe konfiguracje, nie są dostępne do oznaczenia. Z tego powodu nie będą one widoczne na stronie **Zaznaczanie**:

- Produkty definiuje się jako produkty o typie *ilości efektywnej*.
- Są one włączone dla zaawansowanych procesów magazynowych.
- Są one skonfigurowane do sterowania przez zasadę *Koszt standardow*.
