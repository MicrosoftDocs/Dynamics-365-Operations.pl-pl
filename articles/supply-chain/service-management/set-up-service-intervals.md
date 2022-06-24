---
title: Konfigurowanie interwałów serwisu
description: W tym artykule opisano sposób konfigurowania interwałów serwisowych. Interwał serwisu określa częstotliwość, z jaką są tworzone wiersze umowy serwisowej podczas tworzenia zleceń serwisowych.
author: sorenva
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementinterval
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56b8a31af061b90aeddfb460f6e86c2c5636b280
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845961"
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

## <a name="related-articles"></a>Powiązane artykuły

[Ramy czasowe serwisów ](service-intervals.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]