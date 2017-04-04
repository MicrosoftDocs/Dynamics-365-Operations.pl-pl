---
title: "Kompetencje pracownika i Power BI Development zawartości"
description: "W tym temacie opisano 365 Dynamics dla operacji - kompetencje pracownika i rozwoju Power BI zawartości. Wyjaśnia, jak uzyskać dostęp do raportów, które są zawarte w pakiecie zawartości i zawiera informacje o modelu danych i podmiotów, które były użyte do utworzenia pakietu zawartości."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263894
ms.assetid: 7d375d8a-b2de-4bec-b575-93d1d4521b79
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 1fd6f978b6a871f9f7d3d5e91ab3e0aac789ae88
ms.lasthandoff: 03/31/2017


---

# <a name="employee-competencies-and-development-power-bi-content"></a>Kompetencje pracownika i Power BI Development zawartości

W tym temacie opisano 365 Dynamics dla operacji - kompetencje pracownika i rozwoju Power BI zawartości. Wyjaśnia, jak uzyskać dostęp do raportów, które są zawarte w pakiecie zawartości i zawiera informacje o modelu danych i podmiotów, które były użyte do utworzenia pakietu zawartości.

<a name="accessing-the-content-pack"></a>Uzyskiwanie dostępu do zawartości pack
--------------------------

