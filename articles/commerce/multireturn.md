---
title: Zwracanie pozycji w ramach wielu zamówień i faktur odbiorców
description: W tym temacie opisano funkcje obsługi zwrotów z wielu zamówień i faktur w rozwiązaniu Dynamics 365 Commerce.
author: josaw1
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4a64794a0e04516441fab628d441640e4d154b8d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796904"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Zwracanie pozycji w ramach wielu zamówień i faktur odbiorców

[!include [banner](includes/banner.md)]


W tym artykule opisano dwie funkcje optymalizujące zwroty zamówień odbiorców na wiele faktur. 

## <a name="enable-refunds-over-multiple-captures"></a>Włącz zwroty dla wielu przechwyceń

Ta funkcja umożliwia łączenie wielu powiązanych refundacji z tym samym zamówieniem odbiorcy. 

1. Przejdź do obszaru roboczego **Zarządzanie funkcjami** i wyszukaj opcję **Włącz zwroty dla wielu przechwyceń**.
2. Wybierz opcję **Włącz refundacje dla wielu zamówień**, a następnie kliknij opcję **Włącz**. 

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a>Włącz poprawne obliczanie podatku dla zwrotów z ilością częściową

Ta funkcja zapewnia, że gdy zamówienie zostanie zwrócone przy użyciu wielu faktur, podatki będą ostatecznie równe kwocie podatku pierwotnie naliczonego. 

1. Przejdź do obszaru roboczego **Zarządzanie funkcjami** i wyszukaj opcję **Włącz poprawne obliczanie podatku dla zwrotów z ilością częściową**.
2. Zaznacz opcję **Włącz poprawną kalkulację podatku dla zwrotów o ilości częściowej**, a następnie kliknij opcję **Włącz**. 


## <a name="process-returns"></a>Przetwarzanie zwrotów

Po włączeniu tych funkcji i zsynchronizowaniu zmian ze sklepami kasjer w sklepie można wybrać wiele zamówień sprzedaży dla danego odbiorcy i dokonać ich zwrotu.

Gdy zamówienia są wybrane, zostanie wyświetlona lista wszystkich produktów podlegających zwrotowi z wszystkich faktur dla tych zamówień. Kasjer może następnie wybrać produkty do zwrotu. Dla wszystkich wybranych produktów zostanie utworzone jedno zamówienie zwrotu.

Jeśli zamówienie jest w pełni zwrócone, kwota podatków zwrócona odbiorcy będzie równa kwocie pierwotnie naliczonego podatku.



[!INCLUDE[footer-include](../includes/footer-banner.md)]