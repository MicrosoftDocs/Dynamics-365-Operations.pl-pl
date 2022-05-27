---
title: Cykl życia zarządzania modelami
description: W tym temacie opisano sposoby utrzymywania modeli uczenia maszynowego organizacji w celu optymalizacji generowanych przez nie prognoz.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: a7b57bc0322e0f9a78dddfb924e379ac05ffca32
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/06/2022
ms.locfileid: "8722102"
---
# <a name="model-management-lifecycle"></a>Cykl życia zarządzania modelami

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposoby utrzymywania modeli uczenia maszynowego organizacji w celu optymalizacji generowanych przez nie prognoz.

Zalecamy przeszkolenie modelu AI w środowisku piaskownicy, a następnie użycie zarządzanych rozwiązań do wdrożenia go w środowisku produkcyjnym. Takie podejście pomaga zapewnić, że istnieją odpowiednie kontrole zarządzania cyklem życia modelu.

Ponieważ model AI opiera się na dostępnych danych faktur i klientów, ważne jest, aby środowisko piaskownicy miało najnowszą kopię danych produkcyjnych. Możesz rozpocząć szkolenie modelu, wykonując kroki opisane w [Korzystanie z prognoz płatności odbiorcy](use-customer-payment-predictions.md). Po przekwalifikowaniu modelu oceny wyników zgodnie z opisem w [Ocenianie modelu początkowych prognoz płatności odbiorcy](evaluate-payment-prediction.md). Użyj informacji w [Usprawnij model przewidywania](improve-model.md) do eksperymentowania z kombinacji funkcji i filtrów, które mogą pomóc poprawić model.

Po spełnieniu wyników szkolenia wykonaj kroki opisane w obszarze [Dystrybucja modelu AI](/ai-builder/distribute-model), aby przejść model do środowiska produkcyjnego.