Można znaleźć pracowników kompetencje i charakter rozwojowy dodatkiem Service pack w bibliotece zasobów współużytkowanych w Microsoft Dynamics cyklu życia usługi (LCS). Aby uzyskać więcej informacji o tym, jak pobrać pakiet zawartości i podłącz go do sieci Microsoft Dynamics 365 dla danych operacji, zobacz [Power BI zawartości w LCS firmy Microsoft i jej partnerzy](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Raporty, które są zawarte w pakiecie zawartości
Po połączeniu content pack na swoim 365 Dynamics dla operacji danych, raporty wyświetlanie danych organizacji. Jeśli nigdy nie używane Microsoft Power BI przed, można znaleźć informacje na jego temat na [stronę z przewodnikiem nauki BI zasilania](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Raporty, które są zawarte w pakiecie zawartości mają zarówno wykresów i tabel, które zawierają dodatkowe informacje. W poniższej tabeli opisano dostępne raporty.

| Raport                            | Zawartość                                               |
|-----------------------------------|--------------------------------------------------------|
| Analiza rozwoju i kompetencji | Typy umiejętności członka zespołu i umiejętności członka zespołu według typu |
| Profil umiejętności                     | Profil kwalifikacji wybranego pracownika                |
| Analiza kwalifikacji                    | Umiejętności wg typu i ocena                              |

Można filtrować wykresy i płytki na te raporty i przypiąć wykresy i płytki do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtru i numer pin w BI zasilania, zobacz [tworzenie i konfigurowanie pulpitu nawigacyjnego A](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Dynamics 365 dla danych operacji jest używany do wypełniania raportów w kompetencji pracownika i rozwój content pack. W poniższej tabeli przedstawiono podmiotów, że dodatek został oparty na.

| Jednostka                            | Zawartość                                                                                                   | Relacje z innymi encjami                                                                                                                                                                                                                                                                       |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pracownicy\_CalendarOffset         | Kalendarz jest przeciwstawna do plasterka raportów                                                                          |                                                                                                                                                                                                                                                                                                         |
| Pracownicy\_firmy                | Firm do filtrowania raportów przez                                                                             |                                                                                                                                                                                                                                                                                                         |
| Pracownicy\_odszkodowania           | Stawka płacy i częstość w czasie                                                                           |                                                                                                                                                                                                                                                                                                         |
| Pracownicy\_CurrentCompensation    | Stawka płacy i częstotliwość bieżącej daty                                                              | Pracowników\_pracowników firmy\_pracowników CurrentCompensation\_dane demograficzne pracowników\_pracy pracowników\_pozycji                                                                                                                                                                                            |
| Pracownicy\_CurrentPosition        | Otworzyć stanowiska na bieżący dzień, ekwiwalent pełnego wymiaru czasu (ekwiwalent pełnego wymiaru czasu), pozycje i otwórz wypełnione pozycje | Pracownicy\_pracy pracowników\_pozycji                                                                                                                                                                                                                                                                      |
| Pracownicy\_CurrentWorker          | Pracowników, począwszy od bieżącej daty, wiek i liczba pracowników                                                         | Siły roboczej\_pracowników firmy\_wynagrodzenia pracowników\_pracowników Połgeogr\_wydajności pracowników\_pracowników PersonSkill\_WorkerName pracowników\_pracowników ReportsToWorkerName\_WorkerTitle pracowników\_demografii pracowników\_pracy pracowników\_zatrudnienia pracowników\_pozycji                     |
| Pracownicy\_Data                   | Dni, tygodnie, miesiące i lata                                                                             |                                                                                                                                                                                                                                                                                                         |
| Pracownicy\_dane demograficzne           | Data urodzenia, płeć, pochodzenie etniczne i stanu cywilnego                                                   |                                                                                                                                                                                                                                                                                                         |
| Pracownicy\_zatrudnienia             | Data rozpoczęcia, Data zakończenia i Data przejścia                                                                  |                                                                                                                                                                                                                                                                                                         |
| Pracownicy\_Połgeogr     | Miasto, kod pocztowy, Powiat i województwo                                                           |                                                                                                                                                                                                                                                                                                         |
| Pracownicy\_pracy                    | Klawisze funkcyjne, typ i tytuł                                                                                  |                                                                                                                                                                                                                                                                                                         |
| Pracownicy\_JobPreferredSkill      | Poziom znaczenie, ocena, umiejętności i kwalifikacji                                                                 | Pracownicy\_umiejętności pracowników\_pracy                                                                                                                                                                                                                                                                         |
| Pracownicy\_PastPositionAssignment | Przyczyny przypisania, Data rozpoczęcia, Data zakończenia i zadania                                                           | Pracowników\_pracowników ClaendarOffset\_Data pracowników\_pracy pracowników\_pozycji                                                                                                                                                                                                                            |
| Pracownicy\_wydajności            | Ocena, opis i model oceniania                                                                      |                                                                                                                                                                                                                                                                                                         |
| Pracownicy\_PersonSkill            | Poziom, Data poziomu i umiejętności                                                                               | Pracownicy\_kwalifikacji                                                                                                                                                                                                                                                                                        |
| Pracownicy\_PersonSkillAnalysis    | Data kwalifikowanego, poziom, poziom i umiejętności                                                                    | Pracownicy\_pracowników WorkerName\_kwalifikacji                                                                                                                                                                                                                                                                  |
| Pracownicy\_pozycji               | Dział, ekwiwalent pełnego wymiaru czasu, położenie, typ stanowiska i tytuł                                                        |                                                                                                                                                                                                                                                                                                         |
| Pracownicy\_PositionTrend          | Pozycje w czasie, ekwiwalent pełnego wymiaru czasu i pracy                                                                          | Pracowników\_pracowników CalendarOffset\_Data pracowników\_pracy pracowników\_pozycji                                                                                                                                                                                                                            |
| Pracownicy\_ReportsToWorkerName    | Imię, nazwisko i imię i nazwisko                                                                       |                                                                                                                                                                                                                                                                                                         |
| Pracownicy\_kwalifikacji                  | Umiejętności, typ umiejętności i klasyfikacja                                                                              |                                                                                                                                                                                                                                                                                                         |
| Pracownicy\_TerminatedWorker       | Zakończone pracowników, Data zakończenia, tytuł, położenie i zadania                                             | Siły roboczej\_pracowników firmy\_wynagrodzenia pracowników\_pracowników Połgeogr\_wydajności pracowników\_pracowników WorkerName\_pracowników ReportsToWorkerName\_CalendarOffset zasoby ludzkie\_Data siły roboczej\_pracowników WorkerTitle\_dane demograficzne pracowników\_zatrudnienia pracowników\_pracy pracowników\_pozycji |
| Pracownicy\_WorkerName             | Imię, nazwisko i imię i nazwisko                                                                       |                                                                                                                                                                                                                                                                                                         |
| Pracownicy\_WorkerTitle            | Data tytuł i stażu pracy                                                                                   |                                                                                                                                                                                                                                                                                                         |
| Workorce\_WorkerTrend             | Pracownicy w czasie, liczba pracowników, firmy i stanowisko                                                        | Siły roboczej\_pracowników firmy\_wynagrodzenia pracowników\_pracowników Połgeogr\_wydajności pracowników\_pracowników WorkerName\_pracowników ReportsToWorkerName\_CalendarOffset zasoby ludzkie\_Data siły roboczej\_pracowników WorkerTitle\_dane demograficzne pracowników\_zatrudnienia pracowników\_zadania                     |

Podmioty te były używane do tworzenia miar obliczeniowych w modelu danych. Obliczone te środki są następnie używane do obliczania kluczowych wskaźników wydajności (KPI) i raportów, które są używane w pakiecie zawartości. Jeśli chcesz dołączyć dodatkowe obliczenia w raportach i na pulpicie nawigacyjnym, można pobrać i zmodyfikować plik CompetenciesandDevelopment.pbix z LCS. Ten plik jest domyślny model danych, który został użyty do utworzenia pakietu zawartości. Po dokonaniu modyfikacji, można utworzyć organizacyjnej content pack oraz pulpitu nawigacyjnego, które zawierają informacje, które zostały dodane.

## <a name="additional-resources"></a>Dodatkowe zasoby
Poniżej przedstawiono niektóre przydatne łącza dotyczące jednostek i tworzenia zawartości w narzędziu Power BI:

-   [Jednostki danych](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Tworzenie organizacyjnych pakietów zawartości](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelowanie danych przy użyciu narzędzia Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Dodawanie kafelków narzędzia Power BI do obszarów roboczych](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



