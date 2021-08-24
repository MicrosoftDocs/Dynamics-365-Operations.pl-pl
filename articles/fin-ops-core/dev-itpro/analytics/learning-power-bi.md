---
title: Pakiet zawartości usługi Power BI Szkolenia
description: W tym temacie opisano pakiet zawartość Szkolenia dostępny dla usługi Power BI.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 6236868dca26be8cf54ad3cf73e846f2e689af8635e212c493b65a5d1aaa62ed
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742345"
---
# <a name="learning-power-bi-content"></a>Pakiet zawartości usługi Power BI Szkolenia

[!include [banner](../includes/banner.md)]

W tym temacie opisano pakiet zawartości **Szkolenia** dostępny dla usługi Microsoft Power BI.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Raporty dostępne w pakiecie zawartości dla usługi Power BI

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

Wykresy i kafelki w tych raportach można filtrować oraz przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]