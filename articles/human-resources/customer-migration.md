---
title: Migracja odbiorcy do rozwiązania Human Resources — często zadawane pytania
description: Ten artykuł odpowiada na najczęściej zadawane pytania dotyczące migracji rozwiązania Microsoft Dynamics 365 Human Resources do połączonej infrastruktury finansowej i operacyjnej.
author: twheeloc
ms.date: 07/06/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0e11d26ebe084762a8616c8aa0aa041a87306473
ms.sourcegitcommit: e25fe4228add88dd37f4f38ece86979e1c621f6a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2022
ms.locfileid: "9734366"
---
# <a name="human-resources-customer-migration"></a>Migracja odbiorcy do rozwiązania Human Resources

## <a name="how-should-dynamics-365-human-resources-customers-plan-to-move-to-the-finance-and-operations-infrastructure"></a>Jak klienci Dynamics 365 Human Resources powinni zaplanować przejście na infrastrukturę finansów i operacji?

Dotknięte zostaną dwie kategorie klientów Microsoft Dynamics 365 Human Resources, którzy będą musieli wprowadzić zmiany, aby zapewnić sobie dostęp do najnowszej infrastruktury finansowej i operacyjnej:

- Klienci, którzy korzystają z Dynamics 365 Human Resources i nie mają żadnych innych aplikacji operacyjnych z Dynamics 365
- Klienci, którzy używają jednocześnie Dynamics 365 Human Resources i Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce lub Dynamics 365 Project Operations.

Niezależnie od kategorii, do której należą, klienci będą musieli przenieść dane do nowo utworzonego środowiska w infrastrukturze finansowej i operacyjnej oraz sprawdzić, czy połączenie zostało pomyślnie zakończone.

W przyszłości aplikacja Dynamics 365 Human Resources będzie miała swoje własne środowisko aplikacji finansowych i operacyjnych, oddzielone od innych aplikacji operacyjnych. W ten sposób klienci będą mogli korzystać z opcji rozszerzenia bez konieczności łączenia swoich obecnych danych. Microsoft dostarczy narzędzia i środowisko piaskownicy, które klienci będą mogli wykorzystać do przetestowania i zatwierdzenia migracji danych przed przeniesieniem ich do środowiska produkcyjnego. Oprzyrządowanie umożliwi niemal zautomatyzowany proces i będzie dostępne w okresie od sierpnia do listopada 2022 roku.

Klienci, którzy korzystają z innych aplikacji finansowych i operacyjnych, będą mogli połączyć swoje dane dotyczące zasobów ludzkich z istniejącym środowiskiem. 

## <a name="when-will-customers-be-moved-to-the-finance-and-operations-infrastructure"></a>Kiedy klienci zostaną przeniesieni do infrastruktury finansowej i operacyjnej?

Przejście dla każdej firmy będzie zależało od jej obecnej konfiguracji i gotowości do przejścia na infrastrukturę finansową i operacyjną. Zalecamy, aby klienci współpracowali ze swoimi partnerami z firmy Microsoft w celu określenia najlepszego sposobu postępowania.

- Organizacje korzystające z modułu **Human Resources** w Dynamics 365 Finance będą mogły włączyć nowe możliwości Dynamics 365 Human Resources w ramach regularnego procesu aktualizacji One Version. Planujemy, że nowe funkcje będą ogólnie dostępne od stycznia 2022 r.
- Organizacje korzystające z Dynamics 365 Human Resources będą miały dostęp do narzędzi, które mogą wykorzystać do zakończenia procesu łączenia infrastruktury. Microsoft będzie współpracował z klientami przy przejściu na nowy system, aby zapobiec przerwom w świadczeniu usług. Klienci będą mieli od 12 miesięcy na dokonanie przejścia, licząc od momentu udostępnienia narzędzi migracyjnych.
- Organizacje, które używają zarówno Dynamics 365 Human Resources, jak i modułu **Human Resources**, mogą przenieść swoją samodzielną infrastrukturę Human Resources na infrastrukturę finansową i operacyjną. Inną możliwością jest użycie narzędzia scalania, aby połączyć środowiska w jedno. Nie ma wymogu ani terminu połączenia tych dwóch środowisk.

Aby uzyskać aktualne informacje, regularnie sprawdzaj [Plany wydawnicze](/dynamics365/release-plans/).

## <a name="will-customers-still-need-custom-integrations-between-dynamics-365-human-resources-and-the-human-resources-module"></a>Czy klienci nadal będą potrzebowali niestandardowych integracji pomiędzy Dynamics 365 Human Resources a modułem Human Resources?

