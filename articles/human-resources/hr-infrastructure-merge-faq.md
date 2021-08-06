---
title: Infrastruktura Dynamics 365 Human Resources – często zadawane pytania
description: Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące scalania infrastruktury dla aplikacji Microsoft Dynamics 365 Human Resources i Finance and Operations.
author: rachel-profitt
ms.date: 07/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fee4fea9b67ff8a0c8d813940a65cf882bd13abe
ms.sourcegitcommit: bf2daeccbe3f2826e734f409bfc823820144aa23
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/15/2021
ms.locfileid: "6617998"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>Infrastruktura Dynamics 365 Human Resources – często zadawane pytania

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące scalania infrastruktury dla aplikacji Microsoft Dynamics 365 Human Resources i Finance and Operations.

## <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>Co to jest scalanie infrastruktury Dynamics 365 Human Resources?

Dynamics 365 Human Resources jest autonomiczną aplikacją, która korzysta z innej infrastruktury niż inne aplikacje Finance and Operations, takie jak Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce i Dynamics 365 Project Operations. Scalanie infrastruktury przeniesie Dynamics 365 Human Resources do tej samej infrastruktury, co inne aplikacje Finance and Operations.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>Wartość i korzyści związane z fuzją infrastruktury

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-what-benefits-will-we-see-from-these-changes"></a>Moja organizacja używa Dynamics 365 Human Resources do zarządzania operacjami HR. Jakie korzyści odniesiemy z tych zmian?

- Te zmiany eliminują wiele zestawów funkcji zasobów ludzkich (HR) w Dynamics 365.
- Zapewniają zarówno rozszerzalność Microsoft Power Platform, jak i sposób na rozszerzenie logiki biznesowej i opcji funkcji.
- Zapewniają spójność między Dynamics 365 Human Resources a innymi aplikacjami Finance and Operations w zakresie zarządzania cyklem życia aplikacji (ALM), usług Microsoft Dynamics Lifecycle Services (LCS), dostępności geograficznej, rozszerzalności i nie tylko.
- Umożliwiają one korzystanie z usług współdzielonych i narzędzi oraz pomagają obniżyć koszty.

### <a name="my-organization-uses-dynamics-365-human-resources-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-benefits-will-we-see-from-these-changes"></a>Moja organizacja używa Dynamics 365 Human Resources w Dynamics 365 Finance, Supply Chain Management, Commerce lub Project Operations. Jakie korzyści odniesiemy z tych zmian?

Możliwości i inwestycje dokonane w Dynamics 365 Human Resources będą teraz dostępne dla klientów korzystających z modułu HR w Dynamics 365 Finance. Niektóre z tych możliwości obejmują zarządzanie urlopami i nieobecnościami, zarządzanie świadczeniami i zarządzanie zadaniami.

### <a name="will-i-lose-any-features-or-capabilities-that-i-currently-use"></a>Czy stracę jakieś funkcje lub możliwości, z których obecnie korzystam?

Zaistnieje parzystość funkcjonalna między Dynamics 365 Human Resources a modułem HR w aplikacjach Finance and Operations. Dynamics 365 Human Resources będzie miały pierwszeństwo dla podobnych funkcji. Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="will-the-experience-change-for-my-users"></a>Czy doświadczenie zmieni się dla moich użytkowników?

Nowe funkcje HR będą zarządzane przez Zarządzanie funkcjami. Klienci zdecydują, czy chcą je podjąć. W niektórych przypadkach możliwości mogą być modyfikowane. W takich przypadkach zostanie dostarczona dokumentacja.

### <a name="how-does-this-change-affect-me-if-i-am-an-existing-customer-and-i-use-both-the-hr-module-on-the-finance-and-operations-infrastructure-and-dynamics-365-human-resources-through-custom-integrations"></a>Jak ta zmiana wpłynie na mnie, jeśli jestem istniejącym klientem i używam zarówno modułu HR w infrastrukturze Finance and Operations, jak i Dynamics 365 Human Resources poprzez niestandardowe integracje?

