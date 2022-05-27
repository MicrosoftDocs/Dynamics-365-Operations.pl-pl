---
title: Scalanie infrastruktury Dynamics 365 Human Resources — wydanie 10.0.25, aktualizacja
description: Ten temat zawiera informacje dotyczące wydania rozwiązania Microsoft Dynamics 365 Human Resources 10.0.25, które dostarcza pierwszą grupy możliwości w scaleniu infrastruktury.
author: twheeloc
ms.date: 01/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bf7ce43785e3ef485074f2b0294caea381f8f726
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688100"
---
# <a name="dynamics-365-human-resources-infrastructure-merge---release-10025-update"></a>Scalanie infrastruktury Dynamics 365 Human Resources — wydanie 10.0.25, aktualizacja

Zwolnienie z wersji 10.0.25 wprowadza pierwszą czynnościę możliwości w scaleniu infrastruktury. Podczas scalania infrastruktury Microsoft Dynamics 365 Human Resources zostanie scalona z infrastrukturą w rozwiązaniach Finanse i Operacje. Jednak licencja na oprogramowanie będzie kontynuowana jako niezależna aplikacja, podobnie jak Dynamics 365 Finance i Dynamics 365 Supply Chain Management. Aby uzyskać więcej informacji dotyczących scalania infrastruktury, zobacz często zadawane pytania dotyczące [scalania infrastruktury Dynamics 365 Human Resources](../human-resources/hr-infrastructure-merge-faq.md).

Scalenie zapewni spójność użytkownikom zasobów ludzkich na następujące sposoby:

- [Zarządzanie środowiskiem i integracja są spójne między aplikacjami Zasoby ludzkie oraz Finanse i Operacje.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/consistent-environment-management-integrations-between-human-resources-finance-operations-apps)

    - Zarządzaj środowiskami w Microsoft Dynamics Lifecycle Services, wyszukiwanie problemów i Regression Suite Automation Tool.
    - Istnieje jedna podstawa kodu, w której nowe funkcje dla Human Resources są zwalniane w ramach zwykłego procesu aktualizacji jednej wersji.
    - Sposób, w jaki uaktualnienia, aktualizacje i poprawki są stosowane do środowisk, jest spójny.

- [Opcje możliwości rozszerzania zostały poprawione.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/improve-extensibility-options)

    - W razie potrzeby możesz nadal korzystać z narzędzi Microsoft Power Platform.
    - Funkcje można rozszerzać za pośrednictwem formularzy, tabel, metod i interfejsów API.
    - Można tworzyć jednostki i rozszerzać je.

    Aby uzyskać więcej informacji o dostępnych opcjach rozszerzeń, zobacz [Omówienie możliwości rozszerzania w systemie Dynamics 365](../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md).

- [Utwórz jeden zestaw możliwości zasobów ludzkich w systemie Dynamics 365.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/create-one-set-human-resources-capabilities-within-dynamics-365)

    W wersji 10.0.25 funkcje, które istniały tylko w Human Resources, zostały udostępnione w infrastruktury w Finanse i Operacje. Aby klienci mogą korzystać z tych możliwości w środowisku aplikacji Finanse i Operacje, w zarządzaniu funkcjami muszą być włączone poniższe funkcje Zasobów Ludzkich.

    | Nazwa funkcji | Omówienie | Stan zwolnienia | 
    |--------------|----------|----------------| 
    | Obliczanie lat pracy | Opcja konfiguracji umożliwia wybór daty, która będzie używana do **obliczania lat pracy**. | Ogólnie dostępne | 
    | Ulepszenia działania przepływu pracy | Ta funkcja oferuje użytkownikowi ulepszone możliwości przesyłania i zatwierdzania przepływu pracy. | Ogólnie dostępne | 
    | Drukuj oceny wydajności | Przeglądy wydajności można drukować w formacie PDF. | Ogólnie dostępne | 
    | Łącza niestandardowe w **samoobsłudze menedżera** | Możesz utworzyć łącza niestandardowe, które będą widoczne w sekcji **Łącza pokrewne** **samoobsługi menedżera**. | Ogólnie dostępne | 
    | Widok wynagrodzeń między firmami | Użytkownicy mogą wyświetlać plany wynagrodzeń w **samoobsługi menedżera** we wszystkich firmach bez konieczności przełączania firm. | Ogólnie dostępne | 
    | Skonfiguruj wiele poziomów wynagrodzenia według stanowiska\*&dagger; | Zadania obsługują teraz wiele poziomów wynagrodzenia. | Wersja zapoznawcza | 
    | Zarządzanie zadaniami\* | Można tworzyć listy kontrolne i zadania dla procesu dołączania, odejmowania i przejścia. | Wersja zapoznawcza | 
    | Usprawniony wpis pracownika etatowego | Ta funkcja udostępnia zaktualizowane funkcje użytkownika na istniejącej **stronie Pracownik**. | Wersja zapoznawcza | 
    | Ulepszenia środowiska użytkownika zasobów ludzkich | Zobacz tabelę w następnej sekcji.  | Wersja zapoznawcza | 

\* Ta funkcja musi być włączona przed funkcją **ulepszeń interfejsu użytkownika Zasoby ludzkie**.

&dagger; Tej funkcji nie można wyłączyć po jej włączeniu.

## <a name="human-resource-user-experience-enhancements"></a>Ulepszenia doświadczeń użytkowników zasobów ludzkich

| Nazwa funkcji | Omówienie | 
|--------------|----------| 
| Usuń zatrudnienie | Można usunąć zatrudnienie pracownika. | 
| Rodziny zadania | Możesz śledzić grupę zadań, które obejmują podobną pracę i wymagają podobnego szkolenia, umiejętności, wiedzy i doświadczenia. | 
| Dodatkowe pola zatrudnienia | Dodano następujące pola: **Kategoria zatrudnienia**, **Typ zatrudnienia** i **Stan zatrudnienia**. | 
| Strona **Pracownicy bez zatrudnienia** | Na stronie jest wyświetlona lista pracowników, którzy nie mają rekordu zatrudnienia. | 
| Aktualizacja doświadczenia użytkownika wymiaru stanowiska | Istnieje rozszerzone możliwości użytkownika dotyczące przypisywania wymiarów stanowisk według firmy. | 
| Uwzględnij zmiany w obszarze roboczym **Zarządzanie personelem** | Funkcja zawiera liczbę wszystkich zmian adresów, które wystąpiły podczas liczby dni określonej na stronie **Parametry Human Resources**. | 
| Wygasające rekordy w obszarze roboczym **Zarządzanie personelem** | Ta funkcja udostępnia listę pozycji, które utraciły ważność lub wygasną w przypadku certyfikatów, identyfikacji, prób, kontroli lub testów. | 
| Strona **weryfikacji hierarchii stanowisk** | Sprawdzenie odbywa się dla odwołań cyklicznych w hierarchii wiersza pozycji. | 
| Informacje o listy płac specyficzne dla kraju | Dodatkowe pola listy płac są dostępne na stronie **Zatrudnienia pracownika** w zależności od kraju lub regionu firmy, w której są zatrudnieni pracownicy. | 
| Udoskonalenia raportowania zgodności | Dodatkowe opcje raportowania są dostępne dla raportów EEO-1, Vets 4212 i OSHA300a. | 
| Aktualizacje obszaru roboczego **Zarządzanie personelem** | Aktualizacje zostały wprowadzone w celu śledzenia zmian adresów i wygasających rekordów. Ponadto na nowych kartach są dostępne akcje związane z pracownikiem i stanowiskiem. | 