- Klienci, którzy posiadają zarówno Dynamics 365 Human Resources, jak i inne środowiska infrastruktury finansowej i operacyjnej, które są obecnie zintegrowane, będą musieli kontynuować integrację tych dwóch środowisk po połączeniu.
- Klienci, którzy zdecydują się na oddzielenie środowiska Dynamics 365 Human Resources od istniejącego środowiska aplikacji finansowych i operacyjnych, będą musieli kontynuować integrację środowisk, aby dane były dostępne w obu środowiskach.
- Klienci mogą nadal używać Integratora Danych do kopiowania danych pomiędzy dwoma środowiskami. Klienci, którzy po migracji połączą dane w jedno środowisko, nie będą już musieli integrować danych, ponieważ wszystkie dane będą znajdować się w jednej bazie danych.

## <a name="will-customer-isv-solutions-automatically-be-migrated"></a>Czy rozwiązania ISV klientów zostaną automatycznie zmigrowane?

Doświadczenie migracji dla każdego rozwiązania niezależnego dostawcy oprogramowania (ISV) będzie się różnić w zależności od metody integracji rozwiązania. Microsoft będzie ściśle współpracował z dostawcami usług internetowych, aby zapewnić płynne przejście do infrastruktury finansowej i operacyjnej. Wiele rozwiązań ISV jest zbudowanych na Dataverse poprzez wykorzystanie możliwości Microsoft Power Platform. Rozwiązania te zależą od integracji Dataverse między środowiskiem Dynamics 365 Human Resources a środowiskiem Dataverse. Integracja z Dataverse jest wycofywana w ramach łączenia infrastruktury. W infrastrukturze finansowej i operacyjnej planowane są nowe mapy podwójnego zapisu, które zastąpią funkcjonalność integracji z Dataverse.

## <a name="how-will-the-data-integrator-that-moves-data-between-dynamics-365-human-resources-and-other-dynamics-365-apps-be-affected"></a>Jak wpłynie to na Integrator Danych, który przenosi dane pomiędzy Dynamics 365 Human Resources i innymi aplikacjami Dynamics 365?

Po przejściu do infrastruktury finansowej i operacyjnej klienci będą musieli nadal integrować dane między tymi dwoma środowiskami. Klienci mogą nadal używać Integratora Danych do wykonywania tych zadań migracji danych. Klienci, którzy zdecydują się na oddzielenie środowiska Dynamics 365 Human Resources od istniejącego środowiska aplikacji finansowych i operacyjnych, będą musieli kontynuować integrację środowisk, aby dane były dostępne w obu środowiskach. W przypadku klientów, którzy połączą te dwa środowiska w jedno, integracja między nimi nie będzie już wymagana.

## <a name="how-will-data-be-moved-between-dynamics-365-human-resources-on-the-finance-and-operations-infrastructure-and-dataverse-after-the-migration"></a>W jaki sposób dane będą przenoszone między Dynamics 365 Human Resources na infrastrukturze finansowo-operacyjnej a Dataverse po migracji?

Obecna integracja Dataverse pomiędzy Dynamics 365 Human Resources i Dataverse jest wycofywana jako część infrastruktury finansowej i operacyjnej. Planuje się wprowadzenie map dual-write, aby mapować jednostki finansowe i operacyjne do tabel Dataverse. Klienci będą musieli zdecydować, które mapy podwójnego zapisu są wymagane w ich implementacji. Zalecamy, aby w przypadku integracji i rozwiązań ISV używać tabel wirtualnych, chyba że istnieje konkretna potrzeba biznesowa, aby dane były powielane w Dataverse w celu uruchomienia logiki biznesowej.

## <a name="how-does-the-migration-affect-dataverse-extensions-for-dynamics-365-human-resources"></a>Jak migracja wpływa na rozszerzenia Dataverse dla Dynamics 365 Human Resources?

Klienci będą musieli przeprowadzić migrację do środowiska piaskownicy przed migracją swojego środowiska produkcyjnego. Kiedy klienci migrują swoje środowisko piaskownicy, będą musieli stworzyć kopię swojego środowiska Dataverse, aby połączyć się z nowym migrowanym środowiskiem finansów i operacji. Zalecamy, aby klient skopiował zarówno dane, jak i rozwiązania dla danego środowiska, tak aby odpowiadały one aktualnemu środowisku produkcyjnemu klienta.

