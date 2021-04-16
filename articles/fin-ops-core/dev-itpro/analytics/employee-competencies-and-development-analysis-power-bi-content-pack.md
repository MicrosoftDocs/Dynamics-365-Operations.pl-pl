---
title: Pakiet zawartości Kompetencje i rozwój pracownika etatowego dla usługi Power BI
description: W tym temacie opisano pakiet zawartość Kompetencje i rozwój pracownika etatowego w usłudze Power BI.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 263894
ms.assetid: 7d375d8a-b2de-4bec-b575-93d1d4521b79
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 43a6d825de5d8e012d9ccbfccc5d8c708f248981
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751293"
---
# <a name="employee-competencies-and-development-power-bi-content"></a>Pakiet zawartości Kompetencje i rozwój pracownika etatowego dla usługi Power BI

[!include [banner](../includes/banner.md)]

W tym temacie opisano pakiet zawartość Kompetencje i rozwój pracownika etatowego w usłudze Power BI. 

## <a name="reports-that-are-included-in-the-content-pack"></a>Raporty dostępne w pakiecie zawartości
Gdy utworzysz połączenie między pakietem zawartości a Twoimi danymi, w raportach są wyświetlone dane organizacji. Jeśli to Twoja pierwsza styczność z narzędziem Microsoft Power BI, możesz się o nim dowiedzieć więcej na stronie [Przewodnika z instruktażem po narzędziu Power BI](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData). Raporty dostępne w pakiecie zawartości mają wykresy i tabele przedstawiające dodatkowe informacje. W poniższej tabeli opisano dostępne raporty.

| Raport                            | Zawartość                                               |
|-----------------------------------|--------------------------------------------------------|
| Analiza kompetencji i rozwoju | Typy umiejętności członków zespołu i umiejętności członków zespołu z podziałem na typy |
| Profil kwalifikacji                     | Profil kwalifikacji wybranego pracownika etatowego                |
| Analiza kwalifikacji                    | Umiejętności według typu i kategorii                              |

Wykresy i kafelki w tych raportach można filtrować oraz przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Dane aplikacji są używane do wypełniania raportów w pakiecie zawartości Kompetencje i rozwój pracownika etatowego. W poniższej tabeli przedstawiono jednostki, na których bazuje pakiet.

| Jednostka                            | Zawartość                                                                                                   | Powiązania z innymi jednostkami |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Workforce\_CalendarOffset         | Przesunięcia kalendarzy dla raportów wycinkowych                                                                          | |
| Workforce\_Company                | Firmy, według których będą filtrowane raporty                                                                             | |
| Workforce\_Compensation           | Stawka płacy i częstotliwość wypłat w okresie                                                                           | |
| Workforce\_CurrentCompensation    | Stawka płacy i częstotliwość wypłat na obecny dzień                                                              | Workforce\_Company, Workforce\_CurrentCompensation, Workforce\_Demographics, Workforce\_Job, Workforce\_Position |
| Workforce\_CurrentPosition        | Stanowiska na obecny dzień, równoważnik pełnego etatu (FTE), wolne stanowiska i stanowiska wolne do obsadzenia | Workforce\_Job Workforce\_Position |
| Workforce\_CurrentWorker          | Liczba pracowników na obecny dzień, wiek i stan osobowy                                                         | Workforce\_Company Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_PersonSkill, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Job, Workforce\_Employment, Workforce\_Position |
| Workforce\_Date                   | Dni, tygodnie, miesiące i lata                                                                             | |
| Workforce\_Demographics           | Data urodzenia, płeć, pochodzenie etniczne i stan cywilny                                                   | |
| Workforce\_Employment             | Data rozpoczęcia, data zakończenia i data przejścia                                                                  | |
| Workforce\_GeographicLocation     | Miejscowość, kod pocztowy i województwo                                                           | |
| Workforce\_Job                    | Funkcja, typ i tytuł                                                                                  | |
| Workforce\_JobPreferredSkill      | Ważność, ocena, umiejętności i poziom umiejętności                                                                 | Workforce\_Skill, Workforce\_Job |
| Workforce\_PastPositionAssignment | Przyczyna przypisania, data rozpoczęcia, data zakończenia i zadanie                                                           | Workforce\_CalendarOffset, Workforce\_Date, Workforce\_Job, Workforce\_Position |
| Workforce\_Performance            | Ocena, opis i model oceniania                                                                      | |
| Workforce\_PersonSkill            | Poziom, data poziomu i umiejętności                                                                               | Workforce\_Skill |
| Workforce\_PersonSkillAnalysis    | Certyfikaty, poziom, data poziomu i umiejętności                                                                    | Workforce\_WorkerName, Workforce\_Skill |
| Workforce\_Position               | Dział, równoważnik pełnego etatu, stanowisko, typ stanowiska i tytuł                                                        | |
| Workforce\_PositionTrend          | Stanowiska zajmowane w okresie, równoważnik pełnego etatu i zadanie                                                                          | Workforce\_CalendarOffset, Workforce\_Date, Workforce\_Job, Workforce\_Position |
| Workforce\_ReportsToWorkerName    | Imię, drugie imię i nazwisko                                                                       | |
| Workforce\_Skill                  | Umiejętności, typ umiejętności i klasyfikacja                                                                              | |
| Workforce\_TerminatedWorker       | Zwolnieni pracownicy, data rozwiązania stosunku pracy, tytuł, stanowisko i zadanie                                             | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_CalendarOffset, Workforces\_Date, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Employment, Workforce\_Job, Workforce\_Position |
| Workforce\_WorkerName             | Imię, drugie imię i nazwisko                                                                       | |
| Workforce\_WorkerTitle            | Tytuł i data ustalenia stażu pracy                                                                                   | |
| Workorce\_WorkerTrend             | Liczba pracowników w okresie, stan osobowy, firma i stanowisko                                                        | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_CalendarOffset, Workforces\_Date, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Employment, Workforce\_Job |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]