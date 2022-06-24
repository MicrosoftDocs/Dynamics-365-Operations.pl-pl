---
title: Pakiet zawartości Wynagrodzenia i świadczenia dostępny w usłudze Power BI
description: W tym artykule opisano zawartość pakietu kompensacji i świadczeń dostępnego dla usługi Power BI.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 263914
ms.assetid: 18634bb5-3341-42f2-9cc9-7b04708b506b
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bed0e8ffbd23c6793c037bade218f637105734b8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908627"
---
# <a name="compensation-and-benefits-power-bi-content"></a>Pakiet zawartości Wynagrodzenia i świadczenia dostępny w usłudze Power BI

[!include [banner](../includes/banner.md)]

W tym artykule opisano zawartość pakietu kompensacji i świadczeń dostępnego dla usługi Power BI. 

## <a name="reports-that-are-included-in-the-content-pack"></a>Raporty dostępne w pakiecie zawartości
Gdy utworzysz połączenie między pakietem zawartości a Twoimi danymi, w raportach są wyświetlone dane organizacji. Jeśli to Twoja pierwsza styczność z narzędziem Microsoft Power BI, możesz się o nim dowiedzieć więcej na stronie [Przewodnika z instruktażem po narzędziu Power BI](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData). Raporty dostępne w pakiecie zawartości mają wykresy i tabele przedstawiające dodatkowe informacje. W poniższej tabeli opisano dostępne raporty.

| Raport                     | Zawartość                                                                                                                              |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Analiza wynagrodzeń i świadczeń | Pracownicy akordowi i etatowi według firmy, średnia stawka godzinowa, średnie wynagrodzenie etatowe, pracownicy według typu oraz rejestracja w planie |
| Świadczenia dla pracowników          | Rejestracje pracowników wg wybranego świadczenia                                                                                               |

Wykresy i kafelki w tych raportach można filtrować oraz przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Dane aplikacji są używane do wypełniania raportów w pakiecie zawartości Wynagrodzenia i Świadczenia. W poniższej tabeli przedstawiono jednostki, na których bazuje pakiet.

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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]