Kiedy klienci będą gotowi do migracji swojego produkcyjnego środowiska Dynamics 365 Human Resources, Microsoft automatycznie przeniesie bazę danych i magazyn Azure Blob. Zmigrowana baza danych i magazyn wskażą nowemu środowisku w infrastrukturze finansowej i operacyjnej to samo produkcyjne środowisko Dataverse. Zanim dane będą mogły być dalej kopiowane do Dataverse, klienci będą musieli włączyć wszystkie mapy podwójnego zapisu, które są wymagane dla ich integracji, rozszerzeń i rozwiązań ISV zbudowanych na Dataverse.

## <a name="will-microsoft-power-platform-components-that-were-built-for-dynamics-365-human-resources-automatically-work-after-the-infrastructure-migration-is-completed"></a>Czy komponenty Microsoft Power Platform, które zostały zbudowane dla Dynamics 365 Human Resources, będą automatycznie działać po zakończeniu migracji infrastruktury?

Aplikacje tworzone w Power Apps, przepływy tworzone w Power Automate oraz inne modyfikacje Microsoft Power Platform są jak rozszerzenia Dataverse. Podczas migracji środowisk produkcyjnych klientów nie ma wpływu na środowiska Dataverse, w tym na wszelkie rozszerzenia. Aplikacje, przepływy i inne dostosowania Power Microsoft Platform powinny nadal działać, nie wymagając dodatkowej konfiguracji.

## <a name="what-will-happen-to-dataverse-virtual-table-entities-for-dynamics-365-human-resources-during-the-migration"></a>Co stanie się z wirtualnymi encjami tabel Dataverse dla Dynamics 365 Human Resources podczas migracji?

Kiedy klienci migrują swoje środowisko Dynamics 365 Human Resources do infrastruktury finansowej i operacyjnej, środowisko to pozostanie połączone ze środowiskiem Dataverse, które jest obecnie połączone z Dynamics 365 Human Resources. Tabele wirtualne Dataverse, które zostały wygenerowane w środowisku, będą nadal działać, nie wymagając dodatkowej konfiguracji. Tabele wirtualne mogą wymagać regeneracji w środowisku Dataverse, które jest połączone z istniejącym środowiskiem finansowym i operacyjnym klienta.

## <a name="how-will-an-integration-that-uses-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-work-after-the-infrastructure-merge-is-completed"></a>Jak będzie działać integracja, która wykorzystuje API systemu śledzenia kandydatów (ATS), API płac, wirtualne tabele Dataverse dla Dynamics 365 Human Resources lub inne jednostki w Dataverse Web API po zakończeniu łączenia infrastruktury?

Kiedy klienci migrują swoje środowisko Dynamics 365 Human Resources do infrastruktury finansowej i operacyjnej, środowisko to pozostanie połączone ze środowiskiem Dataverse, które jest obecnie połączone z Dynamics 365 Human Resources. Wszelkie integracje, które zostały stworzone w oparciu o Dataverse Web API, będą nadal działać po zakończeniu migracji.

## <a name="our-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-it-still-be-applied-after-the-infrastructure-migration-is-completed"></a>Moja organizacja skonfigurowała niestandardowe zabezpieczenia w Dynamics 365 Human Resources. Czy będzie ona nadal stosowana po zakończeniu migracji infrastruktury?

Tak, niestandardowe konfiguracje zabezpieczeń zostaną uwzględnione w migracji danych.

## <a name="will-workflows-in-dynamics-365-human-resources-automatically-be-migrated"></a>Czy przepływy pracy w Dynamics 365 Human Resources zostaną automatycznie zmigrowane?

Tak, konfiguracje przepływów pracy, historia przepływów i bieżące przepływy w toku zostaną przeniesione do połączonej infrastruktury.

## <a name="will-saved-views-in-dynamics-365-human-resources-automatically-be-migrated"></a>Czy zapisane widoki w Dynamics 365 Human Resources zostaną automatycznie zmigrowane?

Tak, zapisane widoki zostaną przeniesione do połączonej infrastruktury.

## <a name="will-features-that-are-enabled-in-dynamics-365-human-resources-automatically-be-available-after-the-infrastructure-merge"></a>Czy funkcje włączone w Dynamics 365 Human Resources będą automatycznie dostępne po scaleniu infrastruktury?

