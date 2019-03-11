---
title: Pakiet zawartości Wartości rzeczywiste a budżet dostępny dla usługi Power BI
description: W tym temacie opisano pakiet zawartość Wartości rzeczywiste a budżet dostępny dla usługi Power BI. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.
author: ryansandness
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: c801544e9e37a528203f5a1730aa8cb526d63dbf
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "343496"
---
# <a name="actual-vs-budget-power-bi-content"></a>Pakiet zawartości Wartości rzeczywiste a budżet dostępny dla usługi Power BI

[!include [banner](../includes/banner.md)]

W tym temacie opisano pakiet zawartość **Wartości rzeczywiste a budżet** dostępny dla usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="overview"></a>Przegląd

Pakiet zawartości usługi Power BI **Wartości rzeczywiste** a budżet jest przeznaczony dla osób odpowiedzialnych za monitorowanie wartości rzeczywistych w porównaniu z zabudżetowanymi w swoich organizacjach. Pakiet zawartość usługi Power BI **Wartości rzeczywiste a budżet** zapewnia wgląd w odchylenia budżetu. Można analizować budżet dla bieżącego roku według kategorii kont, kodów budżetu, kont głównych, opisów konta głównego lub okresów obrachunkowych, aby lepiej zrozumieć przyczyny wszelkich odchyleń .

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI
Raporty z pakietów zawartości usługi Power BI **Wartości rzeczywiste a budżet** są wyświetlane w obszarach roboczych **Budżet księgi i prognozy** i **Dyrektor finansowy**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Raporty dostępne w pakiecie zawartości dla usługi Power BI
W poniższej tabeli przedstawiono szczegóły dotyczące mierników, które znajdują się na każdej stronie raportu w pakiecie zawartości dla usługi Power BI **Wartości rzeczywiste a budżet**.

| Raport                      | Metryki                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| Wydatki — wartości rzeczywiste a budżet | <ul><li>Łączne wydatki w roku</li><li>Łączne zabudżetowane wydatki w roku</li></ul>  |
| Przychody — wartości rzeczywiste a budżet  | <ul><li>Łączne przychody w roku</li><li>Łączne zabudżetowane przychody w roku</li><ul>     |
| Wydatki                     | <ul><li>Łączne wydatki w roku</li><li>Cel wydatków założony w budżecie</li><ul> |
| Przychód                     | <ul><li>Łączne przychody w roku</li><li>Cel przychodów założony w budżecie</li><ul>   |
| Dochód netto                  | <ul><li>Dochód netto w roku</li><li>Cel dochodu netto założony w budżecie</li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek

| Jednostka                    | Zawartość                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| Działania na księdze głównej | Kwoty transakcji w księdze głównej                                       |
| Działania na budżecie         | Kwoty transakcji w rejestrze budżetu                                      |
| Konta główne             | Konta główne, według których będą filtrowane raporty                                               |
| Kalendarze obrachunkowe          | Kalendarze obrachunkowe, według których będą filtrowane raporty                                            |
| Księgi                   | Księgi, które można wyfiltrować jako bieżące księgi dla raportu              |
| Kody budżetu              | Kody budżetu, według których będą filtrowane raporty                                                |
| Firmy            | Firmy, które można wyfiltrować jako bieżące firmy dla raportu |
