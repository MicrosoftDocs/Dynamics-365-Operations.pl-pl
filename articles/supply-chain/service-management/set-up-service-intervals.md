---
title: Konfigurowanie ram czasowych serwisu
description: Interwał serwisu określa częstotliwość, z jaką są tworzone wiersze umowy serwisowej podczas tworzenia zleceń serwisowych.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementinterval
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 54eba378548e1bef8ae9c3f4e7b202cf06aeff2d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434898"
---
# <a name="set-up-service-intervals"></a>Konfigurowanie ram czasowych serwisu  

[!include [banner](../includes/banner.md)]

Interwał serwisu określa częstotliwość, z jaką są tworzone wiersze umowy serwisowej podczas tworzenia zleceń serwisowych.

1. Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Umowy serwisowe** \> **Ramy czasowe serwisów**.
2. Utwórz nowe ramy czasowe serwisu.
3. Wprowadź identyfikator i opis ram czasowych serwisu.
4. W polu **Zakres** wybierz zakres.
5. W polu **Częstotliwość** wpisz częstotliwość. Częstotliwość to współczynnik, przez który należy pomnożyć zakres w celu uzyskania ram czasowych umowy serwisowej.
6. Naciśnij klawisze **Alt+S**, aby zapisać ramy czasowe serwisu.

## <a name="example"></a>Przykład

Chcesz utworzyć ramy czasowe serwisu o długości 10 dni.

**Tworzenie 10-dniowych ram czasowych serwisu**

1. Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Umowy serwisowe** \> **Ramy czasowe serwisów**.
2. Utwórz nowe ramy czasowe serwisu.
3. Wprowadź identyfikator i opis ram czasowych serwisu.
4. W polu **Zakres** wybierz opcję **Codziennie**.
5. W polu **Częstotliwość** wpisz 10.
6. Naciśnij klawisze **Alt+S**, aby zapisać ramy czasowe serwisu.

## <a name="related-topics"></a>Powiązane tematy

[Ramy czasowe serwisów ](service-intervals.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]