- W przypadku klientów korzystających z modułu **Human Resources** funkcje dostępne tylko w Dynamics 365 Human Resources będą zarządzane poprzez Zarządzanie cechami. Zazwyczaj te funkcje nie są domyślnie włączone. Wszystkie funkcje, które muszą być domyślnie włączone, zostaną udokumentowane.
- Dla klientów, którzy korzystają z Dynamics 365 Human Resources, funkcje będą dostępne w infrastrukturze. Wszystkie funkcje, które nie są dostępne, zostaną udokumentowane. Każdy klucz zarządzania cechami, który jest włączony w obecnym środowisku Dynamics 365 Human Resources, będzie włączony w połączonej infrastrukturze. Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](/fin-ops/get-started/feature-management-overview.md).

## <a name="what-happens-to-byod-databases-during-the-migration"></a>Co dzieje się z bazami danych BYOD podczas migracji?

Konfiguracje importu i eksportu dla przyniesionej własnej bazy danych (BYOD) zostaną przeniesione do infrastruktury finansowej i operacyjnej.

## <a name="is-there-an-impact-on-the-azure-region-when-the-customer-environment-is-migrated"></a>Czy migracja środowiska klienta ma wpływ na region Azure?

Środowisko Dynamics 365 Human Resources pozostanie na czas migracji w tym samym regionie Azure. Jeśli zaistnieje potrzeba przeniesienia środowiska do innego regionu Azure, klienci będą musieli wykonać standardowe kroki migracji do nowego regionu po zakończeniu migracji.

## <a name="what-happens-to-azure-data-lakes-during-the-migration"></a>Co dzieje się z jeziorami danych Azure podczas migracji?

Każdy eksport, który jest obecnie skonfigurowany dla Azure Data Lake w aplikacjach finansowych i operacyjnych, zachowa tę samą konfigurację po migracji.

> [!NOTE]
> Aby kontynuować zapisywanie danych ze środowiska Human Resources do Dataverse, trzeba będzie włączyć mapy podwójnego zapisu.

Klienci, którzy chcą eksportować dane dotyczące zasobów ludzkich do jeziora danych, mogą włączyć tę funkcję po zakończeniu migracji do infrastruktury finansowej i operacyjnej. Aby uzyskać więcej informacji, zobacz Temat [Struktury danych — Centrum architektury](/azure/architecture/data-guide/scenarios/data-lake) Azure.

Klienci mogą połączyć wiele środowisk finansowych i operacyjnych z tym samym jeziorem danych. Każde środowisko będzie jednak wskazywało na inny folder i kontener. Klienci, którzy planują późniejsze łączenie środowisk, powinni dokładnie zaplanować swoje podejście.
 
## <a name="what-migration-will-be-required-if-a-customer-is-currently-using-the-human-resources-module"></a>Jaka migracja będzie wymagana, jeśli klient używa obecnie modułu HR?

Klienci korzystający z modułu **Human Resources** otrzymają nowe funkcje Dynamics 365 Human Resources, które zostaną zastosowane w ich środowisku poprzez standardowy proces aktualizacji One Version. Klienci mogą spodziewać się nowych funkcji w swoich środowiskach, gdy będą one dostępne w każdej aktualizacji. Klienci mogą korzystać z zarządzania cechami, aby je włączyć. Klienci powinni zaplanować walidację tych nowych funkcji za pomocą procesów, które już posiadają i których używają do walidacji innych aktualizacji swojego środowiska.

## <a name="what-will-happen-to-custom-integrations-to-external-systems"></a>Co stanie się z niestandardowymi integracjami z systemami zewnętrznymi?

Klienci będą musieli zmigrować swoje integracje do środowiska finansowego i operacyjnego. Ponieważ punkt końcowy tego środowiska jest inny, klienci mogą być zmuszeni do aktualizacji lub zmiany integracji, tak aby wskazywały one na nowe środowisko. Zadanie to będzie przede wszystkim procesem ręcznym, a wymagane zmiany będą zależały od architektury integracji. Klienci powinni współpracować z partnerem firmy Microsoft w celu określenia najlepszego sposobu przeniesienia integracji.

## <a name="what-will-happen-to-microsoft-power-platform-dataverse-extensions-if-customers-merge-a-dynamics-365-human-resources-environment-with-an-existing-finance-and-operations-environment"></a>Co stanie się z rozszerzeniami Microsoft Power Platform (Dataverse), jeśli klienci połączą środowisko Dynamics 365 Human Resources z istniejącym środowiskiem finansowym i operacyjnym?

Jeśli klienci zdecydują się połączyć środowisko Dynamics 365 Human Resources i istniejące środowisko finansów i operacji w jedną instancję Dataverse po migracji, ich środowiska Dataverse muszą zostać połączone w ramach procesu łączenia. Zadanie to będzie wymagało ponownego rozmieszczenia w nowym środowisku wszystkich aplikacji utworzonych przy użyciu Power Apps oraz wszelkich innych dostosowań.

