---
title: Infrastruktura Dynamics 365 Human Resources – często zadawane pytania
description: Ten artykuł zawiera odpowiedzi na często zadawane pytania dotyczące scalania infrastruktury dla aplikacji Microsoft Dynamics 365 Human Resources i w aplikacjach finansowych i operacyjnych.
author: twheeloc
ms.date: 11/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7325231718d7387450391b16b2866f9a2c05bdc4
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779643"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>Infrastruktura Dynamics 365 Human Resources – często zadawane pytania

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="what-is-dynamics-365-human-resources"></a>Co to jest usługa Dynamics 365 Human Resources?

Microsoft Dynamics 365 Human Resources zapewnia narzędzia, które pomagają zespołom HR zwiększyć sprawność organizacyjną, przekształcić doświadczenia pracowników i zoptymalizować programy HR, aby stworzyć miejsce pracy, w którym ludzie i firma mogą się rozwijać. Aby dowiedzieć się więcej o Dynamics 365 Human Resources, zobacz [Dynamics 365 Human Resources](https://dynamics.microsoft.com/human-resources/overview/).

- **Przekształć doświadczenia pracowników.** Zatrzymaj najlepszych pracowników, umożliwiając menedżerom i pracownikom korzystanie z samoobsługowych rozwiązań, które zwiększają zaangażowanie i rozwój.
- **Optymalizacja programów HR.** Zmniejsz koszty operacyjne i stwórz zorientowane na ludzi programy zarządzania urlopami i nieobecnościami, czasem, świadczeniami i wynagrodzeniami.
- **Zwiększanie sprawności organizacyjnej.** Umożliwić HR działanie ze sprawnością, jakiej wymaga biznes, wykorzystując Dataverse i Microsoft Power Platform do centralizacji danych o ludziach i łatwego rozszerzania Dynamics 365 Human Resources.
- **Odkryj wiedzę o pracownikach.** Podejmuj decyzje na podstawie danych, dzięki możliwości analizowania i wizualizacji danych o ludziach na bogatych pulpitach, dostępnych na każdym urządzeniu.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>Wartość i korzyści związane z fuzją infrastruktury

### <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>Co to jest scalanie infrastruktury Dynamics 365 Human Resources?

Obecnie w Dynamics 365 istnieją dwa oddzielne zestawy funkcji HR na dwóch różnych infrastrukturach:

- **Dynamics 365 Human Resources**— Samodzielna aplikacja, która działa na niezależnej infrastrukturze. Po uruchomieniu tej aplikacji infrastruktura została oddzielona od innych aplikacji operacyjnych Dynamics 365. Nasi klienci używają tej aplikacji, aby zwiększyć sprawność organizacyjną, zoptymalizować programy HR, zmienić doświadczenia pracowników i uzyskać wgląd w ich pracę.
- **Moduł HR** - Starszy zestaw funkcji, który był wcześniej częścią licencjonowania Unified Operations (SKU). Moduł HR działa na infrastrukturze aplikacji finansowych i operacyjnych, która jest taka sama we wszystkich aplikacjach operacyjnych. Do tych aplikacji należą: Dynamics 365 Finance, Dynamics 365 Project Operations i Dynamics 365 Supply Chain Management. Klienci otrzymali funkcje HR jako część Dynamics 365 Finance lub Dynamics 365 Supply Chain Management.

W ciągu ostatnich trzech lat firma Microsoft nie dodała żadnych nowych możliwości ani ulepszeń do modułu HR. Zamiast tego nasze inwestycje na mapie drogowej skupiły się na aplikacji Dynamics 365 Human Resources.

Wprowadzając te dwa zestawy możliwości do tej samej infrastruktury, pomożemy klientom uzyskać następujące korzyści:

- Ulepszenia, które zostały dodane do Dynamics 365 Human Resources w ciągu ostatnich trzech lat, w tym udoskonalone urlopy i nieobecności, zarządzanie świadczeniami i raportowanie.
- Większa rozciągliwość dzięki Microsoft Power Platform i możliwość rozszerzenia logiki biznesowej w celu personalizacji stron.
- Ulepszone wdrażanie, aktualizacje i utrzymanie, które są spójne pod względem zarządzania cyklem życia aplikacji (ALM), usług cyklu życia, dostępności geograficznej i innych.
- Więcej innowacji technologicznych, ponieważ nasz zespół inżynierów korzysta z usług wspólnych, narzędzi i zredukowanych kosztów platformy.

Przejście to będzie dotyczyło klientów, którzy obecnie korzystają z Dynamics 365 Human Resources lub starszego modułu HR.

## <a name="glossary-of-terms-used-in-this-faq"></a>Słowniczek terminów używanych w tym FAQ

- **Dynamics 365 Human Resources**— Nasz obecny i przyszły produkt, który oferuje rynkowi możliwości w zakresie HR.
- **Moduł HR** - Zestaw starszych funkcji, które były wcześniej licencjonowane w ramach oferty Unified Operations. Możliwości te są włączone, gdy klient posiada Dynamics 365 Finance lub Dynamics 365 Supply Chain Management.
- **Infrastruktura finansowa i operacyjna** – Architektura rozwoju używana przez portfolio operacji, w tym usługę Dynamics 365 Finance, Dynamics 365 Supply Chain Management i Dynamics 365 Project Operations. Ta infrastruktura jest tą, która będzie używana w przyszłości. W tym FAQ termin *połączona infrastruktura* odnosi się do środowiska finansowego i operacyjnego.
- **Infrastruktura zasobów ludzkich** — architektura programistyczna, która była historycznie wykorzystywana w aplikacji Dynamics 365 Human Resources. Projekt łączenia infrastruktury wprowadza Dynamics 365 Human Resources do infrastruktury finansowej i operacyjnej. Samodzielna infrastruktura zostanie zlikwidowana.

## <a name="general-questions-about-the-infrastructure-merge"></a>Ogólne pytania dotyczące łączenia infrastruktury

### <a name="will-customers-lose-any-features-or-capabilities"></a>Czy klienci stracą jakieś funkcje lub możliwości?

Naszym celem jest zminimalizowanie wpływu tego przejścia na klientów. Nie usuwamy żadnych funkcji ani możliwości. Zaistnieje parzystość funkcjonalna między Dynamics 365 Human Resources a modułem HR. W przypadkach, gdy dana funkcja występuje w obu infrastrukturach, wykorzystane zostanie doświadczenie Dynamics 365 Human Resources.

### <a name="will-the-user-experience-change"></a>Czy zmieni się doświadczenie użytkownika?

Doświadczenie użytkownika będzie spójne ze standardowym doświadczeniem platformy Dynamics 365. Mimo że ogólny wygląd pulpitu i menu pozostanie podobny, zostanie on dostosowany do standardowego wyglądu aplikacji Dynamics 365 Finance. Nawigacja będzie obejmować zarówno moduły, jak i obszary robocze, umożliwi korzystanie z ulubionych i wiele więcej. Przestrzenie robocze Dynamics 365 Human Resources, takie jak **Zarządzanie personelem** i **Pracownicy**, zostaną połączone z infrastrukturą finansową i operacyjną. W przyszłości nowe możliwości będą dostarczane poprzez zarządzanie funkcjami, które umożliwia klientom przeglądanie nowych funkcji i decydowanie, z których chcą korzystać. Więcej informacji znajdziesz w [Przegląd zarządzania funkcjami](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i [Dokumentacja interfejsu użytkownika](../fin-ops-core/fin-ops/get-started/user-interface-elements.md?toc=/dynamics365/human-resources/toc.json).

### <a name="when-will-the-dynamics-365-human-resources-infrastructure-merge-be-completed"></a>Kiedy zostanie zakończone łączenie infrastruktury Dynamics 365 Human Resources?

Połączenie infrastruktury będzie wprowadzane etapami, aby dać klientom czas na zaplanowanie i wykonanie niezbędnych czynności. Rozpoczęliśmy wprowadzanie możliwości w ramach fali 2 wydania Dynamics 2021. Planujemy zakończyć wszystkie prace nad rozwojem produktu w ramach tego projektu do końca 2022 roku. Należy pamiętać, że terminy mogą ulec zmianie. Najbardziej aktualne informacje można znaleźć na stronie [plany wydań](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-finance).

### <a name="what-training-and-resources-will-be-available-to-help-with-the-infrastructure-merge"></a>Jakie szkolenia i zasoby będą dostępne, aby pomóc w połączeniu infrastruktury?

Dostarczymy dokumentację, która szczegółowo opisuje każdy etap procesu scalania infrastruktury. W razie potrzeby zapewnimy dodatkowe zasoby szkoleniowe, takie jak filmy i warsztaty, aby pomóc klientom i partnerom w płynnym przejściu.

### <a name="will-there-be-changes-in-development-capabilities-after-the-infrastructure-merge-is-completed"></a>Czy po zakończeniu łączenia infrastruktury nastąpią zmiany w możliwościach rozwoju?

Aby dowiedzieć się więcej o możliwościach rozwoju, zobacz [Rozwiń i dostosuj stronę główną](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md).

## <a name="feature-availability-questions"></a>Pytania dotyczące dostępności funkcji

### <a name="will-the-linkedin-talent-hub-integration-work-on-the-finance-and-operations-infrastructure"></a>Czy integracja LinkedIn Talent Hub będzie działać w infrastrukturze finansowej i operacyjnej?

Nie, integracja LinkedIn Talent Hub nie będzie częścią połączonej infrastruktury. Dostępne są publiczne interfejsy programowania aplikacji (API) umożliwiające tworzenie integracji z rozwiązaniami do rekrutacji i śledzenia kandydatów. Klienci, którzy planują korzystać z LinkedIn Talent Hub, powinni współpracować z partnerem firmy Microsoft w celu integracji przy użyciu udostępnionych interfejsów API. Więcej informacji na temat interfejsów API integracji systemów śledzenia kandydatów (ATS) można znaleźć w części [Wprowadzenie do interfejsów API integracji systemów śledzenia kandydatów](./hr-admin-integration-ats-api-introduction.md).

### <a name="will-the-capabilities-that-are-currently-available-only-in-dynamics-365-human-resources-for-example-leave-management-and-benefits-management-be-available-after-the-merge-is-completed"></a>Czy możliwości, które są obecnie dostępne tylko w Dynamics 365 Human Resources (na przykład zarządzanie urlopami i świadczeniami) będą dostępne po zakończeniu połączenia?

Tak. Wszystkie możliwości aplikacji Dynamics 365 Human Resources są przenoszone do infrastruktury finansowej i operacyjnej. Funkcje te będą udostępniane stopniowo. Aby uzyskać aktualne informacje o dostępności funkcji dla połączonej infrastruktury, regularnie przeglądaj [plany wydań](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-finance).

### <a name="will-ceridian-integrations-with-dynamics-365-human-resources-be-available-after-the-infrastructure-merge-is-completed"></a>Czy integracje Ceridian z Dynamics 365 Human Resources będą dostępne po zakończeniu łączenia infrastruktury?

Ceridian jest w trakcie tworzenia integracji V2 z Dynamics 365 Human Resources, która wykorzystuje interfejsy API Payroll. Integracja oparta na plikach, która obecnie istnieje w Dynamics 365 Human Resources, nie zostanie zmigrowana do infrastruktury aplikacji finansowych i operacyjnych. Aby uzyskać więcej informacji, zobacz [Wprowadzenie interfejsu API listy płac](./hr-admin-integration-payroll-api-introduction.md).

### <a name="will-applicant-tracking-or-onboardingoffboarding-of-employees-functionality-be-included"></a>Czy funkcja śledzenia kandydatów lub włączania/wyłączania pracowników zostanie włączona?

W poprzednich wydaniach stworzyliśmy API integracji ATS, aby umożliwić partnerom i klientom tworzenie integracji ATS z HR. Dodatkowe funkcje związane z ATS zostały udostępnione w pierwszym etapie programu 2022. W kolejnych wydaniach będziemy nadal udoskonalać te interfejsy API.

Funkcje HR, które obecnie istnieją w infrastrukturze finansowej i operacyjnej, obejmują pewne funkcje zarządzania rekrutacją, które nie istnieją w Dynamics 365 Human Resources. Po zakończeniu łączenia infrastruktury ta funkcjonalność będzie dostępna dla wszystkich klientów HR. Ta funkcjonalność zapewnia lekką funkcjonalność ATS. Nie planujemy jednak rozszerzania tej funkcji w przyszłości. Klienci, którzy potrzebują bardziej zaawansowanych funkcji, mogą skorzystać z integracji z partnerskimi systemami ATS. Więcej informacji na temat interfejsów API integracji systemów ATS można znaleźć w części [Wprowadzenie do interfejsów API integracji systemów śledzenia kandydatów](./hr-admin-integration-ats-api-introduction.md).

### <a name="will-the-dynamics-ax-2012-upgrade-tools-be-used-to-upgrade-the-hr-module-in-ax-2012-to-the-dynamics-365-human-resources-app"></a>Czy narzędzia do aktualizacji Dynamics AX 2012 będą używane do aktualizacji modułu HR w AX 2012 do aplikacji Dynamics 365 Human Resources?

Tak. Aktualizacja z Dynamics AX 2012 do Dynamics 365 Human Resources odbędzie się według tej samej ścieżki aktualizacji i narzędzi, które są używane do aktualizacji do najnowszej wersji innych aplikacji operacyjnych Dynamics 365, takich jak Dynamics 365 Finance czy Dynamics 365 Supply Chain Management.

Więcej informacji na temat migracji do infrastruktury finansowej i operacyjnej znajdziesz w sekcji [Migracja klienta Human Resource FAQ](./customer-migration.md).
