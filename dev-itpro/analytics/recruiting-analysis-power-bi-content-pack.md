---
title: "Pakiet zawartości usługi Power BI Rekrutacja"
description: "W tym temacie opisano pakiet zawartość Rekrutacja dostępny dla usługi Power BI. Wyjaśniono, jak uzyskać dostęp do raportów, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu."
author: jcart1106
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 49cfd0f1ed645f1980b21b6d4f453cb7a8957a1a
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017

---

# <a name="recruiting-power-bi-content"></a>Pakiet zawartości usługi Power BI Rekrutacja

[!include[banner](../includes/banner.md)]

W tym temacie opisano pakiet zawartość **Rekrutacja** dostępny dla usługi Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI
Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition z aktualizacją z lipca 2017 r., pakiet zawartości usługi Power BI **Rekrutacja** jest wyświetlany w obszarze roboczym **Zarządzanie rekrutacją** . 

## <a name="reports-and-visuals-in-the-recruitment-management-workspace"></a>Raporty i wizualizacje w obszarze roboczym Zarządzanie rekrutacją
Obszar roboczy **Zarządzanie rekrutacją** zawiera kartę **Analizy**. Na tej karcie znajduje się osadzony pakiet zawartości usługi Power BI dotyczący rekrutacji. Pakiet składa się z karty przeglądu oraz dodatkowych kart z informacjami szczegółowymi. W poniższej tabeli opisano raporty dostępne na każdej karcie.

| Raport               | Zawartość |
|----------------------|----------|
| Przegląd regulacji | Podsumowuje inne raporty |
| Analiza kandydatów   | Łączna liczba kandydatów, kandydaci według zadania, źródła kandydatów, proporcja między mężczyznami i kobietami wśród kandydatów i kandydaci według lokalizacji |
| Stan kandydata     | Kandydaci według typu i stanu, stan kandydata |
| Analiza rekrutacji  | Współczynnik zatrudnienia netto, średnia liczba dni do zatrudnienia, procent nietrafionych zatrudnień, koszty rekrutacji, liczba projektów rekrutacji, liczba zatrudnionych kandydatów do liczby zgłoszeń oraz liczba kandydatów do liczby wakatów według projektów rekrutacji |

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek
Wykresy i kafelki w tych raportach można filtrować oraz przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

W poniższej tabeli przedstawiono jednostki, na których bazuje pakiet zawartości **Rekrutacja** dostępny dla usługi Power BI.

| Jednostka               | Zawartość                                                         | Powiązania z innymi jednostkami |
|----------------------|------------------------------------------------------------------|-----------------------------------|
| Kandydat            | Kandydaci, zatrudnieni kandydaci, współczynnik zatrudnienia netto i koszty          | Nazwisko i imię kandydata, Firma, Przesunięcie kalendarza, Data, Położenie geograficzne, Dane demograficzne, Zadanie, Media, Projekt rekrutacji |
| Nazwisko i imię kandydata       | Imię, drugie imię i nazwisko kandydata                   | Kandydat, Zatrudniony kandydat, Odrzucony kandydat |
| Przesunięcie kalendarza      | Przesunięcia kalendarzy dla raportów wycinkowych                                | Kandydat, Zatrudniony kandydat, Odrzucony kandydat |
| Firma              | Firmy, według których będą filtrowane raporty                                   | Kandydat, Zatrudniony kandydat, Odrzucony kandydat |
| Data                 | Dni, tygodnie, miesiące i lata                                   | Kandydat, Zatrudniony kandydat, Odrzucony kandydat |
| Dane demograficzne         | Data urodzenia, płeć, pochodzenie etniczne i stan cywilny         | Kandydat, Zatrudniony kandydat, Odrzucony kandydat |
| Zatrudniony kandydat   | Kandydat, osiągane wyniki, data rozpoczęcia i typ kandydata           | Firma, Przesunięcie kalendarza, Data, Położenie geograficzne, Nazwisko i imię kandydata, Zatrudnienie, Wydajność, Zadanie, Media, Projekt rekrutacji |
| Zatrudnienie           | Data rozpoczęcia, data zakończenia i data przejścia                        | Kandydat, Zatrudniony kandydat, Odrzucony kandydat |
| Położenie geograficzne  | Miejscowość, kod pocztowy i województwo                 | Kandydat, Zatrudniony kandydat, Odrzucony kandydat |
| Stanowisko                  | Funkcja, typ i tytuł                                        | Kandydat, Zatrudniony kandydat, Odrzucony kandydat |
| Multimedia                | Źródło kandydatów                                             | Kandydat, Zatrudniony kandydat, Odrzucony kandydat |
| Wydajność          | Ocena, opis i model oceniania                            | Kandydat, Zatrudniony kandydat, Odrzucony kandydat |
| Projekt rekrutacji  | Opis projektu, stan projektu i wakaty                | Kandydat, Zatrudniony kandydat, Odrzucony kandydat |
| Odrzucony kandydat | Odrzuceni kandydaci, przyczyna, osiągane wyniki i daty zakończenia zatrudnienia | Firma, Przesunięcie kalendarza, Data, Położenie geograficzne, Wydajność, Dane demograficzne, Zatrudnienie, Media, Projekt rekrutacji, Nazwisko i imię kandydata |

Te jednostki zostały użyte do utworzenia obliczanych miar. Następnie obliczone mierniki są używane do obliczania kluczowych wskaźników wydajności (KPI) i generowania raportów, które są używane w pakiecie zawartości. Jeśli chcesz umieścić dodatkowe obliczenia w raportach i na pulpicie nawigacyjnym, możesz z usługi Microsoft Dynamics Lifecycle Services (LCS) pobrać plik Recruiting.pbix i go zmodyfikować. Ten plik jest domyślnym modelem danych, który został użyty do utworzenia pakietu zawartości. Po wprowadzeniu wszystkich modyfikacji można utworzyć organizacyjny pakiet zawartości i pulpit nawigacyjny, który zawiera dodane informacje.