Niestandardowe integracje między Dynamics 365 Human Resources a modułem HR w Dynamics 365 Finance nie będą już wymagane. Wszystkie dane HR będą reprezentali się w tej samej bazie danych co inne aplikacje Finance and Operations.

## <a name="migration-from-dynamics-365-human-resources-to-finance-and-operations-apps"></a>Migracja z Dynamics 365 Human Resources do aplikacji Finance and Operations

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-hr-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>Moja organizacja używa Dynamics 365 Human Resources do zarządzania operacjami HR. Co musimy zaplanować, aby przejść na nowe środowisko?

Jeśli Twoja organizacja korzysta z Dynamics 365 Human Resources, ale nie używa żadnych innych aplikacji Finance and Operations, Twoje środowisko Human Resources zostanie zmigrowane do nowej infrastruktury. Duża część tego procesu migracji zostanie zautomatyzowana. Wdrożone zostaną procesy migracji Twojej bazy danych i zsynchronizowania jej z nową infrastrukturą.

Ponadto dostępne będą narzędzia, które pozwolą przetestować proces migracji oraz zweryfikować dane i doświadczenie przed migracją środowiska produkcyjnego.

Jeśli Twoja organizacja korzysta zarówno z Dynamics 365 Human Resources, jak i innych aplikacji Finance and Operations, należy zaplanować więcej czasu na weryfikację, aby upewnić się, że dane są poprawnie migrowane do nowego środowiska. Migracja do nowej infrastruktury spowoduje scalenie danych ze środowiska Human Resources ze środowiskiem Finance and Operations. Wprowadzone zostaną narzędzia do jak największej automatyzacji procesu scalania danych. Jednak wystąpienia danych powodujących konflikt będzie wymagać danych wejściowych użytkownika, aby zdefiniować, jak konflikt powinien zostać rozwiązany. Użytkownicy i administratorzy będą musieli zarządzać mapowaniami danych tam, gdzie występują konflikty i testować migrację w środowiskach piaskownicy przed migracją środowiska produkcyjnego.

### <a name="my-organization-uses-dynamics-365-human-resources-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>Moja organizacja używa Dynamics 365 Human Resources w Dynamics 365 Finance, Supply Chain Management, Commerce lub Project Operations. Co musimy zaplanować, aby przejść na nowe środowisko?

