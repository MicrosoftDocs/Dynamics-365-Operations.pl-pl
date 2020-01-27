---
title: Ograniczanie metod płatności dla zwrotów bez paragonu
description: W tym temacie opisano, jak niektóre typy płatności można ograniczyć pod katem zwrotu, jeśli zwroty są dokonywane bez paragonu.
author: rapraj
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: 22e675fd9b7ee33c89f52ac4c8c15807580b86a7
ms.sourcegitcommit: b806f0c94d703bec39680fead827733361d47045
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/07/2020
ms.locfileid: "2935859"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Ograniczanie metod płatności dla zwrotów bez paragonu


[!include [banner](includes/banner.md)]

Każdy typ płatności akceptowany przez sprzedawcę detalicznego musi zostać skonfigurowany na etapie konfiguracji systemu. W tym temacie opisano, jak niektóre typy płatności można ograniczyć pod katem zwrotu, jeśli zwroty są dokonywane bez paragonu.

## <a name="set-up-payment-methods"></a>Konfigurowanie metod płatności

Aby skonfigurować metody płatności, należy wykonać następujące zadania.
1. Utwórz formy płatności akceptowane w całej organizacji.
2. Utwórz typy i numery kart na poziomie organizacji. Jeśli będą przyjmowane karty kredytowe lub debetowe, trzeba utworzyć jeden typ metody płatności kartami, a następnie utworzyć typy i numery kart na poziomie organizacji.
3. Konfigurowanie metod płatności sklepu. Skojarz typy metod płatności z poszczególnymi sklepami, a następnie wprowadź dla każdego typu metody płatności ustawienia właściwe dla sklepu.
4. Skonfiguruj metody płatności kartą dla sklepów. Skonfiguruj karty dla każdej formy płatności akceptowanej w sklepie.

![Ustawienia sklepu detalicznego](media/NoReceiptReturns1.png "Ustawienia sklepu detalicznego") 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Ograniczanie metod płatności dla zwrotów bez paragonu

Dla każdej metody płatności na stronie **Zarządzanie sklepu detalicznym** w obszarze **Zwroty bez paragonu** wybierz dla ustawienia **Ogranicz dla zwrotów bez paragonu** wartość **Tak**. 

Domyślną wartością tego ustawienia jest **Nie**, co zapewnia, że metoda płatności jest dozwolona dla zwrotów. 

Po wybraniu dla ustawienia **Ogranicz zwroty bez paragonu** wartości **Tak**, dla wybranej metody płatności nie będą możliwe zwroty. 

![Metoda płatności sklepu detalicznego](media/NoReceiptReturns3.png "Metoda płatności sklepu detalicznego") 

> [!NOTE]
> Kiedy kasjer wybiera metodę płatności, dla której obowiązuje ograniczenie zwrotów bez paragonu, pojawia się komunikat przypominający o sprawdzeniu dopuszczalnych metod płatności.

![Dopuszczalne metody płatności](media/NoReceiptReturns4.png "Dopuszczalne metody płatności") 

Jeśli dla transakcji istnieją zarówno zwrot z dokumentem przyjęcia, jak i zwrot bez paragonu, warunek ograniczenia nie zostanie zastosowany, ponieważ transakcja będzie przepływem pracy zwrotu z dokumentem przyjęcia. 

