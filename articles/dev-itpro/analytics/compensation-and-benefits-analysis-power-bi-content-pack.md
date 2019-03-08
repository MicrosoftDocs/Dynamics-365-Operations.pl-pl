---
title: Pakiet zawartości Wynagrodzenia i świadczenia dostępny w usłudze Power BI
description: W tym temacie opisano pakiet zawartości Finance and Operations — Wynagrodzenia i świadczenia dla usługi Power BI.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 263914
ms.assetid: 18634bb5-3341-42f2-9cc9-7b04708b506b
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6834940b16749461066e8f1000cbb7c2d4371109
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "327442"
---
# <a name="compensation-and-benefits-power-bi-content"></a>Pakiet zawartości Wynagrodzenia i świadczenia dostępny w usłudze Power BI

[!include [banner](../includes/banner.md)]

W tym temacie opisano pakiet zawartości Finance and Operations — Wynagrodzenia i świadczenia dla usługi Power BI. 

## <a name="reports-that-are-included-in-the-content-pack"></a>Raporty dostępne w pakiecie zawartości
Gdy utworzysz połączenie między pakietem zawartości a danymi programu Finance and Operations, w raportach są wyświetlone dane organizacji. Jeśli to Twoja pierwsza styczność z narzędziem Microsoft Power BI, możesz się o nim dowiedzieć więcej na stronie [Przewodnika z instruktażem po narzędziu Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Raporty dostępne w pakiecie zawartości mają wykresy i tabele przedstawiające dodatkowe informacje. W poniższej tabeli opisano dostępne raporty.

| Raport                     | Zawartość                                                                                                                              |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Analiza wynagrodzeń i świadczeń | Pracownicy akordowi i etatowi według firmy, średnia stawka godzinowa, średnie wynagrodzenie etatowe, pracownicy według typu oraz rejestracja w planie |
| Świadczenia dla pracowników          | Rejestracje pracowników wg wybranego świadczenia                                                                                               |

Wykresy i kafelki w tych raportach można filtrować oraz przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Dane programu Finance and Operations są używane do wypełniania raportów w pakiecie zawartości Wynagrodzenia i świadczenia. W poniższej tabeli przedstawiono jednostki, na których bazuje pakiet.

| Jednostka                            | Zawartość                                                                                                   | Powiązania z innymi jednostkami |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Workforce\_CalendarOffset         | Przesunięcia kalendarzy dla raportów wycinkowych                                                                          | Workforce\_PastPositionAssignment, Workforce\_PositionTrend, Workforce\_WorkerTrend, Workforce\_TerminatedWorker |
| Workforce\_Company                | Firmy, według których będą filtrowane raporty                                                                             | Workforce\_CurrentCompensation, Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Compensation           | Stawka płacy i częstotliwość wypłat w okresie                                                                           | Workforce\_CurrentCompensation, Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_CurrentCompensation    | Stawka płacy i częstotliwość wypłat na obecny dzień                                                              | Workforce\_Company, Workforce\_Compensation, Workforce\_Demographics, Workforce\_Job, Workforce\_Position |
| Workforce\_CurrentPosition        | Stanowiska na obecny dzień, równoważnik pełnego etatu (FTE), wolne stanowiska i stanowiska wolne do obsadzenia | Workforce\_Job, Workforce\_Position |
| Workforce\_CurrentWorker          | Liczba pracowników na obecny dzień, wiek i stan osobowy                                                         | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Job, Workforce\_Employment, Workforce\_Position, Workforce\_WorkerBenefit |
| Workforce\_Date                   | Dni, tygodnie, miesiące i lata                                                                             | Workforce\_PastPositionAssignment, Workforce\_PositionTrend, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Demographics           | Data urodzenia, płeć, pochodzenie etniczne i stan cywilny                                                   | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Employment             | Data rozpoczęcia, data zakończenia i data przejścia                                                                  | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_GeographicLocation     | Miejscowość, kod pocztowy i województwo                                                           | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Job                    | Funkcja, typ i tytuł                                                                                  | Workforce\_CurrentPosition, Workforce\_CurrentWorker |
| Workforce\_PastPositionAssignment | Przyczyna przypisania, data rozpoczęcia, data zakończenia i zadanie                                                           | Workforce\_CalendarOffset, Workforce\_Date, Workforce\_Job, Workforce\_Position |
| Workforce\_Performance            | Ocena, opis i model oceniania                                                                      | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Position               | Dział, równoważnik pełnego etatu, stanowisko, typ stanowiska i tytuł                                                        | Workforce\_CurrentPosition, Workforce\_CurrentWorker |
| Workforce\_PositionTrend          | Stanowiska zajmowane w okresie, równoważnik pełnego etatu i zadanie                                                                          | Workforce\_CalendarOffset, Workforce\_Date, Workforce\_Job, Workforce\_Position |
| Workforce\_ReportsToWorkerName    | Imię, drugie imię i nazwisko                                                                       | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Skill                  | Umiejętności, typ umiejętności i klasyfikacja                                                                              | |
| Workforce\_TerminatedWorker       | Zwolnieni pracownicy, data rozwiązania stosunku pracy, tytuł, stanowisko i zadanie                                             | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_CalendarOffset, Workforces\_Date, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Employment, Workforce\_Job, Workforce\_Position, Workforce\_WorkerBenefit |
| Workforce\_WorkerBenefit          | Data wejścia w życie, opcja świadczenia, plan świadczeń i typ świadczenia                                             | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_WorkerName             | Imię, drugie imię i nazwisko                                                                       | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_WorkerTitle            | Tytuł i data ustalenia stażu pracy                                                                                   | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_WorkerTrend            | Liczba pracowników w okresie, stan osobowy, firma i stanowisko                                                        | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_CalendarOffset, Workforces\_Date, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Employment, Workforce\_Job, Workforce\_WorkerBenefit |