W przypadku organizacji, które korzystają z modułu HR w aplikacjach Finance and Operations, nowa funkcja z Dynamics 365 Human Resources zostanie zastosowana w Twoim środowisku za pośrednictwem standardowego procesu aktualizacji jednej wersji. Możesz spodziewać się pojawienia się nowej funkcjonalności w swoim środowisku, gdy będzie ona dostępna w każdej aktualizacji. Możesz użyć zarządzania funkcjami, aby włączyć nowe funkcje. Należy jednak zaplanować sprawdzanie poprawności tych funkcji. Postępuj zgodnie z istniejącymi procesami sprawdzania poprawności innych aktualizacji środowiska. Aby uzyskać więcej informacji o sposobie stosowania aktualizacji do aplikacji Finance and Operations, zobacz [Omówienie jednej wersji](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="when-will-my-organization-be-migrated"></a>Kiedy moja organizacja zostanie zmigrowana?

Migracja dla każdej organizacji będzie zależeć od jej aktualnej konfiguracji i gotowości do migracji do nowej infrastruktury. Daty te mogą ulec zmianie.

- Organizacje, które obecnie korzystają z modułu HR w aplikacjach Finance and Operations, otrzymają funkcje HR Dynamics 365 Human Resources w ramach zwykłego procesu aktualizacji jednej wersji. Planujemy, że nowe funkcje będą ogólnie dostępne od października 2021 r.
- Organizacje, które obecnie używają tylko Dynamics 365 Human Resources, będą miały dostęp do narzędzi do migracji, dzięki czemu będą mogły rozpocząć testowanie i rozpocząć migrację począwszy od połowy 2022 roku. Data, do której migracja do nowej infrastruktury musi zostać zakończona, nie została jeszcze ustalona. Jednak minie co najmniej rok od daty udostępnienia narzędzi do migracji.
- Organizacje, które obecnie używają zarówno Dynamics 365 Human Resources, jak i innych aplikacji Finance and Operations, będą miały dostęp do narzędzi do migracji, dzięki czemu będą mogły rozpocząć testowanie i rozpocząć migrację od końca 2022 roku. Data, do której migracja do nowej infrastruktury musi zostać zakończona, nie została jeszcze ustalona. Jednak minie co najmniej rok od daty udostępnienia narzędzi do migracji.

Aby uzyskać więcej informacji na temat nowych funkcji Dynamics 365 Human Resources, zobacz [Co nowego lub zmienionego w Human Resources](./hr-admin-whats-new.md).

### <a name="i-am-using-new-capabilities-that-are-available-only-in-dynamics-365-human-resources-such-as-leave-and-absence-and-benefits-management-will-these-capabilities-now-be-available-in-the-human-resources-module-on-the-finance-and-operations-infrastructure-too"></a>Korzystam z nowych funkcji, które są dostępne tylko w Dynamics 365 Human Resources (takich jak **Urlopy i nieobecności** oraz **Zarządzanie korzyściami**). Czy te możliwości będą teraz dostępne w module Zasoby ludzkie również w infrastrukturze Finance and Operations?

Tak, wszystkie moduły Dynamics 365 Human Resources będą działać bez zmian w aplikacjach Finance and Operations i będzie mieć 100-procentową parzystość funkcji. W ramach ogólnej strategii migracji dla klientów, którzy obecnie korzystają z tych funkcji w dziale HR, dane klientów zostaną zmigrowane, aby nadal działały w infrastrukturze Finance and Operations.

### <a name="i-use-the-new-dynamics-365-human-resources-benefits-management-capabilities-ive-built-custom-integrations-with-the-hr-module-on-the-finance-and-operations-infrastructure-so-that-i-can-take-advantage-of-the-payroll-capabilities-by-using-benefits-data-will-these-custom-integrations-be-required-going-forward"></a>Korzystam z nowych możliwości zarządzania korzyściami Dynamics 365 Human Resources. Zbudowałem niestandardowe integracje z modułem HR w infrastrukturze Finance and Operations, dzięki czemu mogę korzystać z funkcji płacowych przy użyciu danych dotyczących świadczeń. Czy te niestandardowe integracje będą wymagane w przyszłości?

W ramach scalania infrastruktury dane zasobów ludzkich są wprowadzane do tej samej bazy danych co inne aplikacje Finance and Operations. Integracja między modułami w aplikacjach Finance and Operations nie będzie już wymagana.

### <a name="my-organization-uses-one-or-more-isv-solutions-with-dynamics-365-human-resources-will-our-isv-solutions-be-migrated-automatically"></a>Moja organizacja korzysta z jednego lub więcej rozwiązań z isv z Dynamics 365 Human Resources. Czy nasze rozwiązania isv zostaną automatycznie przeniesione?

Doświadczenie migracji dla każdego rozwiązania niezależnego dostawcy oprogramowania (ISV) będzie się różnić w zależności od metody integracji rozwiązania. Microsoft będzie ściśle współpracować z niezależnymi dostawcami oprogramowania, aby zapewnić płynne przejście do nowej infrastruktury.

### <a name="my-organization-uses-linkedin-talent-hub-integration-with-dynamics-365-human-resources-will-this-integration-continue-to-work-after-the-infrastructure-change-is-completed"></a>Moja organizacja korzysta z integracji LinkedIn Talent Hub z Dynamics 365 Human Resources. Czy ta integracja będzie nadal działać po zakończeniu zmiany infrastruktury?

Tak, integracja LinkedIn Talent Hub będzie nadal działać po migracji do nowej infrastruktury.

### <a name="my-organization-uses-the-human-resources-app-for-teams-will-the-app-continue-to-work-after-the-infrastructure-change-is-completed"></a>Moja organizacja korzysta z aplikacji Human Resources dla aplikacji Teams. Czy aplikacja będzie nadal działać po zakończeniu zmiany infrastruktury?

Tak, aplikacja Human Resources for Teams będzie nadal działać po migracji do nowej infrastruktury.

### <a name="my-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-our-custom-security-still-be-applied-after-the-infrastructure-change-is-completed"></a>Moja organizacja skonfigurowała niestandardowe zabezpieczenia w Dynamics 365 Human Resources. Czy nasze niestandardowe zabezpieczenia będą nadal stosowane po zakończeniu zmiany infrastruktury?

Tak, niestandardowe konfiguracje zabezpieczeń zostaną uwzględnione w migracji danych do nowej infrastruktury.

### <a name="we-are-using-data-integrator-to-move-data-between-dynamics-365-human-resources-and-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected"></a>Używamy integratora danych do przenoszenia danych między Dynamics 365 Human Resources i aplikacjami Finance and Operations. W jaki sposób będzie to dotyczyć danych, które są obecnie integrowane?

Dane HR, które są obecnie opanowane w Dynamics 365 Human Resources są synchronizowane z Dataverse. Integrator danych może być następnie używany do synchronizacji jednokierunkowej z aplikacjami Finance and Operations. Po migracji do nowej infrastruktury dane dotyczące kadr zostaną natywne dla aplikacji Finance and Operations. Integrator danych nie będzie już wymagany do synchronizowania danych między aplikacjami Finance and Operations i Human Resources.

Obecne natywne tabele danych Dataverse dla Human Resources będą nadal synchronizować dane ze środowiska w nowej infrastrukturze. Jednostki zostaną przekonwertowane na obsługę podwójnego zapisu. Wszelkie inne integracje danych skonfigurowane za pomocą Data Integrator względem tych tabel dla innych aplikacji Dynamics 365 będą nadal działać tak, jak są obecnie skonfigurowane.

### <a name="we-are-using-dual-write-to-move-hr-data-between-dataverse-and-other-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected-by-the-migration-to-the-new-infrastructure"></a>Używamy podwójnego zapisu do przenoszenia danych HR między Dataverse a innymi aplikacjami Finance and Operations. Jak na dane, które są obecnie integrowane, wpłynie migracja do nowej infrastruktury?

Dane HR będą natywne dla aplikacji Finance and Operations w środowisku nowej infrastruktury. Podwójny zapis będzie następnie używany do przenoszenia danych HR między nowym środowiskiem a środowiskiem Dataverse.

### <a name="we-have-built-custom-integrations-from-dynamics-365-human-resources-to-one-or-more-external-systems-will-we-have-to-develop-new-integrations-after-the-infrastructure-change-is-completed"></a>Zbudowaliśmy niestandardowe integracje z Dynamics 365 Human Resources z jednym lub większą liczbą systemów zewnętrznych. Czy po zakończeniu zmiany infrastruktury będziemy musieli tworzyć nowe integracje?

Zależy to od punktu końcowego integracji. Aby uzyskać więcej informacji o technologiach integracji dostępnych w aplikacjach Finance and Operations oraz o tym, jak wybrać najlepszą technologię integracji, zobacz [Omówienie integracji](../fin-ops-core/dev-itpro/data-entities/integration-overview.md).

### <a name="we-have-extended-dataverse-for-dynamics-365-human-resources-will-these-extensions-be-migrated-automatically"></a>Rozszerzyliśmy Dataverse dla Dynamics 365 Human Resources. Czy te rozszerzenia zostaną przeniesione automatycznie?

Jeśli środowiska Dynamics 365 Human Resources oraz Finance and Operations, które zostaną połączone w środowisku nowej infrastruktury, są połączone z tym samym środowiskiem Dataverse, po migracji obie aplikacje będą nadal połączone z tym samym środowiskiem Dataverse. Z tego względu migracja nie jest wymagana dla żadnych rozszerzeń Dataverse.

Jeśli jednak środowiska Dynamics 365 Human Resources i Finance and Operations są obecnie połączone z oddzielnymi środowiskami Dataverse, oba środowiska Dataverse będą musiały zostać połączone tak, aby były połączone z jednym środowiskiem w nowej infrastrukturze. W przypadku tej migracji Dataverse tabele Dataverse, które są standardem w rozwiązaniach HR, można połączyć i ponownie zsynchronizować z nowym środowiskiem Dataverse. Jednak żadne rozszerzenia do środowiska Dataverse nie będą migrowane automatycznie, ale muszą zostać ponownie wdrożone w nowym środowisku. Zalecamy korzystanie z zarządzanych rozwiązań do zarządzania rozszerzeniami Dataverse. Aby uzyskać więcej informacji, zobacz [Wprowadzenie do rozwiązań](https://docs.microsoft.com/powerapps/developer/data-platform/introduction-solutions).

### <a name="we-have-configured-microsoft-power-automate-flows-andor-microsoft-power-apps-to-work-with-dynamics-365-human-resources-will-these-microsoft-power-platform-components-be-migrated-and-work-automatically-after-the-infrastructure-change-is-completed"></a>Skonfigurowaliśmy przepływy Microsoft Power Automate i/lub Microsoft Power Apps do pracy z Dynamics 365 Human Resources. Czy te składniki Microsoft Power Platform zostaną zmigrowane i będą działać automatycznie po zakończeniu zmiany infrastruktury?

Przepływy Power Apps, Power Automate i inne dostosowania Microsoft Power Platform są podobne do rozszerzeń Dataverse. To, czy działają one automatycznie po migracji do nowej infrastruktury, zależy od tego, czy aplikacja Human Resources oraz Finance and Operations są połączone z tym samym środowiskiem Power Apps przed migracją.

Jeśli aplikacje są obecnie połączone z tym samym środowiskiem Power Apps, będą nadal połączone z tym środowiskiem Power Apps po migracji do nowej infrastruktury. W takim przypadku przepływy Power Apps, Power Automate i inne dostosowania Microsoft Power Platform będą nadal działać bez dodatkowej konfiguracji. Zalecamy używanie zarządzanych rozwiązań do zarządzania rozszerzeniami aplikacji w Dataverse. Aby uzyskać więcej informacji, zobacz [Wprowadzenie do rozwiązań](https://docs.microsoft.com/powerapps/developer/data-platform/introduction-solutions).

Jeśli jednak aplikacja Human Resources i Finance and Operations są połączone z oddzielnymi środowiskami Power Apps, będą musiały zostać połączone w ramach migracji. To zadanie będzie wymagało ponownego wdrożenia wszystkich Power Apps i innych dostosowań w nowym środowisku.

### <a name="we-have-enabled-dataverse-virtual-tables-for-dynamics-365-human-resources-what-will-happen-to-these-tables-during-the-migration"></a>Włączono wirtualne tabele Dataverse dla Dynamics 365 Human Resources. Co się stanie z tymi tabelami podczas migracji?

Po migracji, jeśli środowisko w nowej infrastrukturze pozostanie połączone ze środowiskiem Dataverse, które jest obecnie połączone z Dynamics 365 Human Resources, tabele wirtualne Dataverse wygenerowane w tym środowisku będą nadal działać bez dodatkowej konfiguracji.

Jeśli jednak środowisko w nowej infrastrukturze zostanie połączone z innym środowiskiem Dataverse po migracji, wirtualne tabele będą musiały zostać zregenerowane w nowym środowisku Dataverse.

### <a name="we-have-developed-an-integration-by-using-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-will-these-integrations-continue-to-work-after-the-infrastructure-change-is-completed"></a>Opracowaliśmy integrację, korzystając z interfejsu API systemu śledzenia aplikantów (ATS), interfejsu API do płac, tabel wirtualnych Dataverse dla Dynamics 365 Human Resources lub innych jednostek w internetowym interfejsie API Dataverse. Czy te integracje będą nadal działać po zakończeniu zmiany infrastruktury?

Po migracji, jeśli środowisko w nowej infrastrukturze pozostanie połączone ze środowiskiem Dataverse, które jest obecnie połączone z Dynamics 365 Human Resources, wszelkie integracje opracowane z użyciem internetowego interfejsu API Dataverse będą nadal działać po zakończeniu migracji.

Jeśli jednak środowisko w nowej infrastrukturze jest połączone z innym środowiskiem Dataverse po migracji, wszelkie integracje opracowane z wykorzystaniem internetowego interfejsu API Dataverse będą musiały zostać ponownie skonfigurowane, aby połączyć się z nowym środowiskiem Dataverse.

### <a name="is-there-an-impact-on-the-azure-region-when-my-environment-is-migrated"></a>Czy migracja mojego środowiska ma wpływ na region platformy Azure?

Oczekuje się, że podczas migracji środowisko Human Resources zwykle pozostanie w tym samym regionie platformy Azure. Jedyny wyjątek występuje wtedy, gdy środowisko Human Resources zostanie scalone ze środowiskiem Finance and Operations znajdującym się w innym regionie. W takim przypadku środowisko Human Resources zostanie zmigrowane do regionu platformy Azure środowiska Finance and Operations.

### <a name="my-organization-depends-on-workflows-in-dynamics-365-human-resources-for-one-or-more-business-processes-will-the-workflows-be-migrated-automatically"></a>Moja organizacja jest zależna od przepływów pracy w Dynamics 365 Human Resources dla jednego lub większej liczby procesów biznesowych. Czy przepływy pracy będą migrowane automatycznie?

Tak, konfiguracje przepływów pracy, historia przepływów pracy i bieżące przepływy pracy w procesie zostaną zmigrowane.

### <a name="what-training-and-resources-will-be-available-to-help-with-the-migration-process"></a>Jakie szkolenia i zasoby będą dostępne, aby pomóc w procesie migracji?

Dostarczona zostanie pełna dokumentacja, aby szczegółowo opisać każdy etap procesu migracji. W zależności od potrzeb można również korzystać z dodatkowych zasobów szkoleniowych, takich jak filmy i warsztaty.

### <a name="my-organization-has-created-saved-views-in-dynamics-365-human-resources-to-improve-the-usability-of-the-interface-will-the-saved-views-be-migrated-automatically"></a>Moja organizacja utworzyła zapisane widoki w Dynamics 365 Human Resources, aby poprawić użyteczność interfejsu. Czy zapisane widoki zostaną przeniesione automatycznie?

Tak, zapisane widoki zostaną przeniesione do nowej infrastruktury.

### <a name="we-are-using-ceridian-with-dynamics-365-human-resources-will-the-ceridian-integration-be-available-after-the-infrastructure-change-is-completed"></a>Używamy Ceridian z Dynamics 365 Human Resources. Czy integracja Ceridian będzie dostępna po zakończeniu zmiany infrastruktury? 

Integracja z Ceridian zostanie przeniesiona do integracji opartej na Payroll API. Integracja oparta na plikach, która obecnie istnieje w Dynamics 365 Human Resources, nie zostanie zmigrowana do infrastruktury Finance and Operations. Aby uzyskać więcej informacji, zobacz [Wprowadzenie interfejsu API listy płac](./hr-admin-integration-payroll-api-introduction.md).

### <a name="how-will-the-migration-affect-the-service-update-process"></a>Jak migracja wpłynie na proces aktualizacji usługi?

Po migracji klienci będą mieli znacznie większą elastyczność w zakresie aktualizacji ALM i usług. Aktualizacje usług nie będą już automatycznie stosowane w środowiskach Human Resources. W zamian usługa będzie przestrzegać procesów i funkcji aktualizacji usługi One Version. Dlatego opcje konfiguracji aktualizacji będą dostępne za pośrednictwem usługi LCS. Aby uzyskać więcej informacji, zobacz temat [Omówienie One Version](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="how-will-the-migration-affect-my-lcs-project-for-dynamics-365-human-resources"></a>Jak migracja wpłynie na mój projekt LCS dla Dynamics 365 Human Resources?

Migracja do nowej infrastruktury przeniesie zarządzanie Twoimi środowiskami Dynamics 365 Human Resources do projektu wdrożenia LCS. Jeśli migracja scala Dynamics 365 Human Resources z istniejącym środowiskiem Finance and Operations, Twój projekt Human Resources LCS zostanie scalony z projektem implementacji LCS dla aplikacji Finance and Operations. Jeśli obecnie używasz tylko Dynamics 365 Human Resources, zostanie utworzony nowy projekt implementacji LCS, a Twój istniejący projekt Human Resources LCS zostanie przeniesiony do nowego projektu.

Nowy projekt będzie tego samego typu, z którego korzystają aplikacje Finance and Operations. Będzie miał te same funkcje i funkcjonalność do zarządzania środowiskiem. Aby uzyskać więcej informacji, zobacz [Zasoby w Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

### <a name="we-have-linked-our-task-recordings-to-the-business-process-modeler-in-human-resources-how-will-the-business-process-modeler-be-migrated-and-merged-into-lcs"></a>Połączyliśmy nasze nagrania zadań z modelarzem procesów biznesowych w Human Resources. W jaki sposób narzędzie do modelowania procesów biznesowych zostanie zmigrowane i połączone z LCS?

Biblioteki procesów biznesowych dla projektu LCS zostaną przeniesione do nowego projektu LCS dla zasobów ludzkich.

### <a name="my-organization-currently-uses-only-dynamics-365-human-resources-what-resources-are-available-so-that-we-can-learn-more-about-the-development-capabilities-after-the-infrastructure-change-is-completed"></a>Moja organizacja aktualnie używa tylko Dynamics 365 Human Resources. Jakie zasoby są dostępne, abyśmy mogli dowiedzieć się więcej o możliwościach programistycznych po zakończeniu zmiany infrastruktury?

Zarówno opcje rozszerzalności Microsoft Power Platform, jak i opcje rozszerzalności Finance and Operations będą dostępne i mogą być używane do programowania. Aby uzyskać więcej informacji, zobacz [Ipracowywanie i dostosowywanie strony głównej](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md).

### <a name="we-have-enabled-features-in-dynamics-365-human-resources-will-these-features-be-enabled-automatically-during-the-migration"></a>Włączono funkcje w programie Dynamics 365 Human Resources. Czy te funkcje zostaną włączone automatycznie podczas migracji?

To, czy funkcja jest włączana automatycznie w nowej infrastrukturze, będzie określane indywidualnie dla każdej funkcji. Te informacje zostaną uwzględnione w dokumentacji funkcji.

### <a name="what-happens-to-my-byod-database-during-the-migration"></a>Co się dzieje z bazą danych BYOD podczas migracji?

Konfiguracje importu i eksportu w celu wprowadzenia własnej bazy danych (BYOD) zostaną przeniesione do nowej infrastruktury.

### <a name="what-happens-to-my-azure-data-lake-during-the-migration"></a>Co się dzieje z Azure Data Lake podczas migracji?

Każdy eksport, który jest obecnie skonfigurowany dla usługi Azure Data Lake Storage w aplikacjach Finance and Operations, zachowa tę samą konfigurację po migracji.

### <a name="we-are-currently-using-dynamics-ax-2012-will-the-upgrade-tools-that-are-currently-available-be-used-to-upgrade-the-hr-module-in-ax-2012-to-dynamics-365-human-resources"></a>Aktualnie używasz systemu Dynamics AX 2012. Czy narzędzia do uaktualniania, które są obecnie dostępne, zostaną użyte do uaktualnienia modułu HR w AX 2012 do Dynamics 365 Human Resources?

Tak. Dynamics 365 Human Resources zostanie uwzględniony w scalonej bazie kodów i infrastruktury aplikacji Finance and Operations. Uaktualnienie z Dynamics AX 2012 do Dynamics 365 Human Resources będzie korzystać z tej samej ścieżki uaktualnienia i narzędzi, które są używane do uaktualniania do najnowszej wersji aplikacji Finance and Operations.

### <a name="we-use-document-handling-with-dynamics-365-human-resources-what-will-happen-to-the-documents-during-the-migration"></a>Korzystamy z funkcji obsługi dokumentów z Dynamics 365 Human Resources. Co stanie się z dokumentami podczas migracji?

Dokumenty pozostaną w istniejącym magazynie dokumentów. Zostaną one przemapowane do środowiska w nowej infrastrukturze.

### <a name="what-happens-to-the-batch-jobs-that-we-have-configured-in-dynamics-365-human-resources-after-the-migration"></a>Co się stanie z zadaniami wsadowymi, które skonfigurowaliśmy w Dynamics 365 Human Resources po migracji?

Odpowiednie zadania wsadowe zostaną automatycznie zmigrowane do nowej infrastruktury.

## <a name="licensing-impact"></a>Wpływ na licencje

Ta dokumentacja nie zastępuje ani nie zastępuje żadnej dokumentacji prawnej, która obejmuje prawa do użytkowania.

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-does-our-licensing-or-cost-change"></a>Moja organizacja używa Dynamics 365 Human Resources do zarządzania operacjami HR. Czy zmienia się nasza licencja lub koszt?

Klienci, którzy kupili licencje Dynamics 365 Human Resources, nie będą mieli wpływu. Nie istnieje migracja licencji dla tego odbiorcy. Dodatkowa jednostka przechowywania zapasów w piaskownicy (SKU), która była specyficzna dla Human Resources, nie będzie już obowiązywać. Zamiast tego klienci mogą zdecydować się na zakup piaskownicy warstwy 2 aplikacji Finance and Operations po nieco niższych kosztach. Dotychczasowi klienci, którzy kupili piaskownicę Human Resources, zostaną przeniesieni do piaskownicy warstwy 2 aplikacji Finance and Operations bez dodatkowych kosztów.

### <a name="my-organization-uses-dynamics-365-human-resources-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-does-my-licensing-or-cost-change"></a>Moja organizacja używa Dynamics 365 Human Resources w Dynamics 365 Finance, Supply Chain Management, Commerce lub Project Operations. Czy zmienia się moja licencja lub koszt?

Obecni użytkownicy aplikacji Dynamics 365 i użytkownicy autonomicznych Dynamics 365 Finance, Supply Chain Management, Commerce i Project Operations mogą uzyskiwać dostęp do Human Resources w ramach tych licencji do lutego 2025 lub do wygaśnięcia obecnej umowy licencyjnej, w zależności od tego, co nastąpi wcześniej. Możesz zdecydować się na wcześniejsze przejście na licencje Human Resources, jeśli pomoże Ci to osiągnąć lepsze oszczędności. Od lutego 2025 r. wszyscy obecni klienci CSP i EA muszą wycofać moduł HR i kupić licencje HR, aby korzystać z nowych funkcji wprowadzanych do aplikacji Finance and Operations.

### <a name="my-organization-is-live-with-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-will-we-be-required-to-purchase-an-additional-environment-to-support-the-infrastructure-merge"></a>Moja organizacja używa Dynamics 365 Finance, Supply Chain Management, Commerce lub Project Operations. Czy będziemy musieli zakupić dodatkowe środowisko w celu wsparcia fuzji infrastruktury?

Dodatkowe środowiska nie są wymagane do obsługi zmiany infrastruktury.

### <a name="where-should-i-go-if-i-have-additional-questions-about-product-licensing"></a>Gdzie mam się udać, jeśli mam dodatkowe pytania dotyczące licencjonowania produktów?

W przypadku pytań dotyczących licencjonowania można znaleźć więcej informacji w [Biz Apps Hub — ceny i licencje D365](https://businessapplications.transform.microsoft.com/resources/pricing-and-licensing?tab=grandfathering). Jeśli te informacje nie pomogą w tym problemie, otwórz prośbę za pomocą usługi LicenseQ.
