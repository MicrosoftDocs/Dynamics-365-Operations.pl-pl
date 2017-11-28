---
title: "Śledzenie dynamicznych średnich kosztów własnych dla wymiaru magazynowego"
description: "Każda pozycja magazynowa ma przypisaną grupę wymiarów magazynowych. Dlatego dynamiczny średni koszt własny dla towaru jest obliczany na podstawie wyboru wymiarów magazynowych, które są śledzone pod względem finansowym."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bb2a3a193585944810c5dfac1eb3c019e074008f
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="tracking-running-average-cost-per-inventory-dimension"></a>Śledzenie dynamicznych średnich kosztów własnych dla wymiaru magazynowego

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Każda pozycja magazynowa ma przypisaną grupę wymiarów magazynowych. Dlatego dynamiczny średni koszt własny dla towaru jest obliczany na podstawie wyboru wymiarów magazynowych, które są śledzone pod względem finansowym.

Istnieją trzy typy wymiarów magazynowych: produkt, magazyn i śledzenie. Wymiary produktów obejmują konfigurację, rozmiar i kolor. Wymiary produktów są zawsze śledzone pod względem finansowym. Wymiary magazynowania i śledzenia obejmują oddział, magazyn, lokalizację, stan zapasów, numer identyfikacyjny, numer partii i numer seryjny. Można określić, które wymiary magazynowania i śledzenia są śledzone pod względem finansowym. 

**Przykład 1** 

Jeśli grupa wymiarów magazynowania przypisana do towaru jest śledzona pod względem finansowym według magazynów, dynamiczne średnie koszty własne będą obliczane dla każdego magazynu. Zafakturowano następujące zamówienia zakupu:

-   Zamówienie zakupu dotyczące ilości równej 2 i kosztu własnego równego 10,00 zł zostało zafakturowane dla magazynu GW.
-   Zamówienie zakupu dotyczące ilości równej 3 i kosztu własnego równego 12,00 zł zostało zafakturowane dla magazynu GW.
-   Zamówienie zakupu dotyczące ilości równej 5 i kosztu własnego równego 15,00 zł zostało zafakturowane dla magazynu MW.

Dynamiczny średni koszt własny dla magazynu GW wynosi 11,20 zł., a dynamiczny średni koszt własny dla magazynu MW wynosi 15,00 zł. Dla magazynu GW zaksięgowano fakturę zamówienia sprzedaży. Wartość zapasów i koszt własny sprzedaży (przed uruchomieniem zamknięcia magazynu i bez zaznaczania) to 11,20 zł. Dla magazynu MW zaksięgowano inne zamówienia sprzedaży. Wartość zapasów i koszt własny sprzedaży (przed uruchomieniem zamknięcia magazynu i bez zaznaczania) to 15,00 zł. 

**Przykład 2** Jeśli grupa wymiarów magazynowania, która jest przypisana do towaru, jest śledzona pod względem według magazynu, a grupa wymiarów śledzenia jest śledzona pod względem finansowym wg numeru partii, dynamiczny średni koszt własny jest obliczany dla każdej partii. 

**Uwaga:** Zaleca się, aby koszt własny zawsze wyświetlać razem ze wszystkimi śledzonymi wymiarami finansowymi. Zafakturowano następujące zamówienia zakupu:

-   Zamówienie zakupu dotyczące ilości równej 2 i kosztu własnego równego 10,00 zł zostało zafakturowane dla magazynu GW i partii AAA.
-   Zamówienie zakupu dotyczące ilości równej 3 i kosztu własnego równego 12,00 zł zostało zafakturowane dla magazynu GW i partii AAA.
-   Zamówienie zakupu dotyczące ilości równej 2 i kosztu własnego równego 15,00 zł zostało zafakturowane dla magazynu GW i partii BBB.

Dynamiczny średni koszt własny dla magazynu GW i partii AAA wynosi 11,20 zł., a dynamiczny średni koszt własny dla magazynu GW i partii BBB wynosi 15,00 zł.




