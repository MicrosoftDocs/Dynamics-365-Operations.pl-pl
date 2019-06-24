---
title: Raporty wydatków w nowej wersji
description: Ten temat zawiera informacje dotyczące przeprojektowanego mechanizmu wprowadzania raportu z wydatków w Microsoft Dynamics 365 for Finance and Operations. Nowa procedura upraszcza proces uzupełniania raportów z wydatków i skraca czas ich przygotowania.
author: ryansandness
manager: AnnBe
ms.date: 05/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2019-6-30
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: c7a2b95456e812970b135d83f0f7e503310ce185
ms.sourcegitcommit: 97ed74889a09ef385f6ecbab69e84a05ff42ee41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/20/2019
ms.locfileid: "1592644"
---
# <a name="expense-reports-reimagined"></a>Raporty wydatków w nowej wersji

[!include[banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Wprowadzanie raportu z wydatków służy do uproszczenia wykonywania raportów z wydatków i skrócenia czasu tego procesu. Oto główne elementy nowego zarządzania wydatkami:

- Nowy obszar roboczy zarządzania wydatkami, który pozwala uzyskać dostęp do wydatków dotyczących danego pracownika delegowanego.
- Nowy proces obsługi paragonów, aby lepiej pokazać paragony na poziomie nagłówka i uprościć proces dołączania paragonów do wierszy wydatków.
- Nowa siatka tylko do odczytu, która umożliwia wyświetlanie większej liczby wierszy wydatków i dodatkowych kolumn danych. Teraz można wyświetlić wszystkie wyszczególnione i podzielone wiersze wraz z ich wydatkami nadrzędnymi.
- Uproszczone okienko do edycji wydatków
- Przeprojektowane komunikaty o błędach, ostrzeżeniach i zasadach ułatwiające zagwarantowanie, że użytkownik ma poprawny kontekst, aby zrozumieć problem i rozwiązać go. Firma Microsoft usunęła wiele wiadomości, które pojawiały się zanim użytkownicy mieli możliwość wykonania swoich zadań i rozwiązania problemów, takich jak komunikat „Podział na pozycje nieukończony”.
- Nowa strona służąca do określania, które pola są wymagane przez organizację, które pola są opcjonalne i które pola nie powinny być przechwytywane. Ta strona ułatwi zmniejszenie liczby pól, które użytkownicy muszą określić.
- Nowy wygląd i działanie raportów z wydatków— już nie wyglądają tak, jakby były przeznaczone dla pracowników działu księgowości.

Aby włączyć nowe środowisko, należy w obszarze roboczym **zarządzanie funkcjami** włączyć funkcję **Raporty wydatków w nowej wersji**. Po włączeniu tej funkcji są wykonywane następujące akcje:

- Istniejący obszar roboczy wydatków jest zastępowany nowym obszarem roboczym.
- Zostanie dodany nowy element menu widoczności pola wydatków.
- Brak istniejących elementów menu dla raportów z wydatków (istniejąca strona) lub pola raportu wydatków są usuwane.
- Przepływy pracy i wszelkie zatwierdzenia nadal powodują przekierowanie do istniejącej strony raportów z wydatków.

## <a name="getting-started-video-for-new-users"></a>Filmy instruktażowe dla nowych użytkowników

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE2Y7gO]

Film [Obsługa wydatków w programie Dynamics 365 for Finance and Operations](https://youtu.be/Ocy-MsTvEE0) (widoczny powyżej) jest zawarty w [liście odtwarzania Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej w witrynie YouTube.

## <a name="new-features"></a>Nowe funkcje

| Nowa funkcjonalność | Opis |
|---|----|
| Widoczność pola wydatków | Nowa strona konfiguracji pozwala określić, które pola powinny być wyłączone dla organizacji, które pola powinny być wymagane i które pola są zalecane. |
| Pole wymagane | Nowa prosta konfiguracja pozwala wprowadzić niektóre pola wymagane bez konieczności korzystania z zasad ramowych. |
| Pola opcjonalne | Zostanie dodana druga strona dla pól opcjonalnych. W ten sposób pracownicy nie czują się tak, jakby musieli ustawić pola, ale pola są nadal łatwo dostępne. |
| Dodawanie niedołączonych pokwitowań | Możliwość dodawania niedołączonych pokwitowań do raportu z wydatków jest bardziej widoczna z obszaru roboczego i raportu z wydatków. |
| Ulepszone wiadomości | Lepszy wgląd w wiersze wydatków, które mają ostrzeżenia lub błędy. |
| Mniej wiadomości na pasku komunikatów| Zmniejszono liczbę komunikatów dziennika informacyjnego i dołożono starań, by zapobiegać pojawianiu się zduplikowanych wiadomości w wielu przypadkach. |
| Zgrupowane często wykonywane działania | Interfejs został oczyszczony za pomocą dodania nowego przycisku akcji dla większości typowych działań na poziomie wiersza i dodanie przycisku wielokropka (...) dla nagłówka i innych rzadziej wykonywanych działań. |
| Nowy obszar roboczy, aby zwiększyć widoczność | Nowy obszar roboczy ujednolica funkcje i łącza, które umożliwiają użytkownikom przechodzenie do różnych obszarów. |
| Dodawanie istniejących wydatków i paragonów podczas tworzenia wydatków | Podczas tworzenia raportów z wydatków można dodać wszystkie lub wybrane wydatki i paragony. |
| Kalkulator kursu wymiany | Dodano kalkulator kursu wymiany, który umożliwia obliczenie kursu wymiany dla transakcji z wieloma walutami opłacanymi z własnej kieszeni. |
| Zapisywanie i dodawanie nowych wierszy wydatków | Przyciski **Zapisz** i **nowe** są dostępne po wprowadzeniu nowych wydatków, aby pomóc szybko wprowadzić wiersze wydatków. |
| Lepszy wgląd w podzielone wiersze i wiersze dla pozycji | Podzielone wiersze i wiersze dla pozycji są dodawane bezpośrednio do listy wydatków, aby zwiększyć widoczność i pomóc w łatwym ustaleniu, czy istnieją błędy zasad lub inne błędy. |
| Pokaż paragony podczas podziału na pozycje | Paragony będą widoczne podczas podziału na pozycje. |

Początkowe wydanie koncentruje się na scenariuszach wprowadzania wydatków. Każdy scenariusz sprawdzania lub zatwierdzania raportu z wydatków będzie nadal używał istniejącej strony wprowadzania wydatków.

Następujące funkcje są obecne na istniejącej stronie, ale nie są jeszcze dostępne na nowej stronie. Funkcje te zostaną ponownie wprowadzone w kilku następnych wydaniach:

- Zatwierdzenia
- Zatwierdzanie rozrachunków z dostawcami i możliwość edytowania księgowości
- Wiele punktów wejścia
- Integracja wniosku wyjazdowego
- Jednostka danych dla widoczności pola wydatków
- Wprowadzanie wydatków na diety
- Przepływ pracy na poziomie wiersza
- Wsparcie tymczasowej osoby zatwierdzającej
- Zaawansowany podział na pozycje
