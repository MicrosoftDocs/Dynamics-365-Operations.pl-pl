---
title: Pakiet zawartości Szkolenie organizacyjne dla usługi Power BI
description: W tym artykule opisano zawartość pakietu aplikacji finansowych i operacyjnych — Szkolenie organizacyjne dla usługi Power BI.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ba332fc0c241969cbe0c25e7985101a2bbe12be4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892429"
---
# <a name="organizational-training-power-bi-content"></a>Pakiet zawartości Szkolenie organizacyjne dla usługi Power BI

[!include [banner](../includes/banner.md)]

W tym artykule opisano zawartość pakietu aplikacji finansowych i operacyjnych — Szkolenie organizacyjne dla usługi Power BI.

## <a name="reports-that-are-included-in-the-content-pack"></a>Raporty dostępne w pakiecie zawartości
Gdy utworzysz połączenie między pakietem zawartości a Twoimi danymi, w raportach są wyświetlone dane organizacji. Jeśli to Twoja pierwsza styczność z narzędziem Microsoft Power BI, możesz się o nim dowiedzieć więcej na stronie [Przewodnika z instruktażem po narzędziu Power BI](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData). Raporty dostępne w pakiecie zawartości mają wykresy i tabele przedstawiające dodatkowe informacje. W poniższej tabeli opisano dostępne raporty.

| Raport          | Zawartość                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Analiza kursu | Rejestracja według lokalizacji, uczestnicy kursu według stanu oraz lista rejestracyjna |
| Typy kursów    | Typy kursów wg kwalifikacji                                                       |

Wykresy i kafelki w tych raportach można filtrować oraz przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Dane aplikacji są używane do wypełniania raportów w pakiecie zawartości Szkolenie organizacyjne. W poniższej tabeli przedstawiono jednostki, na których bazuje pakiet.

| Jednostka                    | Zawartość                                                         | Powiązania z innymi jednostkami |
|---------------------------|------------------------------------------------------------------|-----------------------------------|
| Training\_CalendarOffset  | Przesunięcia kalendarzy dla raportów wycinkowych                                | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Company         | Firmy, według których będą filtrowane raporty                                   | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Course          | Kurs, opis, imię i nazwisko instruktora, lokalizacja, pomieszczenie i stan | Training\_CourseAgenda, Training\_CourseAttendees, Training\_CourseSkill |
| Training\_CourseAgenda    | Program kursu, kurs oraz godziny rozpoczęcia i zakończenia                          | Training\_Company, Training\_CalendarOffset, Training\_Date, Training\_Course |
| Training\_CourseAttendees | Imię i nazwisko, stan, zadanie i data rejestracji                         | Training\_Company, Training\_CalendarOffset, Training\_Date, Training\_Demographics, Training\_Employment, Training\_Course, Training\_WorkerName, Training\_WorkerTitle, Training\_Job, Training\_Position |
| Training\_CourseSkill     | Umiejętności, typ umiejętności i poziom                                     | Training\_Course |
| Training\_Date            | Dni, tygodnie, miesiące i lata                                   | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Demographics    | Data urodzenia, płeć, pochodzenie etniczne i stan cywilny         | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Employment      | Data rozpoczęcia, data zakończenia i data przejścia                        | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Job             | Funkcja, typ i tytuł                                        | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Position        | Stanowisko, tytuł i równoważnik pełnego etatu (FTE)                  | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_WorkerName      | Imię, drugie imię i nazwisko                             | Training\_CourseAttendees |
| Training\_WorkerTitle     | Tytuł i data ustalenia stażu pracy                                         | Training\_CourseAttendees |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]