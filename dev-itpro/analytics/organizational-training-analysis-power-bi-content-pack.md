---
title: "Pakiet zawartości usługi Power BI Szkolenie organizacyjne"
description: "W tym temacie opisano pakiet zawartości Dynamics 365 for Operations — Szkolenie organizacyjne dla usługi Power BI. Wyjaśniono, jak uzyskać dostęp do pakietu zawartości, oraz opisano model danych i jednostki użyte do zbudowania pakietu."
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

# <a name="organizational-training-power-bi-content"></a>Pakiet zawartości usługi Power BI Szkolenie organizacyjne

[!include[banner](../includes/banner.md)]


W tym temacie opisano pakiet zawartości Dynamics 365 for Operations — Szkolenie organizacyjne dla usługi Power BI. Wyjaśniono, jak uzyskać dostęp do pakietu zawartości, oraz opisano model danych i jednostki użyte do zbudowania pakietu.

<a name="accessing-the-content-pack"></a>Przechodzenie do pakietu zawartości
--------------------------

Pakiet zawartości Szkolenie organizacyjne znajduje się w bibliotece zasobów wspólnych w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i łączeniu go z danymi usługi Microsoft Dynamics 365 for Operations, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Raporty dostępne w pakiecie zawartości
Gdy utworzysz połączenie między pakietem zawartości a danymi programu Dynamics 365 for Operations, w raportach są wyświetlone dane organizacji. Jeśli to Twoja pierwsza styczność z narzędziem Microsoft Power BI, możesz się o nim dowiedzieć więcej na [stronie Przewodnika z instruktażem po narzędziu Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Raporty dostępne w pakiecie zawartości mają wykresy i tabele przedstawiające dodatkowe informacje. W poniższej tabeli opisano dostępne raporty.

| Raport          | Zawartość                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Analiza kursu | Rejestracja według lokalizacji, uczestnicy kursu według stanu oraz lista rejestracyjna |
| Typy kursów    | Typy kursów wg kwalifikacji                                                       |

Wykresy i kafelki w tych raportach można filtrować oraz przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Dane programu Dynamics 365 for Operations są używane do wypełniania raportów w pakiecie zawartości Szkolenie organizacyjne. W poniższej tabeli przedstawiono jednostki, na których bazuje pakiet.

| Jednostka                    | Zawartość                                                         | Powiązania z innymi jednostkami                                                                                                                                                                  |
|---------------------------|------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Training\_CalendarOffset  | Przesunięcia kalendarzy dla raportów wycinkowych                                | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Company         | Firmy, według których będą filtrowane raporty                                   | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Course          | Kurs, opis, imię i nazwisko instruktora, lokalizacja, pomieszczenie i stan | Training\_CourseAgenda Training\_CourseAttendees Training\_CourseSkill                                                                                                                             |
| Training\_CourseAgenda    | Program kursu, kurs oraz godziny rozpoczęcia i zakończenia                          | Training\_Company Training\_CalendarOffset Training\_Date Training\_Course                                                                                                                         |
| Training\_CourseAttendees | Imię i nazwisko, stan, zadanie i data rejestracji                         | Training\_Company Training\_CalendarOffset Training\_Date Training\_Demographics Training\_Employment Training\_Course Training\_WorkerName Training\_WorkerTitle Training\_Job Training\_Position |
| Training\_CourseSkill     | Umiejętności, typ umiejętności i poziom                                     | Training\_Course                                                                                                                                                                                   |
| Training\_Date            | Dni, tygodnie, miesiące i lata                                   | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Demographics    | Data urodzenia, płeć, pochodzenie etniczne i stan cywilny         | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Employment      | Data rozpoczęcia, data zakończenia i data przejścia                        | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Job             | Funkcja, typ i tytuł                                        | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Position        | Stanowisko, tytuł i równoważnik pełnego etatu (FTE)                  | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_WorkerName      | Imię, drugie imię i nazwisko                             | Training\_CourseAttendees                                                                                                                                                                          |
| Training\_WorkerTitle     | Tytuł i data ustalenia stażu pracy                                         | Training\_CourseAttendees                                                                                                                                                                          |

Te jednostki zostały użyte do utworzenia obliczanych miar w modelu danych. Następnie obliczane miary są używane do obliczania kluczowych wskaźników wydajności (KPI) i generowania raportów, które są używane w pakiecie zawartości. Jeśli chcesz umieścić dodatkowe obliczenia w raportach i na pulpicie nawigacyjnym, możesz z usługi LCS pobrać plik Training.pbix i go zmodyfikować. Ten plik jest domyślnym modelem danych, który został użyty do utworzenia pakietu zawartości. Po wprowadzeniu wszystkich modyfikacji można utworzyć organizacyjny pakiet zawartości i pulpit nawigacyjny, który zawiera dodane informacje.

## <a name="additional-resources"></a>Dodatkowe zasoby
Poniżej przedstawiono niektóre przydatne łącza dotyczące jednostek i tworzenia zawartości w narzędziu Power BI:

-   [Jednostki danych](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Tworzenie organizacyjnych pakietów zawartości](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelowanie danych przy użyciu narzędzia Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Dodawanie kafelków narzędzia Power BI do obszarów roboczych](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





