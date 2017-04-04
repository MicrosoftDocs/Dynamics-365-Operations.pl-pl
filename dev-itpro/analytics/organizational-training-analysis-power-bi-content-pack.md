---
title: "Zawartość szkolenia Power BI organizacyjne"
description: "W tym temacie opisano 365 Dynamics dla operacji - zawartość organizacyjnej szkolenia Power BI. Wyjaśniono, jak dostęp do zawartości pack i opisuje model danych i podmiotów, które były użyte do utworzenia pakietu zawartości."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 104164f8ffd0d2bc3a64bf15d2fb5213234046ce
ms.lasthandoff: 03/31/2017


---

# <a name="organizational-training-power-bi-content"></a>Zawartość szkolenia Power BI organizacyjne

W tym temacie opisano 365 Dynamics dla operacji - zawartość organizacyjnej szkolenia Power BI. Wyjaśniono, jak dostęp do zawartości pack i opisuje model danych i podmiotów, które były użyte do utworzenia pakietu zawartości.

<a name="accessing-the-content-pack"></a>Uzyskiwanie dostępu do zawartości pack
--------------------------

Szkolenie organizacyjne pack zawartości można znaleźć w bibliotece zasobów współużytkowanych w Microsoft Dynamics cyklu życia usługi (LCS). Aby uzyskać więcej informacji o tym, jak pobrać pakiet zawartości i podłącz go do sieci Microsoft Dynamics 365 dla danych operacji, zobacz [Power BI zawartości w LCS firmy Microsoft i jej partnerzy](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Raporty, które są zawarte w pakiecie zawartości
Po połączeniu content pack na swoim 365 Dynamics dla operacji danych, raporty wyświetlanie danych organizacji. Jeśli nigdy nie używane Microsoft Power BI przed, można znaleźć informacje na jego temat na [stronę z przewodnikiem nauki BI zasilania](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Raporty, które są zawarte w pakiecie zawartości mają zarówno wykresów i tabel, które zawierają dodatkowe informacje. W poniższej tabeli opisano dostępne raporty.

| Raport          | Zawartość                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Analiza przebiegu | Rejestracja według lokalizacji, Uczestnicy kursu przez stan i Lista rejestracyjna |
| Typy kursów    | Typy kursów wg kwalifikacji                                                       |

Można filtrować wykresy i płytki na te raporty i przypiąć wykresy i płytki do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtru i numer pin w BI zasilania, zobacz [tworzenie i konfigurowanie pulpitu nawigacyjnego A](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Dynamics 365 dla danych operacji jest używany do wypełniania raportów w pakiecie zawartości szkolenie organizacyjne. W poniższej tabeli przedstawiono podmiotów, że dodatek został oparty na.

| Jednostka                    | Zawartość                                                         | Relacje z innymi encjami                                                                                                                                                                  |
|---------------------------|------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Szkolenia\_CalendarOffset  | Kalendarz jest przeciwstawna do plasterka raportów                                | Szkolenia\_szkolenia CourseAgenda\_CourseAttendees                                                                                                                                                   |
| Szkolenia\_firmy         | Firm do filtrowania raportów przez                                   | Szkolenia\_szkolenia CourseAgenda\_CourseAttendees                                                                                                                                                   |
| Szkolenia\_kursu          | Kurs, opis, imię i nazwisko instruktora, lokalizacji, miejsca i stanu | Szkolenia\_szkolenia CourseAgenda\_szkolenia CourseAttendees\_CourseSkill                                                                                                                             |
| Szkolenia\_CourseAgenda    | Plan spotkania, kurs i czas rozpoczęcia i zakończenia                          | Szkolenia\_szkolenie firmowe\_szkolenia CalendarOffset\_Data szkolenia\_kursu                                                                                                                         |
| Szkolenia\_CourseAttendees | Data nazwa, stan, zadanie i rejestracji                         | Szkolenia\_szkolenie firmowe\_szkolenia CalendarOffset\_Data szkolenia\_dane demograficzne szkolenia\_szkolenia zatrudnienia\_kurs kształcenia\_szkolenia WorkerName\_WorkerTitle szkolenia\_szkoleniem zawodowym\_pozycji |
| Szkolenia\_CourseSkill     | Umiejętności, typ kwalifikacji i poziomu                                     | Szkolenia\_kursu                                                                                                                                                                                   |
| Szkolenia\_Data            | Dni, tygodnie, miesiące i lata                                   | Szkolenia\_szkolenia CourseAgenda\_CourseAttendees                                                                                                                                                   |
| Szkolenia\_dane demograficzne    | Data urodzenia, płeć, pochodzenie etniczne i stanu cywilnego         | Szkolenia\_szkolenia CourseAgenda\_CourseAttendees                                                                                                                                                   |
| Szkolenia\_zatrudnienia      | Data rozpoczęcia, Data zakończenia i Data przejścia                        | Szkolenia\_szkolenia CourseAgenda\_CourseAttendees                                                                                                                                                   |
| Szkolenia\_pracy             | Klawisze funkcyjne, typ i tytuł                                        | Szkolenia\_szkolenia CourseAgenda\_CourseAttendees                                                                                                                                                   |
| Szkolenia\_pozycji        | Pozycja, tytuł i ekwiwalent pełnego wymiaru czasu (ekwiwalent pełnego wymiaru czasu)                  | Szkolenia\_szkolenia CourseAgenda\_CourseAttendees                                                                                                                                                   |
| Szkolenia\_WorkerName      | Imię, nazwisko i imię i nazwisko                             | Szkolenia\_CourseAttendees                                                                                                                                                                          |
| Szkolenia\_WorkerTitle     | Data tytuł i stażu pracy                                         | Szkolenia\_CourseAttendees                                                                                                                                                                          |

Podmioty te były używane do tworzenia miar obliczeniowych w modelu danych. Obliczone te środki są następnie używane do obliczania kluczowych wskaźników wydajności (KPI) i raportów, które są używane w pakiecie zawartości. Jeśli chcesz dołączyć dodatkowe obliczenia w raportach i na pulpicie nawigacyjnym, można pobrać i zmodyfikować plik Training.pbix z LCS. Ten plik jest domyślny model danych, który został użyty do utworzenia pakietu zawartości. Po dokonaniu modyfikacji, można utworzyć organizacyjnej content pack oraz pulpitu nawigacyjnego, które zawierają informacje, które zostały dodane.

## <a name="additional-resources"></a>Dodatkowe zasoby
Poniżej przedstawiono niektóre przydatne łącza dotyczące jednostek i tworzenia zawartości w narzędziu Power BI:

-   [Jednostki danych](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Tworzenie organizacyjnych pakietów zawartości](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelowanie danych przy użyciu narzędzia Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Dodawanie kafelków narzędzia Power BI do obszarów roboczych](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



