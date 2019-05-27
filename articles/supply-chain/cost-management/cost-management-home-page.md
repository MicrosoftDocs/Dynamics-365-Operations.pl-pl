---
title: Zarządzanie kosztami — strona główna
description: Moduł Zarządzanie kosztami pozwala wykonywać operacje wyceny i księgowania surowców, półproduktów, wyrobów gotowych oraz zasobów produkcji w toku.
author: AndersGirke
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd94ae4c5ea855139fd1c41060de7db455ffab06
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557656"
---
# <a name="cost-management-home-page"></a>Zarządzanie kosztami — strona główna

[!include [banner](../includes/banner.md)]

Moduł [Zarządzanie kosztami (film)](https://www.youtube.com/watch?v=vXzlC-mOBcg&feature=youtu.be) pozwala wykonywać operacje wyceny i księgowania surowców, półproduktów, wyrobów gotowych oraz zasobów produkcji w toku. Określa proces definiowania, zarządzania i raportowania dla operacji [księgowania zapasów](cost-object.md) i [księgowania produkcji](bom-calculations.md).

Zasady kosztów można zdefiniować w następujących obszarach: 
-  [Wstępnie ustalony koszt](costing-versions.md)
-  [Księgowanie zapasów](cost-object.md)
-  [Księgowanie produkcji](bom-calculations.md)
-  [Księgowanie kosztów pośrednich](costing-sheets.md)
-  [Integracja księgi](production-order-cost-analysis.md)

Na przykład można określić, które metody wyceny zapasów, np. [FIFO](fifo-physical-value-marking.md), [średnia ważona](weighted-average-physical-value-marking.md), [koszt standardowy](prerequisites-standard-costs.md) czy [średnia ruchoma](moving-average.md), mają być stosowane do produktów w [grupie modeli pozycji](../inventory/reserve-inventory-quantities.md) w module Księgowanie zapasów.

Do modułów Księgowanie zapasów i Księgowanie produkcji można przejść z obszarów roboczych **Administrowanie kosztami** i **Analiza kosztów**. Te obszary robocze pokazują kompletny przegląd bieżącego stanu i kluczowe wskaźniki wydajności (KPI) oraz umożliwiają wykrywanie odchyleń. 

Moduł Księgowanie produkcji umożliwia obsługę [kalkulacji doliczeniowej zleceniowej](production-order-cost-analysis.md) w zleceniach produkcyjnych i szarżach produkcyjnych oraz [wyceny wstecznej](backflush-costing.md) w produkcji oszczędnej.

[Pakiet zawartości Zarządzanie kosztami usługi Power BI](../../dev-itpro/analytics/cost-management-content-pack.md) zapewnia zaawansowany wgląd w zapasy i zapasy pracy w toku (PWT) oraz przepływy kosztów między tymi zapasami z podziałem na kategorie w ujęciu czasowym. Informacje mogą być również wykorzystywane jako szczegółowe uzupełnienie sprawozdania finansowego.

### <a name="additional-resources"></a>Dodatkowe zasoby

#### <a name="whats-new-and-in-development"></a>Nowe i opracowywane funkcje

Przejdź na stronę [Plan rozwoju usługi Microsoft Dynamics 365](https://roadmap.dynamics.com/), aby zobaczyć, jakie nowe funkcje zostały wydane, a jakie są jeszcze opracowywane. 

#### <a name="white-paper"></a>Oficjalny dokument
W artykule [Obliczenia BOM za pomocą arkusza wyceny](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/white-papers/365operationsbomcalsheet) opisano, jak skonfigurować arkusz wyceny obejmujący materiały i wytwarzanie oraz jak ta konfiguracja wpływa na wyniki obliczania BOM. Aby lepiej wyjaśnić zagadnienia, zawiera konkretne scenariusze i dane, które ilustrują efekt działania różnych ustawień i konfiguracji. Nie oczekujemy ścisłego prześledzenia tych scenariuszy, ponieważ dokument zawiera za mało szczegółów, aby można było je skonfigurować. Niemniej jednak jeśli masz podstawową wiedzę, możesz spróbować odtworzyć wymienione niżej przewodniki po zadaniach w kolejności, w jakiej są podane. Wiedzę uzyskaną po przeczytaniu tego dokumentu można wykorzystać do analizy obliczeń BOM. 

-  [Tworzenie wyrobu gotowego](tasks/create-finished-product-2016-02.md)
-  [Tworzenie półproduktu](tasks/create-semi-finished-product-2016-02.md)
-  [Tworzenie surowców](tasks/create-raw-materials-2016-02.md)
-  [Tworzenie list składowych](tasks/create-boms-2016-02.md)
-  [Tworzenie tras](tasks/create-routes-2016-02.md)
-  [Obliczanie BOM przy użyciu struktury jednopoziomowej](tasks/calculate-bom-single-level-structure-2016-02.md)
-  [Obliczanie BOM przy użyciu struktury wielopoziomowej](tasks/calculate-bom-multilevel-structure-2016-02.md)


#### <a name="blogs"></a>Blogi
Opinie, wiadomości i inne informacje na temat modułu Zarządzanie kosztami można znaleźć w [blogu zespołu ds. badań i rozwoju modułu Wytwarzanie systemu Dynamics AX](https://blogs.msdn.microsoft.com/axmfg) oraz [blogu zespołu ds. badań i rozwoju modułu Zarządzanie łańcuchem dostaw systemu Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm). Mimo że część z tych wpisów została napisana dla poprzedniej wersji modułu Zarządzanie kosztami, to w obecnej wersji są również używane te same pojęcia i podobne procedury.

#### <a name="task-guides"></a>Przewodniki zadań
Dodatkowa pomoc jest dostępna w formie przewodników po zadaniach wewnątrz rozwiązania Finance and Operations. Aby uzyskać dostęp do przewodników po zadaniach, kliknij przycisk Pomoc na dowolnej stronie.

