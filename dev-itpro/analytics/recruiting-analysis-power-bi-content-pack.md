---
title: "Rekrutacja Power BI zawartości"
description: "W tym temacie opisano 365 Dynamics dla operacji - Rekrutacja Power BI zawartości. Wyjaśnia, jak uzyskać dostęp do raportów, które są zawarte w pakiecie zawartości i zawiera informacje o modelu danych i podmiotów, które były użyte do utworzenia pakietu zawartości."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: d307733193b388149f83dd420cc7003edcf7749a
ms.lasthandoff: 03/31/2017


---

# <a name="recruiting-power-bi-content"></a>Rekrutacja Power BI zawartości

W tym temacie opisano 365 Dynamics dla operacji - Rekrutacja Power BI zawartości. Wyjaśnia, jak uzyskać dostęp do raportów, które są zawarte w pakiecie zawartości i zawiera informacje o modelu danych i podmiotów, które były użyte do utworzenia pakietu zawartości.

<a name="accessing-the-content-pack"></a>Uzyskiwanie dostępu do zawartości pack
--------------------------

Rekrutacja pack zawartości można znaleźć w bibliotece zasobów współużytkowanych w Microsoft Dynamics cyklu życia usługi (LCS). Aby uzyskać więcej informacji o tym, jak pobrać pakiet zawartości i podłącz go do sieci Microsoft Dynamics 365 dla danych operacji, zobacz [Power BI zawartości w LCS firmy Microsoft i jej partnerzy](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Raporty, które są zawarte w pakiecie zawartości
Po połączeniu content pack na swoim 365 Dynamics dla operacji danych, raporty wyświetlanie danych organizacji. Jeśli nigdy nie używane Microsoft Power BI przed, można znaleźć informacje na jego temat na [stronę z przewodnikiem nauki BI zasilania](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Raporty, które są zawarte w pakiecie zawartości mają zarówno wykresów i tabel, które zawierają dodatkowe informacje. W poniższej tabeli opisano dostępne raporty.

| Raport                       | Zawartość                                                                                               |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Wnioskodawca analizy           | Wnioskodawcy przez zadanie, wnioskodawca źródeł, wnioskodawcy według lokalizacji i łączna liczba kandydatów           |
| Stan kandydata             | Wnioskodawców przez typ, stan i Stan kandydata                                                    |
| Dane demograficzne kandydata       | Wnioskodawcy według płci i wieku i kandydatów według poziomu edukacji i stanu                             |
| Analiza rekrutacji          | Współczynnik zatrudnienia netto, średnia liczba dni zatrudnić procent uszkodzonych wynajmuje i koszty rekrutacji                    |
| Analiza projektu rekrutacji | Liczba projektów rekrutacji, otwory według projektów rekrutacji kandydatów i według projektów rekrutacji |

Można filtrować wykresy i płytki na te raporty i przypiąć wykresy i płytki do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtru i numer pin w BI zasilania, zobacz [tworzenie i konfigurowanie pulpitu nawigacyjnego A](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Dynamics 365 dla danych operacji jest używany do wypełniania raportów w pakiecie zawartości Rekrutacja. W poniższej tabeli przedstawiono podmiotów, że dodatek został oparty na.

| Jednostka                          | Zawartość                                                         | Relacje z innymi encjami                                                                                                                                                                                                                 |
|---------------------------------|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Rekrutacja\_wnioskodawcy           | Wnioskodawcy, zatrudniania kandydatów, stosunek zatrudnienia netto i kosztów          | Rekrutacja\_rekrutacji ApplicantName\_firmy rekrutacji\_CalendarOffset Recuriting\_Data rekrutacji\_rekrutacji Połgeogr\_dane demograficzne rekrutacji\_pracy Rekrutacja\_nośników rekrutacji\_RecruitmentProject                                |
| Rekrutacja\_ApplicantName       | Wnioskodawca imię, nazwisko i imię i nazwisko                   | Rekrutacja\_wnioskodawcy rekrutacji\_rekrutacji EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrutacja\_CalendarOffset      | Kalendarz jest przeciwstawna do plasterka raportów                                | Rekrutacja\_wnioskodawcy rekrutacji\_rekrutacji EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrutacja\_firmy             | Firm do filtrowania raportów przez                                   | Rekrutacja\_wnioskodawcy rekrutacji\_rekrutacji EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrutacja\_Data                | Dni, tygodnie, miesiące i lata                                   | Rekrutacja\_wnioskodawcy rekrutacji\_rekrutacji EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrutacja\_dane demograficzne        | Data urodzenia, płeć, pochodzenie etniczne i stanu cywilnego         | Rekrutacja\_wnioskodawcy rekrutacji\_rekrutacji EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrutacja\_EmployedApplicant   | Wnioskodawca, wydajność, Data rozpoczęcia i typ kandydata           | Rekrutacja\_firmy rekrutacji\_rekrutacji CalendarOffset\_Data rekrutacji\_rekrutacji Połgeogr\_ApplicantName rekrutacji\_rekrutacji zatrudnienia\_rekrutacji wydajności\_zadanie rekrutacji\_nośników rekrutacji\_RecruitmentProject          |
| Rekrutacja\_zatrudnienia          | Data rozpoczęcia, Data zakończenia i Data przejścia                        | Rekrutacja\_wnioskodawcy rekrutacji\_rekrutacji EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrutacja\_Połgeogr  | Miasto, kod pocztowy, Powiat i województwo                 | Rekrutacja\_wnioskodawcy rekrutacji\_rekrutacji EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrutacja\_pracy                 | Klawisze funkcyjne, typ i tytuł                                        | Rekrutacja\_wnioskodawcy rekrutacji\_rekrutacji EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrutacja\_Media               | Źródło wnioskodawców                                             | Rekrutacja\_wnioskodawcy rekrutacji\_rekrutacji EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrutacja\_wydajności         | Ocena, opis i model oceniania                            | Rekrutacja\_wnioskodawcy rekrutacji\_rekrutacji EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrutacja\_RecruitmentProject  | Opis projektu, stan projektu i otwory                | Rekrutacja\_wnioskodawcy rekrutacji\_rekrutacji EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrutacja\_TerminatedApplicant | Zakończone wnioskodawców, przyczyny, wydajności i daty zakończenia zatrudnienia | Rekrutacja\_firmy rekrutacji\_rekrutacji CalendarOffset\_Data rekrutacji\_rekrutacji Połgeogr\_wydajności rekrutacji\_demografii rekrutacji\_rekrutacji zatrudnienia\_nośników rekrutacji\_rekrutacji RecruitmentProject\_ApplicantName |

Podmioty te były używane do tworzenia miar obliczeniowych. Obliczone te środki są następnie używane do obliczania kluczowych wskaźników wydajności (KPI) i raportów, które są używane w pakiecie zawartości. Jeśli chcesz dołączyć dodatkowe obliczenia w raportach i na pulpicie nawigacyjnym, można pobrać i zmodyfikować plik Recruiting.pbix z LCS. Ten plik jest domyślny model danych, który został użyty do utworzenia pakietu zawartości. Po dokonaniu modyfikacji, można utworzyć organizacyjnej content pack oraz pulpitu nawigacyjnego, które zawierają informacje, które zostały dodane.

## <a name="additional-resources"></a>Dodatkowe zasoby
Poniżej przedstawiono niektóre przydatne łącza dotyczące jednostek i tworzenia zawartości w narzędziu Power BI:

-   [Jednostki danych](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Tworzenie organizacyjnych pakietów zawartości](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelowanie danych przy użyciu narzędzia Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Dodawanie kafelków narzędzia Power BI do obszarów roboczych](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



