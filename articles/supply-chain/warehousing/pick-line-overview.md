---
title: Skonfiguruj element menu urządzenia przenośnego w celu dostarczenia przeglądu wiersza pobrania
description: W tym temacie wyjaśniono, jak zdefiniować, kiedy lista wszystkich wierszy pracy będzie pokazywana pracownikom magazynu przetwarzającym prace magazynowe na urządzeniu mobilnym. Ta funkcja może być przydatna dla pracowników magazynu, którzy często wymagają przeglądu wierszy pobierania w zleceniu pracy, aby mogli zoptymalizować swoją kolejność kompletacji.
author: MarkusFogelberg
manager: tfehr
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 433ed2152c47dbe698a640b099cb34727fe63452
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989700"
---
# <a name="set-up-a-mobile-device-menu-item-to-provide-a-pick-line-overview"></a>Skonfiguruj element menu urządzenia przenośnego w celu dostarczenia przeglądu wiersza pobrania

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie opisano sposób konfigurowania opcji związanych z przeglądem wiersza pobrania dla elementów menu urządzeń przenośnych, które są używane do przetwarzania pracy pobrania. Przegląd wiersza pobrania umożliwia pracownikom magazynu przeglądanie i wybieranie z listy wszystkich wierszy pracy związanych z ich bieżącym zadaniem. Ta możliwość może pomóc pracownikom w optymalizacji kolejności pobierania. Funkcja ta obejmuje opcje, które zastępują standardowy przycisk **Pomiń**, który pozwala pracownikom kolejno przechodzić kolejno między wierszami, w stałym zamówieniu. (Opcja używania tego przycisku jest jednak nadal dostępna.)

Administratorzy mogą oddzielnie konfigurować poszczególne elementy menu, aby kontrolować sposób, kiedy i w jakiej aplikacji magazynu jest wyświetlany przegląd wierszy pobrania.

## <a name="turn-on-the-work-pick-line-overview-feature"></a>Włącz funkcję Przegląd wiersza wyboru pracy

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** _Zarządzanie magazynem_
- **Nazwa funkcji:** _Przegląd wiersza wyboru pracy_

## <a name="configure-menu-items-to-show-a-list-of-all-work-lines"></a>Skonfiguruj elementy menu w celu wyświetlenia listy wszystkich wierszy pracy

Aby skonfigurować element menu urządzenia przenośnego w celu zapewnienia przeglądu linii pobrania, wykonaj następujące kroki.

1. Przejdź do pozycji **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego**.
1. Służy do wybierania lub tworzenia elementu menu związanego z pracą pobrania oraz ustawiania następujących wartości:

    - **Tryb:** *Praca*
    - **Używanie istniejącej pracy:** *Tak*
    - **Zarządzane przez:** *Sterowane przez użytkownika* lub *Sterowane przez system*

    Aby uzyskać więcej informacji na temat tworzenia elementów menu i korzystania z różnych ustawień dostępnych na stronie **Elementy menu urządzeń przenośnych**, zapoznaj się z tematem [Konfigurowanie urządzeń przenośnych do pracy w magazynie](configure-mobile-devices-warehouse.md).

1. Na karcie skróconej **Ogólne** skonfiguruj funkcję, ustawiając wartość pola **Pokaż listę wierszy pracy** na jedną z następujących wartości:

    - **Pokaż tylko w przypadku żądania** — pracownicy mogą wyświetlić listę wierszy pobrania, wybierając przycisk **Przejdź do** w aplikacji magazynu.
    - **Pokazuje listę na początku każdego pobrania** — umożliwia wyświetlenie listy za każdym razem po rozpoczęciu lub zakończeniu wiersza pobrania. Można również ponownie wyświetlić listę, wybierając przycisk **Przejdź do** w aplikacji magazynu.
    - **Pokaż tylko na początku pierwszego pobrania** – Pracownicy widzą listę za każdym razem, gdy rozpoczynają nową pracę pobrania, ale nie po każdym wierszu. Można również ponownie wyświetlić listę, wybierając przycisk **Przejdź do** w aplikacji magazynu.
    - **Nigdy nie pokazuj** — w aplikacji magazynowej pojawia się standardowy przycisk **Pomiń**, a wyświetlanie listy wierszy pracy jest wyłączone. Przycisk **Pomiń** umożliwia pracownikom przechodzenie między wierszami pojedynczo w ustalonej kolejności. Mogą również przewijać listę tyle razy, ile potrzebują, aż wszystkie wiersze zostaną przetworzone.

1. Na okienku akcji wybierz opcję **Zapisz**.

    Jeśli pole **Pokaż listę wierszy pracy** zostanie ustawione na dowolną inną wartość niż *Nigdy nie pokazuj*, będzie dostępny przycisk **Lista pól** w okienku akcji.

1. W okienku akcji wybierz opcję **Lista pól**.
1. Na stronie **Lista pól** skonfiguruj informacje, które aplikacja magazynu będzie wyświetlać dla każdego wiersza na liście.

    - Pole **Kontrolka główna** zawsze ma wartość *LineNum*. Dlatego każdy wiersz na liście rozpoczyna się od numeru wiersza.
    - W razie konieczności można skorzystać z pozostałych pól **Pole wyświetlane** w celu dodania do siedmiu dodatkowych pól wyświetlania. W każdym polu **Pole wyświetlane** wybierz nazwę pola wiersza pracy. W każdym wierszu zostanie wyświetlona wartość tego pola. Wartości będą wyświetlane w kolejności wybranej w tym miejscu. Niektóre pola **Pole wyświetlane** mogą pozostać puste, jeśli nie są wymagane wszystkie siedem wartości.

1. W okienku akcji wybierz opcję **Zapisz**, a następnie zamknij stronę **Lista pól**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]