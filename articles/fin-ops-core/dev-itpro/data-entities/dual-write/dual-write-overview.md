---
title: Omówienie podwójnego zapisu
description: Ten artykuł zawiera opis podwójnego zapisu, który zapewnia współpracę prawie w czasie rzeczywistym między aplikacjami Customer Engagement a aplikacjami finansowymi i operacyjnymi.
author: RamaKrishnamoorthy
ms.date: 02/06/2020
ms.topic: overview
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 943607a3ef28db11b7bc7805257914117e6ae38c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289647"
---
# <a name="dual-write-overview"></a>Omówienie podwójnego zapisu

[!include [banner](../../includes/banner.md)]





## <a name="what-is-dual-write"></a>Co to jest podwójny zapis?

Podwójny zapis to gotowa infrastruktura umożliwiająca współpracę w czasie rzeczywistym między aplikacjami oferującymi spersonalizowaną obsługę klienta a aplikacjami finansowymi i operacyjnymi. Gdy dane dotyczące odbiorców, produktów, osób i operacji przepływają poza granice aplikacji, wszystkie działy w organizacji zyskują możliwości.

Funkcja podwójnego zapisu zapewnia ściśle powiązaną, dwukierunkową integrację między aplikacjami finansowymi i operacyjnymi Dataverse. Każda zmiana danych w aplikacjach Finanse i Operacje powoduje zapis do Dataverse, a zmiana danych w Dataverse powoduje zapis w aplikacjach finansowych i operacyjnych. Ten zautomatyzowany przepływ danych umożliwia korzystanie ze zintegrowanego środowiska użytkownika w aplikacjach.

![Relacja danych między aplikacjami.](media/dual-write-overview.jpg)

Podwójny zapis ma dwie aspekty: *aspekt infrastruktury* i aspekt *aplikacji*.

### <a name="infrastructure"></a>Infrastruktura

Infrastruktura podwójnego zapisu jest rozszerzalna i niezawodna i obejmuje następujące najważniejsze cechy:

+ Synchroniczne i dwukierunkowe przepływy danych między aplikacjami
+ Synchronizacja, wraz z trybami odtwarzania, wstrzymywania i doganiania, aby wspierać system w trybach online i offline/asynchronicznych.
+ Możliwość synchronizowania danych początkowych między aplikacjami
+ Połączony widok działań i dzienników błędów dla administratorów danych
+ Możliwość konfigurowania niestandardowych alertów i progów oraz subskrybowanie powiadomień
+ Intuicyjny interfejs użytkownika służący do filtrowania i przekształcania
+ Możliwość ustawiania i wyświetlania zależności i relacji tabel
+ Rozszerzalność dla tabel i map standardowych i niestandardowych
+ Niezawodne zarządzanie cyklem życia zasobu
+ Korzystanie z gotowej konfiguracji wstępnej dla nowych odbiorców

### <a name="application"></a>Zgłoszenie

Podwójny zapis tworzy mapowanie między pojęciami w aplikacjach finansowych i operacyjnych koncepcjami w aplikacjach służących do oferowania spersonalizowanej obsługi klienta. Ta integracja obsługuje następujące scenariusze:

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


## <a name="top-reasons-to-use-dual-write"></a>Najważniejsze powody użycia funkcji podwójnego zapisu

Podwójny zapis dostarcza integrację danych między aplikacjami Microsoft Dynamics 365. To niezawodne środowisko łączy szkieletowo i umożliwia różnym aplikacjom biznesowym współdziałanie ze sobą. Oto najważniejsze powody, dla których należy zastosować metodę podwójnego odpisu:

