---
title: "Pakiet zawartości usługi Power BI Szkolenia"
description: "W tym temacie opisano pakiet zawartość Szkolenia dostępny dla usługi Power BI. Wyjaśniono, jak uzyskać dostęp do raportów, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu."
author: jcart1106
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations, Talent, Core
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0136080b12c6c2bd8e65063e99278f163212178c
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="learning-power-bi-content"></a>Pakiet zawartości usługi Power BI Szkolenia

[!include[banner](../includes/banner.md)]

W tym temacie opisano pakiet zawartość **Szkolenia** dostępny dla usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do pakietu zawartości, oraz opisano model danych i jednostki użyte do zbudowania pakietu.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI

Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (lipiec 2017 r.), pakiet zawartości usługi Power BI zatytułowany **Szkolenia** znajduje się w bibliotece zasobów wspólnych w usłudze Microsoft Dynamics Lifecycle Services (LCS). Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i jego implementowaniu w swojej organizacji, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](power-bi-content-microsoft-partners.md). Aby obejrzeć demonstrację przedstawiającą sposób implementowania pakietu zawartości usługi Power BI, zobacz materiał z serii Office Mix [Pakiety zawartości dla usługi Power BI w usłudze Dynamics Lifecycle Services od Microsoft i partnerów](https://mix.office.com/watch/9puyb1b2xs1w).

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Raporty umieszczone w pakiecie zawartości usługi Power BI

Raporty dostępne w pakiecie zawartości usługi Power BI **Szkolenia** mają wykresy i tabele przedstawiające dodatkowe informacje. W poniższej tabeli opisano dostępne raporty.

| Raport                | Zawartość |
|-----------------------|----------|
| Przegląd szkoleń     | Podsumowanie innych raportów |
| Analiza kursu       | Rejestracje według lokalizacji, uczestnicy według stanu, kursy według typu dla każdej firmy oraz uczestnictwo w kursach według zadań |
| Analiza rejestracji | Lista rejestracyjna |
| Typy kursów          | Typy kursów wg kwalifikacji |
| Analiza instruktorów   | Stosunek liczby kursów do liczby instruktorów, liczba instruktorów, kursy według instruktorów, kursy na jednego instruktora oraz terminarze kursów według instruktorów |
| Oferowane kursy       | Wykaz kursów |
| Konstrukcja kursów        | Terminarz kursu |

Wykresy i kafelki w tych raportach można filtrować oraz przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek

Następujące dane są używane do wypełniania raportów w pakiecie zawartości usługi Power BI **Szkolenia**. W tej tabeli przedstawiono jednostki, na których bazuje pakiet.

| Jednostka           | Zawartość                                                         | Powiązania z innymi jednostkami |
|------------------|------------------------------------------------------------------|-----------------------------------|
| Przesunięcie kalendarza  | Przesunięcia kalendarzy dla raportów wycinkowych                                | Terminarz kursu, Uczestnicy kursu |
| Firma          | Firmy, według których będą filtrowane raporty                                   | Terminarz kursu, Uczestnicy kursu |
| Kursy           | Kurs, opis, imię i nazwisko instruktora, lokalizacja, pomieszczenie i stan | Terminarz kursu, Uczestnicy kursu, Umiejętności na kursie |
| Terminarz kursu    | Program kursu, kurs oraz godziny rozpoczęcia i zakończenia                          | Firma, Przesunięcie kalendarza, Data, Kurs |
| Uczestnicy kursu | Imię i nazwisko, stan, zadanie i data rejestracji                         | Firma, Kalendarz, Przesunięcie, Data, Kurs, Dane demograficzne, Zatrudnienie, Nazwisko pracownika etatowego, Tytuł pracownika, Zadanie, Stanowisko |
| Umiejętności na kursie     | Umiejętności, typ umiejętności i poziom                                     | Kursy |
| Data             | Dni, tygodnie, miesiące i lata                                   | Terminarz kursu, Uczestnicy kursu |
| Dane demograficzne     | Data urodzenia, płeć, pochodzenie etniczne i stan cywilny         | Terminarz kursu, Uczestnicy kursu |
| Zatrudnienie       | Data rozpoczęcia, data zakończenia i data przejścia                        | Terminarz kursu, Uczestnicy kursu |
| Stanowisko              | Funkcja, typ i tytuł                                        | Terminarz kursu, Uczestnicy kursu |
| Pozycja         | Stanowisko, tytuł i równoważnik pełnego etatu (FTE)                  | Terminarz kursu, Uczestnicy kursu |
| Nazwisko pracownika etatowego    | Imię, drugie imię i nazwisko                             | Uczestnicy kursu |
| Tytuł pracownika   | Tytuł i data ustalenia stażu pracy                                         | Uczestnicy kursu |

Te jednostki zostały użyte do utworzenia obliczanych miar w modelu danych. Następnie obliczone mierniki są używane do obliczania kluczowych wskaźników wydajności (KPI) i generowania raportów, które są używane w pakiecie zawartości. Jeśli chcesz umieścić dodatkowe obliczenia w raportach i na pulpicie nawigacyjnym, możesz z usługi LCS pobrać plik .pbix i go zmodyfikować. Ten plik jest domyślnym modelem danych, który został użyty do utworzenia pakietu zawartości. Po wprowadzeniu wszystkich modyfikacji można utworzyć organizacyjny pakiet zawartości i pulpit nawigacyjny, który zawiera dodane informacje.
