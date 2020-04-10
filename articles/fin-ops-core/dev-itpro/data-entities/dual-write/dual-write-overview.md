---
title: Przegląd o podwójnym zapisie
description: Ten temat stanowi omówienie podwójnego zapisu. Podwójny zapis to infrastruktura umożliwiająca współpracę w czasie rzeczywistym między aplikacjami opartymi na modelach Microsoft Dynamics 365 i aplikacjami Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 64626ebdd7fbad3d47a4b4c6bbc45bf3bc0c8277
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172791"
---
# <a name="dual-write-overview"></a>Przegląd o podwójnym zapisie

[!include [banner](../../includes/banner.md)]



## <a name="what-is-dual-write"></a>Co to jest podwójny zapis?

Podwójny zapis to gotowa infrastruktura umożliwiająca współpracę w czasie rzeczywistym między aplikacjami opartymi na modelach Microsoft Dynamics 365 i aplikacjami Finance and Operations. Gdy dane dotyczące odbiorców, produktów, osób i operacji przepływają poza granice aplikacji, wszystkie działy w organizacji zyskują możliwości.

Podwójny zapis to ściśle sprzężona i dwukierunkowa integracja między aplikacjami Finance and Operations i Common Data Service. Każda zmiana danych w aplikacjach Finance and Operations powoduje zapis do Common Data Service, a zmiana danych w Common Data Service powoduje zapis w aplikacjach Finance and Operations. Ten zautomatyzowany przepływ danych umożliwia korzystanie ze zintegrowanego środowiska użytkownika w aplikacjach.

![Relacja danych między aplikacjami](media/dual-write-overview.jpg)

Podwójny zapis ma dwie aspekty: *aspekt infrastruktury* i aspekt *aplikacji*.

### <a name="infrastructure"></a>Infrastruktura

Infrastruktura podwójnego zapisu jest rozszerzalna i niezawodna i obejmuje następujące najważniejsze cechy:

+ Synchroniczne i dwukierunkowe przepływy danych między aplikacjami
+ Synchronizacja, wraz z trybami odtwarzania, wstrzymywania i doganiania, aby wspierać system w trybach online i offline/asynchronicznych.
+ Możliwość synchronizowania danych początkowych między aplikacjami
+ Skonsolidowany widok działań i dzienników błędów dla administratorów danych
+ Możliwość konfigurowania niestandardowych alertów i progów oraz subskrybowanie powiadomień
+ Intuicyjny interfejs użytkownika służący do filtrowania i przekształcania
+ Możliwość ustawiania i wyświetlania zależności i relacji jednostek
+ Rozszerzalność dla jednostek i map standardowych i niestandardowych
+ Niezawodne zarządzanie cyklem życia zasobu
+ Korzystanie z gotowej konfiguracji wstępnej dla nowych odbiorców

### <a name="application"></a>Zgłoszenia

Podwójny zapis tworzy mapowanie między pojęciami w aplikacjach Finance and Operations i koncepcjami w aplikacjach opartych na modelach w Dynamics 365. Ta integracja obsługuje następujące scenariusze:

+ Zintegrowane dane główne odbiorcy
+ Dostęp do kart lojalnościowych odbiorcy i punktów lojalnościowych
+ Ujednolicone doświadczenie w zakresie opanowania produktu
+ Świadomość hierarchii organizacyjnej
+ Zintegrowane dane główne dostawcy
+ Dostęp do danych finansowych i danych referencyjnych podatku
+ Doświadczenie aparatu cen na żądanie
+ Zintegrowane doświadczenia Od prospekta do środków pieniężnych
+ Zdolność do obsługi zarówno zasobów wewnętrznych, jak i aktywów dla odbiorców za pomocą agentów pól
+ Zintegrowane korzystanie z funkcji od zapotrzebowania do płatności
+ Zintegrowane działania i uwagi dotyczące danych i dokumentów odbiorców
+ Możliwość wyszukiwania dostępnych zapasów i szczegółów
+ Edytuj doświadczenie Od projektu do środków pieniężnych
+ Możliwość obsługi wielu adresów i ról za pośrednictwem koncepcji strony
+ Zarządzanie pojedynczym źródłem danych dla użytkowników
+ Zintegrowane kanały do sprzedaży detalicznej i marketingu
+ Widoczność dla promocji i rabatów
+ Funkcje Od żądania do usługi
+ Usprawnione operacje usług

