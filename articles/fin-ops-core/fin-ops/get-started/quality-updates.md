---
title: Aktywne aktualizacje jakości
description: Ten artykuł zawiera informacje dotyczące aktywnego dostarczania aktualizacji jakości.
author: rashmansur
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 9d81cb15e9a127e7bea7ad9b5e0f50a1ee543f71
ms.sourcegitcommit: 78e85ad49634cd31459fdb7325cb273352bf1501
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9338145"
---
# <a name="proactive-quality-updates"></a>Aktywne aktualizacje jakości

[!include[banner](../includes/banner.md)]

W ciągu ostatnich kilku lat firma Microsoft dokonała ciągłych postępów, które nazywamy [One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md). Przesłanie One Version jest proste: im bliżej tego, że możemy mieć wszystkich odbiorców w tej samej wersji oprogramowania, tym wyższa jakość, którą możemy dostarczyć. Znajdujemy i rozwiązujemy problemy jeden raz, a potem szybko dostarczmy te rozwiązania klientom.

To założenie jest potwierdzone przez wyniki: mniejsza liczba problemów w naszych produktach. Jeśli odbiorcy nie używają tej samej wersji, ciągle widzimy, że napotykają na problemy, na które dostępne jest już rozwiązanie. Już poczyniliśmy duże postępy w zakresie Dynamics 365 Finance, Dynamics 365 Supply Chain, Dynamics 365 Project Operations i Dynamics 365 Commerce, dzięki najnowszym postępom technicznym, teraz można przejść do następnego kroku. Poniższe informacje informują, co zamierzamy zrobić, co zostało już wykonane, aby ustawić ten etap oraz w jaki sposób i w jakim czasie wprowadzamy nowe możliwości bez przerw.

## <a name="focus-on-quality-updates"></a>Skupienie się na aktualizacjach jakości

Obecnie dostarczamy siedem [aktualizacji usług](public-preview-releases.md) rocznie. Na przykład wersja 10.0.29 jest aktualizacją usługi. Do tego czasu było osiem aktualizacji rocznie. Jednak jedna aktualizacja została porzucona w odpowiedzi na opinię klienta, która ujawniła żądanie, aby uniknąć zmian pod koniec roku kalendarzowego.

Nie będzie można zmieniać kadencji aktualizacji usługi. Zamiast tego, następny krok w przód w ramach procesu One Version będzie dotyczył *aktualizacji jakości*. Aktualizacje jakości to zbiorcze kompilacje poprawek. Nie zawierają nowych funkcji. W dowolnym czasie cała nasza społeczność odbiorców jest rozłożona na trzy lub cztery ostatnie aktualizacje usług. Jednak w przypadku dowolnej aktualizacji usługi w grupie można używać kilkadziesiąt różnych wersji aktualizacji jakości, w zależności od dat wdrażania. W następnym kroku aktywnie rozsyłamy aktualizacje jakości. Już korzystamy z tego modelu w przypadku aplikacji opartych na naszych systemach Dataverse i widzimy oczekiwane wyniki poprawy jakości i zmniejszenia zdarzeń pomocy technicznej.

Zmniejszenie wad może oczywiście zmniejszyć lub całkowicie wyeliminować aktualizacje jakości. W uaktualnianych standardach systemu istnieje wiele inicjatyw mających na celu ograniczenie wad wymagających aktualizacji jakości. Nawet jeśli w ramach aktualizacji jakości zostaną zredukowane obciążenia, spójność bazy klientów poprawi obsługę, szybciej uzyskają usprawnienia i zmniejszy się częstotliwość napotykania na problemy przez klientów, dla których istnieją już rozwiązania.

## <a name="making-proactive-distribution-possible"></a>Tworzenie aktywnej dystrybucji

Wdrożono już wiele postępów umożliwiających prewencyjne dostarczanie aktualizacji jakości:

- **Aktualizowanie blisko zerowego przestoju** — aby wypychać częściej środowiska, konieczne jest zmniejszenie wpływu na dostępność środowiska w celu zachowania umów dotyczących poziomu usług (SLA) usługi Dynamics 365. Aktualizacja blisko zerowego przestoju pierwotnie została wprowadzona, aby pomóc ulepszyć miesięczne poprawianie systemu operacyjnego poprzez zastosowanie trybu failover klastra w celu uaktywnienia zaktualizowanego obrazu z minimalnym przerwaniem. Mechanizm stosowania aktualizacji jest ulepszony, dzięki czemu jeszcze mniej destruktywny i obejmuje zarówno poprawianie systemu operacyjnego, jak i wdrażanie aktualizacji jakości.

    W przypadku interakcyjnych użytkowników aktywna sesja może zostać przerwana, a ponowienie próby zostanie ponowione w środowisku, które zostało teraz zaktualizowane. Dzięki wprowadzeniu [planowania partii opartego na priorytecie](../../dev-itpro/sysadmin/priority-based-batch-scheduling.md), które jest obecnie dostępne od razu po aktualizacji, planowanie i przetwarzanie wsadowe odzyska i wznowi działanie natychmiast po aktualizacji. Planowanie wsadowe oparte na priorytecie zostanie oparte na priorytetach, zanim odbiorcy zaczną uczestniczyć w prewencyjnej dystrybucji aktualizacji jakości w swoich środowiskach produkcyjnych.

- **Godziny bezczynności** — są zdefiniowane godziny bezczynności dla każdego regionu Azure, a w trakcie tej godziny występują blisko zerowe aktualizacje przestojów.

## <a name="the-proactive-update-process"></a>Proces aktywnej aktualizacji

