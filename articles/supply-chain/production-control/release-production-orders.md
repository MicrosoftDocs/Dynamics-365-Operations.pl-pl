---
title: Zwalnianie zleceń produkcyjnych
description: Zwolnione zlecenie produkcyjne to zlecenie zatwierdzone do produkcji. Określenie „zwolnione” opisuje stan w cyklu życia zlecenia produkcyjnego, gdzie jest ono dostępne do wykonania na wydziale produkcji i dla procesów magazynowych.
author: johanhoffmann
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 740ac516ffa01d8930aedabb9873834b07b7debf700dc61b14d93ac8d6dcd086
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718877"
---
# <a name="release-production-orders"></a>Zwalnianie zleceń produkcyjnych

[!include [banner](../includes/banner.md)]

Zwolnione zlecenie produkcyjne to zlecenie zatwierdzone do produkcji. Określenie „zwolnione” opisuje stan w cyklu życia zlecenia produkcyjnego, gdzie jest ono dostępne do wykonania na wydziale produkcji i dla procesów magazynowych.

## <a name="characteristics-of-the-released-state"></a>Właściwości stanu Zwolnione

Stan **Zwolnione** jest stanem jednego cyklu życia zlecenia produkcyjnego. Zlecenia produkcyjne ze stanem **Zwolnione** są dostępne do wykonania w wydziale produkcji oraz dla procesów magazynowych. Stan **Zwolnione** posiada następujące właściwości:

- Stan zlecenia produkcyjnego może zostać zmieniony na **Zwolnione** ze zlecenia produkcyjnego lub za pomocą produkcji seryjnej. Zlecenie produkcyjne można także aktualizować automatycznie z planowanych zleceń produkcyjnych, które będą ustalane w polu **Horyzont czasowy akceptacji** na stronie **planu głównego**.
- Stan **Zwolnione** jest sygnałem dla operatorów do rozpoczęcia wykonywania zadań produkcyjnych w wydziale produkcyjnym.
- Dokumenty produkcji, takie jak karty marszruty i karty zadań zawierają informacje o zadaniach produkcji i mogą być wystawiane.
- W przypadku materiałów fizycznie zarezerwowanych generowana jest praca w magazynie w celu pobrania materiałów koniecznych do realizacji zlecenia produkcyjnego.

## <a name="releasing-jobs-to-the-shop-floor"></a>Zwalnianie zadań do wydziału produkcyjnego

Po zwolnieniu zlecenia produkcyjnego, zadania produkcji, które są związane z zamówieniem, są widoczne i gotowe do rejestracji. Operatorzy wprowadzają rejestracje zadań, takie jak Rozpoczęcie, Zatrzymanie i Zakończenie, na stronie **Terminal kart zadań** lub **Urządzenia karty zadań**. Zarejestrowany czas i ilości są automatycznie przenoszone ze stron rejestracji do arkuszy produkcji w celu śledzenia zużycia czasu i ilości.

## <a name="route-cards"></a>Karty marszrut

Karta marszrut zawiera przegląd informacji z konfiguracji marszruty i operacji oraz z metod planowania operacji i zadania.

## <a name="route-jobs"></a>Zadania marszruty

W zadaniu marszruty są wymienione wraz ze szczegółami wszystkie zadania w ramach operacji, a także jest podany czas konfiguracji, procesu, oczekiwania i czas transportu. Na przykład operacja malowania może się składać z kilku pojedynczych zadań – przygotowania, wykonywania pracy (czyli malowania) i czas oczekiwania (na wyschnięcie pomalowanej powierzchni).

## <a name="job-cards"></a>Karty zadania

W karcie zadania są wymienione numery poszczególnych zadań w ramach określonej operacji. Jedno zadanie pojawia się na każdej stronie. Zadania znajdujące się na karcie zadania, a także szacunkowe czasy tych zadań są podawane na podstawie informacji konfiguracyjnych marszruty i operacji. Za pomocą karty zadań można otworzyć stronę **Wiersze arkusza produkcji**, **karta zadań**. Osoby, które pracują w gniazdach produkcyjnych, mogą dostarczać informacji zwrotnych dotyczących procesu produkcji. W tych polach można wprowadzać dane statystyczne zużycia oraz informacje o niewłaściwych ilościach.

## <a name="warehouse-work-for-raw-material-picking"></a>Praca magazynu dla pobrania surowca.

Praca pobrania surowca jest generowana podczas zwalniania. Praca jest generowana tylko dla ilości materiałów fizycznie zarezerwowanej dla zlecenia produkcyjnego przed zwolnieniem zlecenia. Do wygenerowania pracy magazynu dla pobrania surowca konieczna jest następująca konfiguracja:

- Dyrektywa lokalizacji dla pobrania surowca, która określa lokalizację pobrania surowca
- Szablon grupy czynności dla surowców, w którym skonfigurowano zasady wykonania pracy w magazynie
- Lokalizacja wejściowa produkcji, która określa umieszczenie materiałów

Korzystając z lokalizacji kontrolowanych za pomocą tablic rejestracyjnych, można wybrać, czy zamówiona ilość lub pełna ilość dostępna dla towaru ma zostać pobrana podczas przetwarzania pracy związanej z pobieraniem surowca. Aby ustawić tę opcję:

1. Otwórz **Zarządzanie informacjami o produktach \> Produkty \> Wydane produkty** i otwórz odpowiednią pozycję.
1. Rozwiń skróconą kartę **Magazyn**.
1. Wybierz jedną z następujących opcji pola  **Pobieranie materiałów w lokalizacjach z tablicami rejestracyjnymi**:
    - *Pobieranie zamówień*: Należy pobrać tylko zamówioną ilość.
    - *Przemieszczanie*: O ile to możliwe, należy wybrać pełną ilość dostępną na tablicy rejestracyjnej. Aby pracownik mógł pobrać pełną liczbę numerów rejestracyjnych, numer rejestracyjny nie może zawierać elementów mieszanych i nie może mieć różnych wymiarów. Jeśli tablica rejestracyjna zawiera mieszane wymiary lub przedmioty, odbiór będzie przebiegał tak, jakby był ustawiony na *Pobieranie zamówień*.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]