## <a name="top-reasons-to-use-dual-write"></a>Najważniejsze powody użycia funkcji podwójnego zapisu

Podwójny zapis dostarcza integrację danych między aplikacjami Microsoft Dynamics 365. To niezawodne środowisko łączy szkieletowo i umożliwia różnym aplikacjom biznesowym współdziałanie ze sobą. Oto najważniejsze powody, dla których należy zastosować metodę podwójnego odpisu:

+ Podwójny zapis umożliwia ścisłą integrację między aplikacjami Finance and Operations a aplikacjami opartymi na modelach w Dynamics 365. Taka integracja stanowi Microsoft Dynamics 365 miejsce, gdzie można znaleźć wszystkie rozwiązania biznesowe. Klienci, którzy korzystają z Dynamics 365 Finance i Dynamics 365 Supply Chain Management, ale używają rozwiązań innych firm niż Microsoft do zarządzania relacjami z klientami (CRM), przenoszą się do Dynamics 365, aby skorzystać ze wsparcia podwójnego zapisu.
+ Dane pochodzące od odbiorców, produktów, operacji, projektów i Internetu rzeczy (IoT) automatycznie przepływają do Common Data Service w ramach podwójnego zapisu. To połączenie jest bardzo przydatne w przypadku firm, które interesują się tymi samymi rozszerzeniami Microsoft Power Platform.
+ Infrastruktura podwójnego zapisywania jest zgodna z zasadą braku kodowania/małej ilości kodowania. Wymagane są minimalne nakłady pracy inżynieryjnej, aby rozszerzyć standardowe mapy od tabeli do tabeli i uwzględnić mapy niestandardowe.
+ Podwójne zapisywanie obsługuje tryb online i tryb offline. Firma Microsoft jest jedyną firmą, która oferuje obsługę trybów online i offline.

## <a name="what-does-dual-write-mean-for-users-and-architects-of-crm-products"></a>Co podwójny zapis oznacza dla użytkowników i architektów produktów CRM?

Podwójny odpis automatyzuje przepływ danych między aplikacjami Finance and Operations i Common Data Service. W przyszłych wersjach, koncepty w aplikacjach opartych na modelach w Dynamics 365 (np. odbiorca, kontakt, oferta i zamówienie) będą skalowane do odbiorców rynków średnich i wyższych średnich.

W pierwszym wydaniu większość automatyzacji jest obsługiwana przez rozwiązania podwójnego zapisu. W przyszłych wersjach te rozwiązania staną się częścią Common Data Service. Przez poznanie nadchodzących zmian w długim okresie w Common Data Service, można zaoszczędzić wiele nakładów pracy. Oto niektóre z kluczowych zmian:

+ Common Data Service ma nowe koncepcje, np. firmę i stronę. Te koncepcje mają wpływ na wszystkie aplikacje, które są zbudowane na Common Data Service, takie jak Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service i Dynamics 365 Field Service.
+ Działania i uwagi są zunifikowane i rozwinięte, co pozwala na obsługę zarówno C1 (użytkowników systemu), jak i C2 (odbiorców systemu).
+ Oto niektóre z nadchodzących zmian w Common Data Service:

    - Typ danych dziesiętnych zastąpi typ danych pieniężnych.
    - Obowiązywanie dat będzie obsługiwać przeszłe, obecne i przyszłe dane w tym samym miejscu.
    - Obsługa waluty i kursów wymiany będzie bardziej pomocna, a interfejs (API) programowania aplikacji **Kursu wymiany** zostanie poprawiony.
    - Konwersje jednostek będą obsługiwane.

Aby uzyskać więcej informacji o nadchodzących zmianach, zapoznaj się z tematem [Dane w Common Data Service – faza 1 i 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/finance-operations-crossapp-capabilities/data-common-data-service-phase-1).