Wdrażanie aktywnej aktualizacji jakości będzie zgodne z procesem wdrażania w bezpieczny sposób (SDP). Szczegółowe informacje kodu SDP będą się rozwijać, ale aktualizacje jakości zostaną początkowo wdrożone w środowiskach piaskownicy. Proces rozpocznie się od środowisk, które decydują się na wcześniejsze wdrożenie. Wraz ze wzrostem procentu pomyślnie wdrożonej piaskownicy rozpoczyna się wdrażanie w środowiskach produkcyjnych. Przypominamy, proces rozpocznie się od środowisk, które decydują się na wcześniejsze wdrożenie. W systemach nasłuchiwania system będzie monitorować telemetrię systemu i zdarzenia w aktywnych witrynach, a w przypadku wykrycia jakiegokolwiek zdarzenia spowoduje to zatrzymanie rozsyłania określonej wersji. Odbiorcy nadal będą mogli ściągać aktualizacje jakości przed prewencyjnym wdrożeniem, jeśli będą potrzebne.

Z aktualnych danych zarządzania wydaniami wynika, że w aktualizacjach jakości jest wprowadzonych mniej niż 3% cofnięć. Większy nacisk na eliminację zmian oraz rozszerzony protokół SDP spowoduje, że potencjalny wpływ cofnięć będzie znacznie niższy niż wzrost jakości osiągnięty dzięki większej możliwości szybkiego wdrażania poprawek dla odbiorców.

## <a name="process-changes"></a>Przetwórz zmiany

Zestaw zmian procesów jest implementowany przed aktywacją wdrożenia aktywnej aktualizacji jakości:

- **Schemat** — narzędzie zapewnia, że kompilacje aktualizacji jakości obejmują tylko zmiany schematów, które można zastosować w trybie online usługi. To podejście pomoże zachować możliwość stosowania aktualizacji przy użyciu przestoju najbliższego zera.
- **Zwiększona obserwacja zmian** — obecnie istnieje już dodatkowy krok procesu zatwierdzania zmian uwzględnianych w aktualizacji jakości. Ograniczenie w dodatkowym kroku zostanie zwiększone, aby zmniejszyć ryzyko cofnięć. Zmiany powodujące niezgodność nie są dozwolone w aktualizacjach jakości, a zwiększona obserwacja zmian pomaga zapewnić, że osiągamy ten cel.
- **Widoczność** — powiadomimy za pośrednictwem poczty e-mail i usługi Lifecycle Services (LCS) o zbliżających się aktywnych aktualizacjach jakości. Ponadto zespoły pomocy technicznej i informacje dotyczące zdarzeń mają wgląd w możliwości aktywnego wdrażania aktualizacji jakości.
- **Powrót do poprzedniej wersji** – dystrybucja testowa zostanie użyta do grupowania wszystkich zmian w aktywnej aktualizacji jakości. Jeśli po aktywnym wdrożeniu konieczny jest powrót do poprzedniej wersji, można tego dokonać za pomocą dystrybucji testowej.
- **Wyznaczenie synchronizacji piaskownicy** — poniżej 20% odbiorców ma obecnie wiele piaskownic i jedna piaskownica jest wdrożona tam, gdzie wersja odpowiada wersji produkcyjnej, co pomaga w rozwiązywaniu problemów. W najbliższej przyszłości wprowadzimy możliwość określania środowiska piaskownicy, w którym klienci nie powinni otrzymywać wdrożenia aktywnej aktualizacji jakości wraz z innymi piaskownicami, ale powinni je otrzymać później, wraz ze środowiskiem produkcyjnym. Jeśli klient używa piaskownicy do testowania nowszej wersji niż w wersji produkcyjnej, ta piaskownica będzie otrzymywać aktualizacje jakości w nowszej wersji.
- 
## <a name="when-will-proactive-quality-updates-start"></a>Kiedy rozpoczną się aktywne aktualizacje jakości?

Dystrybucję aktywnych aktualizacji jakości dla środowisk piaskownicy można rozpocząć pod koniec września lub października 2022 dla odbiorców w chmurze publicznej Azure. Środowiska w wersji próbnej również rozpoczną otrzymywanie wdrożenia aktywnej aktualizacji w tym czasie. We wrześniu do każdego klienta zostanie wysłane powiadomienie, aby poinformować go o oczekiwanym harmonogramie dla swojego środowiska. Wyjątki w procesie aktywnej aktualizacji dystrybucji będą dozwolone tylko dla odbiorców podlegających regulacjom z FDA. Nadal pracujemy nad zarządzaniem środowiskami regulowanymi oraz ich odbiorców w chmurze rządowej.

W ciągu następnych sześciu miesięcy będziemy stopniowo zwiększać wartość procentową środowisk piaskownicy, które otrzymują aktywne aktualizacje, dopóki nie zostaną uwzględnione wszystkie wskazane środowiska i nie rozpoczniemy aktualizowania środowisk produkcyjnych. Przez cały okres będziemy monitorować, aby zagwarantować, że proces wdrażania będzie bezproblemowy i że możemy ponownie osiągnąć cel, który nie przerwie obciążeń.

Ponieważ odbiorcy będą regularnie obierać mniejsze obciążenia, oczekujemy, że bieżący proces będzie prostszy. Dostosujemy częstotliwość wdrażania aktualizacji, ponieważ wykazujemy możliwość uruchamiania procesu bez przerwy. Ten proces działa już efektywnie w naszej platformie Dataverse i aplikacjach oraz dostarcza przewidywanych usprawnień jakości usług. Planujemy podjęcie tego samego kroku w przypadku aplikacji finansowych i operacyjnych.
