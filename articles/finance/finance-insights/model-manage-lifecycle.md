---
title: Cykl życia zarządzania modelami (wersja zapoznawcza)
description: W tym temacie opisano sposoby utrzymywania modeli uczenia maszynowego organizacji w celu optymalizacji generowanych przez nie prognoz.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: d5566bde97a2e60d050f4a7b499b554df4848bf9
ms.sourcegitcommit: f6050b444e636ba662c00d0443c94a99f8ea0b0d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309797"
---
# <a name="model-management-lifecycle-preview"></a>Cykl życia zarządzania modelami (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie opisano sposoby utrzymywania modeli uczenia maszynowego organizacji w celu optymalizacji generowanych przez nie prognoz.

Zalecamy przeszkolenie modelu AI w środowisku piaskownicy, a następnie użycie zarządzanych rozwiązań do wdrożenia go w środowisku produkcyjnym. Takie podejście pomaga zapewnić, że istnieją odpowiednie kontrole zarządzania cyklem życia modelu.

Ponieważ model AI opiera się na dostępnych danych faktur i klientów, ważne jest, aby środowisko piaskownicy miało najnowszą kopię danych produkcyjnych. Możesz rozpocząć szkolenie modelu, wykonując kroki opisane w [Korzystanie z prognoz płatności odbiorcy](use-customer-payment-predictions.md). Po przekwalifikowaniu modelu oceny wyników zgodnie z opisem w [Ocenianie modelu początkowych prognoz płatności odbiorcy](evaluate-payment-prediction.md). Użyj informacji w [Usprawnij model przewidywania](improve-model.md) do eksperymentowania z kombinacji funkcji i filtrów, które mogą pomóc poprawić model.

Po spełnieniu wyników szkolenia wykonaj kroki opisane w obszarze [Dystrybucja modelu AI](https://docs.microsoft.com/ai-builder/distribute-model), aby przejść model do środowiska produkcyjnego.