## <a name="what-will-happen-to-documents-during-the-migration"></a>Co stanie się z dokumentami podczas migracji?

Kiedy klienci migrują swoje środowisko Dynamics 365 Human Resources do infrastruktury finansowo-operacyjnej, dokumenty pozostaną w istniejącym magazynie dokumentów i zostaną automatycznie zmapowane do nowego środowiska w infrastrukturze finansowo-operacyjnej.

W przyszłym wydaniu zostaną udostępnione nowe jednostki danych. Po wprowadzeniu tej zmiany klienci, którzy zdecydują się połączyć swoje środowisko Dynamics 365 Human Resources z istniejącym środowiskiem finansowym i operacyjnym, będą mogli eksportować dokumenty i przenosić je do istniejącego środowiska.

## <a name="after-the-migration-what-happens-to-the-batch-jobs-that-were-configured-in-dynamics-365-human-resources"></a>Co stanie się po migracji z zadaniami wsadowymi, które zostały skonfigurowane w Dynamics 365 Human Resources?

Zadania wsadowe będą musiały zostać przekonfigurowane w środowisku finansowym i operacyjnym. Klienci będą musieli ocenić każde zadanie wsadowe i porównać je z aktualną listą zadań wsadowych w środowisku finansowym i operacyjnym. Klienci powinni również przeanalizować ogólny harmonogram wsadowy po połączeniu dwóch zestawów zadań wsadowych, aby określić, czy należy wprowadzić zmiany w harmonogramie wsadowym, priorytetach lub grupach wsadowych.

## <a name="how-will-the-migration-affect-the-lcs-project-for-dynamics-365-human-resources"></a>Jak migracja wpłynie na mój projekt LCS dla Dynamics 365 Human Resources?

Klienci będą musieli stworzyć nowy projekt Microsoft Dynamics Lifecycle Service (LCS), wybrać aplikacje finansowe i operacyjne jako produkt oraz **wdrożenie** jako typ projektu. Dodatkowo, podczas tworzenia projektu LCS dostępne jest nowe pole dotyczące typu podprojektu. Klienci będą musieli wybrać opcję migracji Dynamics 365 Human Resources, aby przenieść istniejący projekt Human Resources LCS do infrastruktury finansowej i operacyjnej.

Cechy projektów LCS dotyczących finansów i operacji różnią się od cech projektów LCS dotyczących zasobów ludzkich.

Aby zacząć działać, nowi klienci będą musieli wykonać następujące zadania:

- Zakończenie procesu wdrażania projektu.
- Uzupełnij metodologię.
- Wypełnij formularz szacunkowy dotyczący subskrypcji.
- Zakończ proces gotowości do działania.

## <a name="how-will-the-business-process-modeler-be-migrated"></a>W jaki sposób zostanie zmigrowany modeler procesów biznesowych?

Klienci będą musieli wyeksportować swoją bibliotekę Business process modeler z projektu Human Resources LCS i zaimportować ją do finansowego i operacyjnego projektu LCS. Ponadto klienci będą musieli zaktualizować ustawienia pomocy w aplikacji, tak aby wskazywały one na nowy projekt LCS.

## <a name="how-will-the-service-update-process-be-affected-by-the-migration"></a>Jaki wpływ na proces aktualizacji usług będzie miała migracja?

Po migracji klienci będą mieli znacznie większą elastyczność w zakresie zarządzania cyklem życia aplikacji (ALM) i aktualizacji usług. Aktualizacje usług nie będą już automatycznie stosowane w środowiskach Human Resources. Zamiast tego, usługa będzie realizować procesy i funkcje aktualizacji usługi One Version, a opcje konfiguracji aktualizacji poprzez LCS zostaną włączone.

## <a name="will-customers-be-eligible-for-fasttrack-assistance-with-the-infrastructure-merge"></a>Czy klienci będą mogli skorzystać z pomocy FastTrack przy łączeniu infrastruktury?

Microsoft wciąż określa, jakie narzędzia i zasoby będą dostępne w FastTrack, aby pomóc w połączeniu.

## <a name="licensing-impact"></a>Wpływ na licencje

Aby uzyskać więcej informacji na temat wpływu na licencjonowanie, zobacz [Scalanie infrastruktury Dynamics 365 Human Resources](hr-infrastructure-merge.md#licensing).
