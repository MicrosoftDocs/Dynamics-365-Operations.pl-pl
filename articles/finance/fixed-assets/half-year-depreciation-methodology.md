---
title: Metodologia amortyzacji półrocznej
description: W tym temacie opisano metodę, dzięki której środki trwałe wykorzystywane do obliczania amortyzacji przy użyciu półrocznej konwencji, która oblicza sześć miesięcy amortyzacji w pierwszym i ostatnim roku eksploatacji środka trwałego.
author: moaamer
manager: Ann Beebe
ms.date: 08/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-17
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 55fb03cf08d8ec042aa8fb37fd1fb858d98279b1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446660"
---
# <a name="half-year-depreciation-convention-methodology"></a>Metodologia amortyzacji półrocznej

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie opisano metodę używaną w podczas obliczania amortyzacji środków trwałych przy użyciu konwencji półrocznej. Konwencja półroczna oblicza sześć miesięcy amortyzacji podczas pierwszego i ostatniego roku pracy środka trwałego. Aby uzyskać więcej informacji na temat konwencji amortyzacji, zobacz [Metody i konwencje amortyzacji środka trwałego](Fixed-asset-depreciation-conventions.md). 

W przypadku korzystania z półrocznej konwencji amortyzacji, system korzysta z roku nabycia lub roku, w którym środek trwały wszedł do użycia, oblicza pięć lat amortyzacji od tego momentu, a następnie dodaje sześć miesięcy. Aby zilustrować ten proces, weźmy przykładowy składnik aktywów nabyty za cenę 50 000 i wprowadźmy go do użycia w kwietniu 2020 roku. Załóżmy również, że środek trwały ma pięcioletni okres użytkowania.

Pierwszy rok służby minie w grudniu 2020 roku, co oznacza, że koniec pięcioletniego okresu użytkowania aktywa minie w grudniu 2024 roku. Półroczna konwencja amortyzacji doda sześć miesięcy do okresu użytkowania składnika aktywów, co oznacza, że jego okres użytkowania zakończy się w czerwcu 2025 roku. 

> Amortyzacja roczna 50 000/5 = 10 000 miesięczna amortyzacja 10 000/12 = 833,33 <br>
> Amortyzacja w pierwszym roku 10 000/2 = 5000 i późniejsza Amortyzacja miesięczna 5000/9 = 555,56

   [![Plan amortyzacji dla konwencji amortyzacji półrocznej](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)

Rozszerzone okresy amortyzacji dodane przez konwencję półroczną zapewniają bardziej precyzyjną alokację amortyzacji. Konwencja półroczna reprezentuje wydatki na amortyzację w bardziej równomierny sposób, co jest przydatne przy raportowaniu zestawienia zysków i strat.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]