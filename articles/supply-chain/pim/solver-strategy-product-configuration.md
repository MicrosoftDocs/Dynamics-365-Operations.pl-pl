---
title: Strategia zmiennej na potrzeby konfiguracji produktów
description: W tym temacie opisano, jak za pomocą strategii doboru solverów poprawić działanie konfiguracji produktu.
author: cvocph
manager: tfehr
ms.date: 02/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCCreateProductConfigurationModel, PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cb0fc054e0feec4c54c0bd916e01ce3a2a4cd903
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435454"
---
# <a name="solver-strategy-for-product-configuration"></a>Strategia zmiennej na potrzeby konfiguracji produktów

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak za pomocą strategii doboru solverów poprawić działanie konfiguracji produktu.

Koncepcja strategii doboru solverów została po raz pierwszy wprowadzona w aktualizacji zbiorczej 7 (CU7) programu Microsoft Dynamics AX 2012 R2. Została rozszerzona w aktualizacji zbiorczej 8 (CU8) dla programów Microsoft Dynamics AX 2012 R3 oraz Microsoft Dynamics 365 for Finance and Operations  Enterprise Edition wer. 7.3.

Koncepcja strategii doboru solverów obejmuje obecnie następujące strategie:

- Domyślnie
- Najpierw domeny minimalne
- Od góry do dołu
- Z3

## <a name="solver-strategy"></a>Strategia zmiennej 

Model konfiguracji produktu może być sformułowany jako [problem spełnienia ograniczeń (CSP)](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf). Microsoft Solver Foundation (MSF) zawiera dwa rodzaje strategii doboru solverów przeznaczone do rozwiązywania problemów CSP, które można stosować do modeli konfiguracji produktów. Te strategie doboru solverów opierają się na [algorytmach heurystycznych](https://techterms.com/definition/heuristic), które służą do określania kolejności, w jakiej zmienne problemów CSP są brane pod uwagę podczas rozwiązywania problemów. Algorytmy heurystyczne mogą znacząco wpływać na wydajność podczas rozwiązywania problemu lub klasy problemów.

Strategia doboru solverów dla modeli konfiguracji produktu określa, który solver jest używany w algorytmach heurystycznych. W strategiach **Domyślnie**, **Najpierw domeny minimalne** i **Od góry do dołu** są używane dwa solvery ze środowiska MSF, podczas gdy strategia **Z3** wykorzystuje solver Z3. 

Analizy faktycznych wdrożeń u klientów pokazały, że zmiana strategii doboru solverów dla modelu konfiguracji produktu może skrócić czas reakcji z minut do milisekund. Z tego względu warto poświęcić czas na wypróbowanie różnych strategii zmiennej i znalezienie optymalnej strategii dla używanego modelu konfiguracji produktów.

## <a name="change-the-settings-for-the-solver-strategy"></a>Zmiana ustawień strategii doboru solverów

Aby zmienić strategię doboru solverów, na stronie **Modele konfiguracji produktu** w okienku akcji wybierz opcję **Właściwości modelu**. Następnie w oknie dialogowym **Edytowanie szczegółów modelu** wybierz strategię doboru solverów.

[![Zmiana strategii doboru solverów](./media/solver-strategy.png)](./media/solver-strategy.png)

Obecnie nie istnieje logika potrafiąca automatycznie wykrywać, która strategia doboru solverów będzie najbardziej efektywna dla konfiguracji produktu opartej na ograniczeniach. W związku z tym należy testować strategie doboru solverów jedną po drugiej.

W poniższej tabeli przedstawiono zalecenia dotyczące strategii doboru solverów dla różnych scenariuszy.

| Strategia zmiennej      | Użyj strategii w tym scenariuszu |
|----------------------|-----------------------------------|
| Domyślnie              | Strategia **Domyślnie** została zoptymalizowana do rozwiązywania problemów z modelami, które opierają się na powiązanych tabelach. Analizy wdrożeń u klientów pokazały, że ta strategia jest najbardziej efektywna w scenariuszach, gdzie są szeroko stosowane powiązania tabel. |
| Najpierw domeny minimalne | Strategie **Najpierw domeny minimalne** i **Od góry do dołu** są ściśle powiązane. Analizy wdrożeń u klientów pokazały, że strategia **Od góry do dołu** przynosi lepsze efekty, niż strategia **Najpierw domeny minimalne**. Jednak strategia **Najpierw domeny minimalne** została zachowana w produkcie w celu zapewnienia zgodności z poprzednimi wersjami. Obie te strategie doboru solverów okazują się skuteczniejsze w rozwiązywaniu problemów z modelami zawierającymi kilka wyrażeń arytmetycznych, gdzie nie są używane powiązane tabele. Jednak w niektórych przypadkach lepsze efekty przynosi strategia **Domyślnie**. Z tego względu należy pamiętać o wypróbowaniu każdej strategii. |
| Od góry do dołu             | Strategie **Najpierw domeny minimalne** i **Od góry do dołu** są ściśle powiązane. Analizy wdrożeń u klientów pokazały, że strategia **Od góry do dołu** przynosi lepsze efekty, niż strategia **Najpierw domeny minimalne**. Jednak strategia **Najpierw domeny minimalne** została zachowana w produkcie w celu zapewnienia zgodności z poprzednimi wersjami. Obie te strategie doboru solverów okazują się skuteczniejsze w rozwiązywaniu problemów z modelami zawierającymi kilka wyrażeń arytmetycznych, gdzie nie są używane powiązane tabele. Jednak w niektórych przypadkach lepsze efekty przynosi strategia **Domyślnie**. Z tego względu należy pamiętać o wypróbowaniu każdej strategii. |
| Z3                   | Zalecamy używanie strategii **Z3** jako domyślnej strategii doboru solverów. W przypadku obaw o wydajność i skalowalność można przetestować pozostałe strategie. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie konfiguracji produktu](build-product-configuration-model.md)

[Algorytmy heurystyczne](https://techterms.com/definition/heuristic)

[Problem spełnienia ograniczeń](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]