---
title: Zwracanie pozycji w ramach wielu zamówień i faktur odbiorców
description: W tym temacie opisano funkcje obsługi zwrotów z wielu zamówień i faktur w rozwiązaniu Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: 4d1be6606793d498d01be91de6205e3a45c6dfdf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251266"
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