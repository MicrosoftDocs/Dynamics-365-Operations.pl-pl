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
ms.openlocfilehash: 1eb5e4ea8d086baeee686ccb3d044b3ef9d2a4fa
ms.sourcegitcommit: b3df62842e62234e8eaa16992375582518976131
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "3818579"
---
# <a name="dual-write-overview"></a>Przegląd o podwójnym zapisie

[!include [banner](../../includes/banner.md)]



## <a name="what-is-dual-write"></a>Co to jest podwójny zapis?

Podwójny zapis to gotowa infrastruktura umożliwiająca współpracę w czasie rzeczywistym między aplikacjami oferującymi spersonalizowaną obsługę klienta a aplikacjami Finance and Operations. Gdy dane dotyczące odbiorców, produktów, osób i operacji przepływają poza granice aplikacji, wszystkie działy w organizacji zyskują możliwości.

Podwójny zapis to ściśle sprzężona i dwukierunkowa integracja między aplikacjami Finance and Operations i Common Data Service. Każda zmiana danych w aplikacjach Finance and Operations powoduje zapis do Common Data Service, a zmiana danych w Common Data Service powoduje zapis w aplikacjach Finance and Operations. Ten zautomatyzowany przepływ danych umożliwia korzystanie ze zintegrowanego środowiska użytkownika w aplikacjach.

![Relacja danych między aplikacjami](media/dual-write-overview.jpg)

Podwójny zapis ma dwie aspekty: *aspekt infrastruktury* i aspekt *aplikacji*.

### <a name="infrastructure"></a>Infrastruktura

Infrastruktura podwójnego zapisu jest rozszerzalna i niezawodna i obejmuje następujące najważniejsze cechy:

+ Synchroniczne i dwukierunkowe przepływy danych między aplikacjami
+ Synchronizacja, wraz z trybami odtwarzania, wstrzymywania i doganiania, aby wspierać system w trybach online i offline/asynchronicznych.
+ Możliwość synchronizowania danych początkowych między aplikacjami
+ Połączony widok działań i dzienników błędów dla administratorów danych
+ Możliwość konfigurowania niestandardowych alertów i progów oraz subskrybowanie powiadomień
+ Intuicyjny interfejs użytkownika służący do filtrowania i przekształcania
+ Możliwość ustawiania i wyświetlania zależności i relacji jednostek
+ Rozszerzalność dla jednostek i map standardowych i niestandardowych
+ Niezawodne zarządzanie cyklem życia zasobu
+ Korzystanie z gotowej konfiguracji wstępnej dla nowych odbiorców

### <a name="application"></a>Zgłoszenia

Podwójny zapis tworzy mapowanie między pojęciami w aplikacjach Finance and Operations i koncepcjami w aplikacjach służących do oferowania spersonalizowanej obsługi klienta. Ta integracja obsługuje następujące scenariusze:

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
+ Dane pochodzące od odbiorców, produktów, operacji, projektów i Internetu rzeczy (IoT) automatycznie przepływają do Common Data Service w ramach podwójnego zapisu. To połączenie jest przydatne w przypadku firm, które interesują się tymi samymi rozszerzeniami Power Platform.
+ Infrastruktura podwójnego zapisywania jest zgodna z zasadą braku kodowania/małej ilości kodowania. Wymagane są minimalne nakłady pracy inżynieryjnej, aby rozszerzyć standardowe mapy od tabeli do tabeli i uwzględnić mapy niestandardowe.
+ Podwójne zapisywanie obsługuje tryb online i tryb offline. Firma Microsoft jest jedyną firmą, która oferuje obsługę trybów online i offline.

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a>Co oznacza podwójny zapis dla programistów i architektów aplikacji do personalizowania obsługi klienta?

Podwójny odpis automatyzuje przepływ danych między aplikacjami Finance and Operations i aplikacjami służącymi do personalizowania obsługi klienta. Podwójny zapis składa się z dwóch rozwiązań AppSource, które są zainstalowane w Common Data Service. W rozwiązaniach jest rozszerzany schemat encji, wtyczki i przepływy pracy w ramach Common Data Service, dzięki czemu można je skalować do rozmiarów ERP. W przypadku pomyślnej implementacji deweloperzy i architekci aplikacji do personalizowania obsługi klienta muszą zrozumieć te zmiany i współpracować z ich odpowiednikami w aplikacjach Finance and Operations.

Aby utworzyć równość z odpowiednikami aplikacji Finance and Operations, system podwójnego zapisu tworzy istotne zmiany w schemacie Common Data Service. W przypadku zrozumienia planu można uniknąć przepracowania projektu i dodatkowej pracy w przyszłości.

+ Po zainstalowaniu pakietu podwójnego zapisu AppSource, w ramach Common Data Service będą istniały nowe koncepcje, takie jak firma i strona. Te pojęcia pomagają aplikacjom utworzonym w Common Data Service,takim jak m.in. Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service oraz Dynamics 365 Field Service, wchodzić w płynną interakcję z aplikacjami Finance and Operations.

+ Działania i uwagi są zunifikowane i rozwinięte, co pozwala na obsługę zarówno C1 (użytkowników systemu), jak i C2 (odbiorców systemu).

+ Aby zapobiec utracie danych podczas przesyłania walut między aplikacjami Finance and Operations i Common Data Service, można rozszerzyć liczbę miejsc dziesiętnych w typie danych Waluta dla aplikacji służących do spersonalizowanej obsługi klienta. Funkcja automatycznie tłumaczy istniejące rekordy na nowy stan rozszerzony na warstwie metadanych. W trakcie tego procesu wartość waluty jest tłumaczona na dane dziesiętne, a nie dane pieniężne, a wartość waluty obsługuje do 10 miejsc po przecinku. Ta funkcja jest opcjonalna. Organizacje, które nie potrzebują korzystać z więcej niż 4 miejsc po przecinku, nie muszą jej używać. Aby uzyskać więcej informacji, przejrzyj [migrację danych typu Waluta w systemie podwójnego zapisu](currrency-decimal-places.md).

+ [Efektywność danych](../../dev-tools/date-effectivity.md) zostanie dodana do Common Data Service. Będzie obsługiwać przeszłe, obecne i przyszłe dane w tej samej encji.

+ [Konwersje jednostek](../../../../supply-chain/pim/tasks/manage-unit-measure.md) produktów są obsługiwane w przypadku produktów, ofert, zamówień i faktur.

Aby uzyskać więcej informacji o nadchodzących zmianach, zapoznaj się z [nowościami lub zmianami dotyczącymi podwójnego zapisu](whats-new-dual-write.md).