+ Funkcja podwójnego zapisu zapewnia ściśle powiązaną, działającą niemal w czasie rzeczywistym i dwukierunkową integrację między aplikacjami finansowymi i operacyjnymi oraz aplikacjami do obsługi klientów. Taka integracja stanowi Microsoft Dynamics 365 miejsce, gdzie można znaleźć wszystkie rozwiązania biznesowe. Klienci, którzy korzystają z aplikacji Dynamics 365 Finance i Dynamics 365 Supply Chain Management, ale używają rozwiązań innych firm niż Microsoft do zarządzania relacjami z klientami (CRM), przenoszą się do Dynamics 365, aby skorzystać ze wsparcia podwójnego zapisu.
+ Dane pochodzące od odbiorców, produktów, operacji, projektów i Internetu rzeczy (IoT) automatycznie przepływają do Dataverse w ramach podwójnego zapisu. To połączenie jest przydatne w przypadku firm, które interesują się tymi samymi rozszerzeniami Power Platform.
+ Infrastruktura podwójnego zapisywania jest zgodna z zasadą braku kodowania/małej ilości kodowania. Wymagane są minimalne nakłady pracy inżynieryjnej, aby rozszerzyć standardowe mapy od tabeli do tabeli i uwzględnić mapy niestandardowe.
+ Podwójne zapisywanie obsługuje tryb online i tryb offline. Firma Microsoft jest jedyną firmą, która oferuje obsługę trybów online i offline.

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a>Co oznacza podwójny zapis dla programistów i architektów aplikacji do personalizowania obsługi klienta?

Podwójny odpis automatyzuje przepływ danych między aplikacjami finansowymi i operacyjnymi i aplikacjami służącymi do personalizowania obsługi klienta. Podwójny zapis składa się z dwóch rozwiązań AppSource, które są zainstalowane w Dataverse. W rozwiązaniach jest rozszerzany schemat tabeli, wtyczki i przepływy pracy w ramach Dataverse, dzięki czemu można je skalować do rozmiarów ERP. W przypadku pomyślnej implementacji deweloperzy i architekci aplikacji do personalizowania obsługi klienta muszą zrozumieć te zmiany i współpracować z ich odpowiednikami w aplikacjach finansowych i operacyjnych.

Aby utworzyć równość z odpowiednikami aplikacjach finansowych i operacyjnych, system podwójnego zapisu tworzy istotne zmiany w schemacie Dataverse. W przypadku zrozumienia planu można uniknąć przepracowania projektu i dodatkowej pracy w przyszłości.

+ Po zainstalowaniu pakietu podwójnego zapisu AppSource, w ramach Dataverse będą istniały nowe koncepcje, takie jak firma i strona. Te pojęcia pomagają aplikacjom utworzonym w Dataverse, takim jak m.in. Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service oraz Dynamics 365 Field Service, wchodzić w płynną interakcję z aplikacjami finansowymi i operacyjnymi.

+ Działania i uwagi są zunifikowane i rozwinięte, co pozwala na obsługę zarówno C1 (użytkowników systemu), jak i C2 (odbiorców systemu).

+ Aby zapobiec utracie danych podczas przesyłania walut między aplikacjami finansowymi i operacyjnymi i Dataverse, można rozszerzyć liczbę miejsc dziesiętnych w typie danych Waluta dla aplikacji służących do spersonalizowanej obsługi klienta. Funkcja automatycznie tłumaczy istniejące wiersze na nowy stan rozszerzony na warstwie metadanych. W trakcie tego procesu wartość waluty jest tłumaczona na dane dziesiętne, a nie dane pieniężne, a wartość waluty obsługuje do 10 miejsc po przecinku. Ta funkcja jest opcjonalna. Organizacje, które nie potrzebują korzystać z więcej niż 4 miejsc po przecinku, nie muszą jej używać. Aby uzyskać więcej informacji, przejrzyj [migrację danych typu Waluta w systemie podwójnego zapisu](currrency-decimal-places.md).

+ [Efektywność danych](../../dev-tools/date-effectivity.md) zostanie dodana do Dataverse. Będzie obsługiwać przeszłe, obecne i przyszłe dane w tej samej tabeli.

+ [Konwersje jednostek](../../../../supply-chain/pim/tasks/manage-unit-measure.md) produktów są obsługiwane w przypadku produktów, ofert, zamówień i faktur.

Aby uzyskać więcej informacji o nadchodzących zmianach, zapoznaj się z [nowościami lub zmianami dotyczącymi podwójnego zapisu](whats-new-dual-write.md).



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

