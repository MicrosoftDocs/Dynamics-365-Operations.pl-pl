---
title: Pakiet zawartości usługi Power BI Zarządzanie kredytami i windykacją
description: W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI Zarządzanie kredytami i windykacją. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 5ac47ee086569cdaaa3c30f76435432e64f8fac6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189115"
---
# <a name="credit-and-collections-management-power-bi-content"></a>Pakiet zawartości usługi Power BI Zarządzanie kredytami i windykacją

[!include [banner](../includes/banner.md)]

W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Microsoft Power BI **Zarządzanie kredytami i windykacją**. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="overview"></a>Przegląd

Pakiet zawartości usługi Power BI zatytułowany **Zarządzanie kredytami i windykacją** jest przeznaczony dla kierowników ds. kredytów i windykacji oraz dla pracowników ds. windykacji. Zawiera najważniejsze mierniki kredytu i windykacji, takie jak wskaźnik rotacji należności w dniach, saldo zaległości, kwota udzielonych kredytów oraz odbiorcy z przekroczonym limitem kredytu. Wykorzystuje dane transakcyjne i przedstawia zagregowane widoki kredytów i windykacji dla wszystkich firm. Prezentuje także podział na firmy, grupy odbiorców i odbiorców.

Ten pakiet zawartości usługi Power BI zawiera 10 stron raportów:

- Dwie strony informacji ogólnych (jedna dla kredytów i jedna dla windykacji)
- Osiem stron szczegółów, które zawierają szczegółowe informacje o miernikach kredytów i windykacji według różnych wymiarów

Wszystkie kwoty są wyświetlane w walucie systemowej. Można ustawiać walutę systemową na stronie **Parametry systemowe**.

Domyślnie są wyświetlane dane kredytów i windykacji dla bieżącej firmy. Aby wyświetlić dane dla wszystkich firm, należy przypisać obowiązek **CustCollectionsBICrossCompany** do roli.

## <a name="setup-needed-to-view-power-bi-content"></a>Konfiguracja potrzebna do wyświetlenia zawartości Power BI.

Aby dane były wyświetlane, należy wykonać następujące ustawienia **Kredyty i windykacja odbiorcy** materiały ilustracyjne Power BI.

1. Otwórz **Administracja Systemu > Konfiguracja > Parametry Systemu** i ustaw **Walutę systemu** oraz **Kurs wymiany systemu**.
2. Otwórz **Księga ogólna > Konfiguracja > Księga** i ustaw **Waluta księgowa** oraz **Typ kursu wymiany**.
3. Zdefiniuj kursy wymiany między walutami Transakcji a Walutą księgową, Walutą księgową a Walutą systemu. Żeby to zrobić, otwórz **Księga Ogólna > Waluty > Kursy wymiany walut**.
4. Otwórz **Administracja Systemu > Konfiguracja > Sklep podmiotu** i odśwież łączny wskaźnik **CustCollectionsBIMeasurements**.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI

Zawartość usługi Power BI **Zarządzanie kredytami i windykację** jest wyświetlana w obszarze roboczym **Kredyty i windykacja odbiorcy**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Raporty dostępne w pakiecie zawartości dla usługi Power BI

Pakiet zawartości usługi Power BI **CustCollectionsBICrossCompany** obejmuje raport zawierający zbiór mierników. Te wskaźniki są wizualizowane jako wykresy, kafelki i tabele. Poniższa tabela zawiera omówienie wizualizacji dostępnych w pakiecie zawartości usługi Power BI **CustCollectionsBICrossCompany**.

| Strona raportu                 | Wizualizacja |
|-----------------------------|---------------|
| Przegląd windykacji        | <ul><li>Odbiorcy — zaległe</li><li>Odbiorcy przekraczający limit kredytu</li><li>DSO 30 dni</li><li>Otwarte sprawy</li><li>Średnia liczba dni do zamknięcia sprawy</li><li>Otwarte działania</li><li>Średnia liczba dni do zamknięcia działań</li><li>Otwarte noty odsetkowe</li><li>Otwarte ponaglenia</li><li>Wstrzymanie odbiorcy</li><li>Wstrzymanie sprzedaży</li><li>Wiekowane salda</li><li>Kwoty stanu windykacji</li><li>Kwoty kodu windykacji</li><li>Przyczyna odpisu</li><li>Saldo należne według regionów</li><li>Oczekiwane płatności</li></ul> |
| Przegląd kredytów             | <ul><li>Odbiorcy — zaległe</li><li>Limit kredytu a saldo należne</li><li>Tabela odbiorców przekraczających limit kredytu</li><li>Odbiorcy przekraczający limit kredytu na firmę</li><li>Kredyt wykorzystany a łączny limit kredytu</li><li>Limit kredytu a kredyt wykorzystany według regionów</li><li>Odbiorcy na ocenę kredytu</li></ul> |
| Limit kredytu                | <ul><li>Limit kredytu</li><li>Szczegóły limitu kredytu</li><li>Limit kredytu na odbiorcę</li><li>Limit kredytu na grupy odbiorców</li><li>Limit kredytu na ocenę kredytu na firmę</li><li>Limit kredytu a kredyt wykorzystany według regionów</li></ul> |
| Odbiorcy przekraczający limit kredytu | <ul><li>Odbiorcy przekraczający limit kredytu</li><li>Szczegóły odbiorców przekraczających limit kredytu</li><li>Odbiorcy przekraczający limit kredytu na firmę</li><li>Odbiorca przekraczający limit kredytu na grupę odbiorców</li><li>Odbiorcy przekraczający limit kredytu na region</li></ul> |
| Odbiorcy — zaległe          | <ul><li>Odbiorcy — zaległe</li><li>Szczegóły zaległości odbiorców</li><li>Zaległości odbiorców według firmy</li><li>Zaległości odbiorców według grupy odbiorców</li><li>Zaległości odbiorców według regionów</li></ul> |
| Wiekowane salda               | <ul><li>Wiekowane salda</li><li>Szczegóły wiekowanych sald</li><li>Wiekowane salda według firmy</li><li>Wiekowane salda według grup odbiorców</li></ul> |
| Oczekiwane płatności           | <ul><li>Oczekiwane płatności</li><li>Szczegóły oczekiwanych płatności</li><li>Oczekiwane płatności według firmy</li><li>Oczekiwane płatności według grupy odbiorców</li><li>Oczekiwane płatności według regionów</li></ul> |
| Odpisy                  | <ul><li>Odpisy według regionów</li><li>Szczegóły odpisów</li><li>Odpisy według kont głównych</li><li>Odpisy według firm</li><li>Odpisy według grup odbiorców</li><li>Odpisy według regionów</li></ul> |
| Stan windykacji          | <ul><li>Sporne</li><li>Złamane przyrzeczenie zapłaty</li><li>Przyrzeczenie zapłaty</li><li>Szczegóły stanu windykacji</li><li>Kwoty stanu windykacji</li><li>Otwarte sprawy</li><li>Otwarte działania</li></ul> |
| Ponaglenia         | <ul><li>Kwoty kodu ponaglenia</li><li>Szczegóły kwoty kodu ponaglenia</li><li>Kwoty ponagleń według firmy</li><li>Kwoty ponagleń według grupy odbiorców</li><li>Kwoty ponagleń według regionów</li></ul> |

Wykresy i kafelki we wszystkich tych raportach można filtrować i przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w usłudze Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Można także użyć funkcji eksportu danych źródłowych do wyeksportowania danych podsumowanych w wizualizacji.
