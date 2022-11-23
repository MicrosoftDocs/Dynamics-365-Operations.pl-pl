---
title: Migawka wiekowania odbiorcy
description: Ten artykuł zawiera informacje o migawkach wiekowania klientów. Migawka wiekowania oblicza salda wiekowe dla grupy klientów w określonym momencie.
author: JodiChristiansen
ms.date: 10/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.17
ms.search.form: ''
ms.openlocfilehash: e4ccc8ac9b5374ca0713167a17b8704727c687fd
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775249"
---
# <a name="customer-aging-snapshots"></a>Migawka wiekowania odbiorcy

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o migawkach wiekowania klientów. Migawka wiekowania oblicza salda wiekowe dla grupy klientów w określonym momencie. Możesz tworzyć przedawnione rekordy migawek albo dla wszystkich klientów, albo dla klientów z puli klientów.

Informacje z migawek wiekowania są wyświetlane na stronie z listą **Wiekowane salda** i na stronie **Windykacja**. Należy utworzyć migawki wiekowania, aby można było używać strony listy **Wiekowane salda**. Strona listy zawiera listę tylko klientów, dla których utworzono migawkę wiekowania.

W obszarze roboczym **Kredyty i windykacja odbiorcy** jest także widać wiekowanie odbiorcy. Aby uzyskać więcej informacji, zobacz temat [Zarządzanie kredytami i windykacjami. Power BI](credit-collections-power-bi.md).

> [!NOTE]
> Aby skrócić czas potrzebny do utworzenia migawki starzenia, włącz następujące funkcje w obszarze roboczym **Zarządzanie funkcjami**. 
> - **Zwiększenie wydajności wiekowania odbiorcy** 
> - **Ulepszenie wydajności wiekowania klientów z pulami klientów**  
>Gdy są włączone obie funkcje, **Pule klientów** mogą być używane podczas tworzenia migawki wiekowania. 

Podczas tworzenia migawki wiekowania odbiorcy można wprowadzić informacje w następujących polach:

- **Definicja okresu wiekowania** – Wybierz definicję okresu wiekowania dla migawki wiekowania. Możesz mieć jedną migawkę wiekowania dla każdej definicji okresu wiekowania. Migawka wiekowania i definicja okresu wiekowania należy utworzyć osobno.
- **Identyfikator puli** – To pole jest opcjonalne. Pula służy do definiowania zestawu odbiorców, którzy mają być przetwarzane w migawki wiekowania. Jeśli wybierzesz pulę klientów w tym polu, migawka wiekowania jest tworzona tylko dla kont klientów, które są częścią tej puli klientów. Wybrana pula odbiorców musi być typu **Migawka wiekowania**. Jeśli pozostawisz to pole puste, migawka wiekowania zostanie utworzona dla wszystkich kont klientów.


- **Kryteria** — migawka wiekowania jest wiekujna na podstawie wybranej daty:

    - **Datę transakcji** — Każda transakcja jest przedawniona na podstawie jej daty transakcji.
    - **Data wymagalności** — Każda transakcja jest przedawniona na podstawie jej terminu płatności.
    - **Data dokumentu** — Każda transakcja jest przedawniona na podstawie daty jej dokumentu.

- **Wiekowanie na dzień** – Umożliwia wybranie daty w polu **Bieżącej daty** dla migawki wiekowania. Okresy wiekowania są obliczane na podstawie tej daty. 

    - **Data dzisiejsza** — Używanie daty systemowej. Wybierz tę opcję, jeśli skonfigurowano przetwarzanie w serii cyklicznej. Następnie przy każdym uruchomieniu zadania wsadowego używana jest data systemowa tej uruchomienia.
    - **Wybrana data** — Używanie określonej przez siebie daty. Jeśli zostanie wybrana ta opcja, należy również wprowadzić datę wiekowania.

   Na przykład bieżący okres wiekowania wynosi 30 dni. Jeśli w tym polu zostanie zaznaczyna **data Dzisiejsza**, bieżący okres wiekowania rozpoczyna się od daty dzisiejszej, a następnie obejmuje poprzednie 29 dni. Jeśli w tym polu zostanie zaznaczyna **Wybrana data** i wprowadzisz datę, bieżący okres przedawnienia rozpocznie się w określonym dniu i obejmie poprzednie 29 dni.

- **Aktualizuj stan windykacji** – Ustaw tę opcję na Wartość **Tak**, aby zaktualizować stan windykacji transakcji na stronie **Windykacja** z **Przyrzekanie do zapłaty** na **Złamane**, jeśli data wiekowania jest późniejsza niż data w polu **Przyrzeczone do zapłaty**. Ustaw tę opcję **na wartość Nie**, aby pozostawić stan kolekcji niezmieniony na stronie **Windykacja**.
- **Uwzględnij odbiorców z zerowym saldem** – Ustaw dla tej opcji wartość **Tak**, aby uwzględnić wszystkich odbiorców, niezależnie od ich salda. Jeśli uwzględnieni są wszyscy klienci, zalecamy włączenie obu funkcji **Zwiększenie wydajności wiekowania odbiorcy** i **Ulepszenie wydajności wiekowania klientów z pulami klientów**. Ustaw dla tej opcji wartość **Nie**, aby uwzględnić tylko odbiorców z saldem. To ustawienie pomoże przyspieszyć wydajność, ponieważ odbiorcy, którzy nie mają salda, są pomijani.
- **Pomiń obliczanie limitu kredytu podczas wiekowania** — jeśli ta opcja ma wartość **Tak**, proces wiekowania nie obliczy ponownie kwoty **Sumy częściowej dokumentu dostawy**, kwoty **Sumy częściowej otwartego zamówienia** i **Kredytu dostępnego** dla każdego klienta. Te salda są pokazywane na stronie **Salda wiekowe** w polach informacji w obszarze **Limit kredytu**. Aby przyspieszyć wydajność w procesie wiekowania, ustaw tę opcję na wartość **Tak**. Ustaw dla tej właściwości wartość **Nie**, aby ponownie przeliczać salda podczas uruchamiania procesu wiekowania. 
- **Zakres firm** — na karcie **Zakres firmy** wybierz firmy, które mają być dołączane w migawki wiekowania. Do wyboru są tylko firmy, dla których ustawiono płatności scentralizowane. Transakcje z wybranych firm są następnie uwzględniane w okresach wiekowania dla odbiorców, którzy mają ten sam identyfikator jednostki we wszystkich tych firmach. Kwoty w walutach są konwertowane na walutę firmy, do której jesteś zalogowany, podczas tworzenia migawki wiekowania.

Zaleca się zaplanowanie tego procesu do uruchomienia w partii.

> [!NOTE]
> Aby zwiększyć wydajność partii podczas tworzenia migawki wiekowania, wprowadź liczbę w polu **Maksymalna liczba zadań wsadowych** na skróconej karcie **Ustawienia domyślne** windykacji na karcie **Windykacja** na stronie **Parametry rozrachunków z odbiorcami**. Zaleca się, aby w polu **Wiekuj salda odbiorcy** rozpocząć od wartości między **12** i **20**, a następnie skorygować tę wartość, aby zoptymalizować przetwarzanie zgodnie z sytuacją. Nie zaleca się ustawiania tej wartości większej niż **30**, ponieważ będzie to miało wpływ na wydajność. 

