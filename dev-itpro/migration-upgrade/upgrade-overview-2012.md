---
title: Uaktualnianie programu Dynamics AX 2012 do programu Dynamics 365 for Finance and Operations Enterprise Edition
description: "W tym temacie opisano proces, który mogą zastosować obecni użytkownicy systemu Microsoft Dynamics AX 2012, aby przenieść swoje dane i kod źródłowy do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition."
author: tariqbell
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 13507fcf9c0d626709aeb4e00a8632411204c20f
ms.contentlocale: pl-pl
ms.lasthandoff: 06/15/2017

---

# Uaktualnianie programu Microsoft Dynamics AX 2012 do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition
<a id="upgrade-microsoft-dynamics-ax-2012-to-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition" class="xliff"></a>

[!include[banner](../includes/banner.md)]

W aktualizacji platformy nr 8 program Microsoft Dynamics 365 for Finance and Operations Enterprise Edition oferuje ścieżkę uaktualnienia, którą mogą wykorzystać użytkownicy obecnego systemu Microsoft Dynamics AX 2012, aby przenieść swoje dane i kod źródłowy do programu Finance and Operations. Proces uaktualniania opiera się na następujących elementach:

- Narzędzia pomagające przenieść istniejący kod źródłowy niestandardowych aplikacji z systemu AX 2012.
- Proces uaktualniania danych, który umożliwia przeniesienie baz danych. Dzięki temu można uaktualnić całą historię transakcji.

## Przegląd
<a id="overview" class="xliff"></a>

Cały proces uaktualniania można zobrazować w formie trzech głównych faz: Analizowanie, Wykonywanie i Weryfikowanie.

Poniższy diagram przedstawia kompletny proces uaktualniania oraz działania, które zaliczamy do poszczególnych faz. 

![Projekt uaktualniania](./media/upgrade-process.png)

## Analizuj
<a id="analyze" class="xliff"></a>

Działania w fazie Analizowanie pomagają oszacować pracochłonność uaktualniania. Ułatwiają one także przygotowanie planu projektu. Działania te można wykonać przed zakupem oprogramowania Finance and Operations. Ułatwią one podjęcie racjonalnej decyzji zakupowej poprzez dostarczenie informacji o nakładzie pracy i zasobach, które będą wymagane.

### Zamówienie publicznej wersji zapoznawczej w usłudze LCS
<a id="sign-up-for-a-public-preview-in-lcs" class="xliff"></a>

Aby wykonać czynności analityczne przed zakupem produktu Finance and Operations, można się zarejestrować na publiczną wersję zapoznawczą. Publiczna wersja zapoznawcza pozwala wdrożyć własne środowisko oprogramowania Finance and Operations. Zapewnia także dostęp do narzędzi w usłudze Microsoft Dynamics Lifecycle Services (LCS), które służą do oceniania posiadanego środowiska systemu AX 2012 i istniejącego niestandardowego kodu źródłowego.

Jeżeli masz w usłudze LCS istniejący projekt dla systemu AX 2012, i tak musisz się zarejestrować na dodatkowy nowy projekt, aby uzyskać możliwość oceny rozwiązania Finance and Operations.

Aby uzyskać informacje dotyczące sposobu uzyskania publicznej wersji zapoznawczej dla klientów, przejdź do strony https://mbs.microsoft.com/customersource/global/AX/news-events/news/Microsoft_Dynamics_AX_Public_Preview.

Aby uzyskać informacje dotyczące sposobu uzyskania publicznej wersji zapoznawczej dla partnerów, przejdź do strony https://mbs.microsoft.com/partnersource/global/news-events/news/Microsoft_Dynamics_AX_Public_Preview.

Należy pamiętać, że ta publiczna wersja zapoznawcza różni się od [30-dniowej wersji próbnej](https://aka.ms/D365OperationTrials). 30-dniowe wersje próbne zapewniają wdrożone wystąpienia programu Finance and Operations, które umożliwiają poznawanie i ocenianie przydatności aplikacji. Natomiast czynności w fazie Analizowanie wymagają pełnej funkcjonalności i narzędzi dostępnych w usłudze LCS.

### Wybór metodyki uaktualniania
<a id="select-the-upgrade-methodology" class="xliff"></a>
W nowym projekcie usługi LCS wybierz metodologię projektu **Uaktualnienia systemu AX 2012 do programu Dynamics 365 for Operations**. Ta metodyka została opracowana specjalnie dla posiadaczy systemu AX 2012, którzy dokonują uaktualnienia. Szczegółowo opisuje wszystkie trzy fazy i zawiera łącza do całej pomocniczej dokumentacji o procesie.

![Metodologia uaktualniania(./media/methodology.png)
 
### Uruchamianie analizatora uaktualniania
<a id="run-the-upgrade-analyzer" class="xliff"></a>
Narzędzie analizy uaktualnienia działa w kontekście istniejącego środowiska systemu AX 2012 i określa zadania, które należy wykonać w celu przygotowania środowiska systemu AX 2012, aby zwiększyć płynność i obniżyć koszty uaktualniania:

- **Oczyszczanie danych** — Ten proces pomaga zidentyfikować dane, które można usunąć, nie powodując utraty funkcjonalności. Narzędzie identyfikuje różne typy danych, które można zredukować poprzez wykonanie procesu oczyszczania. Dla każdego typu danych jest podane wyjaśnienie dotyczące wpływu oczyszczania. Na tej podstawie można zdecydować, czy ma zostać wykonany proces oczyszczania. Część kosztu subskrypcji rozwiązania Finance and Operations zależy od rozmiaru bazy danych. W związku z tym zmniejszając rozmiar bazy, zmniejszasz ten składnik kosztu subskrypcji, a do tego możesz również skrócić czas potrzebny na przeprowadzenie faktycznego uaktualniania. Mniejsza baza danych pomaga zagwarantować szybsze uaktualnianie.
- **Konfiguracja SQL** — Ten proces bada konfigurację oprogramowania SQL i zaleca optymalizacje. Upewnij się, że oprogramowanie SQL działa optymalnie. Ten proces pomaga skrócić czas potrzebny na przeprowadzenie faktycznego uaktualniania.
- **Przestarzałe funkcje** — Ten proces identyfikuje funkcje, których obecnie używasz, ale które nie są dostępne w programie Finance and Operations. W związku z tym proces pomaga szybko wykryć luki w funkcjonalności. Podpowiada również alternatywne rozwiązania.

Ponadto w ramach tego etapu należy zainstalować aktualizację KBXXXXXXX w środowisku systemu AX 2012. Ta poprawka zawiera listę kontrolną czynności, które należy wykonać przed uaktualnieniem. W środowisku systemu AX 2012 ta lista kontrolna może służyć do wprowadzania danych, które będą wymagane w procedurze uaktualniania. Na przykład w jednym zadaniu na liście kontrolnej czynności poprzedzających uaktualnianie należy podać dane logowania do usługi Microsoft Azure Active Directory (Azure AD) dla każdego bieżącego użytkownika systemu AX 2012, tak aby każdy użytkownik mógł się logować do programu Finance and Operations.

Dane wyjściowe tego kroku stają się strumieniem pracy w planie projektu uaktualniania dla administratorów systemu AX 2012.

Aby uzyskać więcej informacji, zobacz [Analizowanie: Planowanie pracy migracji za pomocą analizatora uaktualnienia](upgrade-analyzer-tool.md).

### Uruchamianie narzędzi szacowania uaktualnienia kodu
<a id="run-the-code-upgrade-estimation-tools" class="xliff"></a>
W tym kroku kod źródłowy z systemu AX 2012 jest konwertowany na nowy format, po czym są wyświetlane informacje zwrotne o konfliktach, które programista musi później rozwiązać. Ten krok stanowi podstawę do szacowania kosztów uaktualnienia kodu źródłowego.

Aby wykonać ten krok, należy wyeksportować kod z systemu AX 2012 za pomocą operacji eksportu magazynu modeli i przekazać go do narzędzia uaktualniania kodu w usłudze LCS. Narzędzie uaktualniania kodu wygeneruje uaktualnioną wersję kodu źródłowego oraz raport o pozostałych konfliktach, które należy rozwiązać. Następnie firmowy programista może przejrzeć uaktualniony kod i raport i na tej podstawie określić nakład pracy niezbędny do uaktualnienia całego kodu.

Dane wyjściowe tego kroku są strumieniem pracy w planie projektu uaktualniania dla programistów systemu Microsoft Dynamics AX.

Aby uzyskać więcej informacji, zobacz [Analizowanie: Szacowanie pracochłonności uaktualniania kodu](analyze-code-upgrade.md).

### Wdrażanie środowiska demonstracyjnego
<a id="deploy-a-demo-environment" class="xliff"></a>
Środowiska demonstracyjne są domyślnymi środowiskami zawierającymi dane demonstracyjne (nie własne dane firmy) i standardowy kod (bez personalizacji). Zalecamy wdrożenie środowiska demonstracyjnego, aby ocenić nowe funkcje oraz wykonać podstawową analizę luk w standardowych procesach, które są używane w systemie AX 2012, ale mogły ulec zmianie w programie Finance and Operations. Te środowiska demonstracyjne można wdrożyć na platformie Azure lub pobrać jako maszyny wirtualne (VM) do uruchomienia na własnym sprzęcie. W przypadku ich wdrożenia w usłudze Azure należy podać dane subskrypcji usługi Azure, ponieważ wciąż używasz projektu w publicznej wersji zapoznawczej i nie masz jeszcze wykupionej subskrypcji programu Finance and Operations.

Dane wyjściowe tego kroku są strumieniem pracy w planie projektu uaktualniania dla użytkowników funkcjonalnych lub biznesowych w firmie.

Aby uzyskać więcej informacji, zobacz [Analizowanie: Wdrażanie środowiska piaskownicy](analysis-sandbox.md)

### Tworzenie planu projektu
<a id="create-a-project-plan" class="xliff"></a>
Metodyka uaktualniania zawiera szablon planu projektu. W tym kroku dane wyjściowe z poprzednich kroków fazy Analizowanie są używane do wypełnienia planu projektu uaktualniania. Plan projektu zawiera również wszystkie szczegóły testowania: testów uaktualniania danych, testów przełączenia i iteracji sesji testów funkcjonalnych, a także szczegółowe informacje o różnych przypisaniach zasobów dla tych zadań.

Na tym etapie plan projektu zawiera informacje, które pomagają określić czas i koszty uaktualnienia do programu Finance and Operations.

## Wykonaj
<a id="execute" class="xliff"></a>
Podczas fazy Wykonanie realizujesz zadania zaplanowane w fazie Analizowanie. Aby przejść do fazy Wykonanie, należy wykupić subskrypcję usługi Finance and Operations oraz posiadać dostępne zasoby, które mogą pracować nad uaktualnieniem.

### Przechodzenie do projektu implementacji w usłudze LCS
<a id="switch-to-the-lcs-implementation-project" class="xliff"></a>
Projekt w publicznej wersji zapoznawczej używany w fazie Analizowanie spełnił swój cel. Teraz można go usunąć. W pozostałych krokach jest potrzebny tylko plan projektu utworzony w ostatnim kroku fazy Analizowanie.

Przy zakupie subskrypcji usługi Finance and Operations otrzymasz szczegółowe informacje dotyczące subskrybowania nowego projektu w usłudze LCS. Ten projekt jest znany jako projekt implementacji i będzie nowym trwałym projektem LCS związanym z Twoją subskrypcją, dopóki posiadasz tę subskrypcję. Ten projekt różni się od projektu w publicznej wersji zapoznawczej tym, że jest zarządzany przez firmę Microsoft. W związku z tym ma następujące cechy:

- Wszystkie środowiska w projekcie są umieszczone w systemie Azure.
- Subskrypcja usługi Azure skojarzona z projektem jest zarządzana przez firmę Microsoft. W związku z tym koszty użytkowania platformy Azure nie są osobno fakturowane. Są one wliczane do subskrypcji oprogramowania Finance and Operations.
- Środowisko produkcyjne w projekcie jest prowadzone przez firmę Microsoft. Z tego względu wdrożenia kodu źródłowego, uaktualnienia i czynności konserwacyjne w infrastrukturze są realizowane bezpośrednio przez firmę Microsoft, a nie pracowników firmy. 

### Wykonanie zadań przygotowawczych w systemie AX 2012
<a id="perform-the-ax-2012-preparation-tasks" class="xliff"></a>
Wykonaj zadania, które zostały zidentyfikowane przez narzędzie analizy uaktualnienia i udokumentowane w planie projektu uaktualniania. Zadania te muszą wykonać administrator systemu Microsoft Dynamics AX i administratora baz danych (DBA).

[Uaktualnianie danych z systemu AX 2012 do programu Dynamics 365 for Operations — lista kontrolna czynności poprzedzających uaktualnienie do wykonania w systemie AX 2012](prepare-data-upgrade.md)

### Wykonanie uaktualnienia kodu źródłowego
<a id="perform-code-upgrade" class="xliff"></a>
Wykonaj zadania, które zostały zaplanowane w fazie Analizowanie w kroku szacowania uaktualnienia kodu. Te zadania muszą wykonać programiści.

Od tej chwili należy zablokować możliwość wprowadzania zmian w kodzie źródłowym w systemie AX 2012. Dopuszczalne są tylko zmiany kodu w sytuacjach awaryjnych. W razie dokonania modyfikacji należy ją ręcznie wprowadzić również w nowym kodzie źródłowym.

### Tworzenie nowego kodu źródłowego
<a id="develop-new-code" class="xliff"></a>
Wykonaj zadania z analizy luk, która została przeprowadzona w fazie Analizowanie w kroku „Wdrażanie środowiska demonstracyjnego”. Te zadania będą prawdopodobnie kombinacją zadań funkcjonalnych, które definiują konfigurację, i zadań programistycznych do personalizacji, które są związane z wprowadzaniem nowych funkcji.

### Uaktualnianie danych (środowisko projektowe)
<a id="data-upgrade-development-environment" class="xliff"></a>
Po ukończeniu zadań uaktualniania kodu można po raz pierwszy uaktualnić bazę danych systemu AX 2012 do formatu Finance and Operations. Pierwsze uaktualnienie następuje w środowisku projektowym, dzięki czemu można łatwiej usunąć lub debugować problemy znalezione na tym etapie. W środowisku projektowym można natychmiast debugować problem, poprawić kod źródłowy i ponownie uruchomić uaktualnianie w ciągu minut. Większe środowiska piaskownicy nie zapewniają tej dynamiki i potrzeba co najmniej kilku godzin, aby debugować i usunąć problemy, zaktualizować kod, wdrożyć zaktualizowany kod i ponownie uruchomić uaktualnianie.

Poniższa ilustracja pokazuje ten proces. Wystarczy utworzyć kopię zapasową bazy danych systemu AX 2012, przekazać ją do systemu Azure, przywrócić do środowiska Finance and Operations, a następnie uruchomić uaktualnianie danych.

![Uaktualnianie danych w środowisku projektowym](./media/data-upgrade-dev.png)
 
Uaktualnianie danych odbywa się za pośrednictwem specjalnego wdrażalnego pakietu. Ten sam mechanizm jest używany do wdrażania nowego kodu źródłowego usługi Finance and Operations z jednego środowiska do innego.

Bazowa struktura służąca do konwertowania danych w bazie danych w trakcie tego procesu jest w dużej części taka sama, jak struktura uaktualniania w systemie AX 2012 oparta na zadaniach wsadowych w języku X++ używających klas **ReleaseUpdatexxx**.

Aby uzyskać szczegółowe informacje, zobacz [Uaktualnianie danych z systemu AX 2012 do programu Dynamics 365 for Operations w środowisku projektowym](data-upgrade-2012.md).

### Uaktualnianie danych (środowiska piaskownicy)
<a id="data-upgrade-sandbox-environments" class="xliff"></a>
Po zakończeniu uaktualniania danych w środowisku projektowym ten sam proces można wykonać w środowisku piaskownicy. Środowisko piaskownicy jest środowiskiem, gdzie użytkownicy biznesowi i członkowie zespołu funkcjonalnego mogą testować procesy biznesowe za pomocą zaktualizowanych danych i kodu źródłowego systemu AX 2012.

Na poniższej ilustracji przedstawiono proces wykonywania uaktualniania danych w środowisku piaskownicy. Różnica polega na tym, że zamiast tradycyjnego narzędzia wykonywania kopii zapasowych języka SQL jest używane narzędzie bacpac. To narzędzie jest wymagane do konwertowania danych między programami Microsoft SQL Server i Azure SQL Database. Jest to standardowe narzędzie języka SQL i działa nie tylko dla modułu Finance and Operations.

![Uaktualnianie danych w środowisku piaskownicy](./media/data-upgrade-sandbox.png)

Aby uzyskać szczegółowe informacje, zobacz [Uaktualnianie danych z systemu AX 2012 do programu Dynamics 365 for Operations w środowisku piaskownicy](upgrade-data-sandbox.md).
 
## Sprawdzanie poprawności
<a id="validate" class="xliff"></a>
Po przejściu do fazy Weryfikowanie będziesz mieć dostępne środowiska zawierające Twój uaktualniony niestandardowy kod źródłowy i uaktualnione dane. Ta faza opisuje proces sprawdzania poprawności oraz testowania, czy uaktualnione środowisko działa zgodnie z oczekiwaniami. Opisuje również proces przygotowywania do rozpoczęcia eksploatacji.

### Wykonywanie testu przełączenia i tworzenie planu przełączenia
<a id="perform-cutover-testing-and-create-a-cutover-plan" class="xliff"></a>
Określenie _przełączenie_ służy tutaj do opisania końcowego procesu rozpoczęcia eksploatacji nowego systemu. Ten proces składa się z zadań, które następują po wyłączeniu systemu AX 2012, a przed włączeniem programu Finance and Operations. 

Testowanie ma na celu przećwiczenie procesu przełączenia. Dzięki temu pomagasz zagwarantować, że wszystkie osoby biorące udział w faktycznym przełączeniu przed rozpoczęciem eksploatacji będą odpowiednio przeszkolone.

Istnieją dwa główne strumienie pracy:

- **Techniczny strumień pracy** — Ten strumień pracy to proces wykonywania uaktualniania danych. Firma wymusi limit dozwolonego czasu przestoju. Podczas tego przestoju nie będzie dostępne oprogramowanie AX 2012 ani Finance and Operations. W technicznym strumieniu pracy może być konieczne dostrojenie procedury uaktualniania danych pod kątem wydajności, tak aby spełniała limit czasu przestojów obowiązujący w firmie. 
- **Funkcjonalny strumień pracy** — Po uaktualnieniu danych należy wykonać kilka zadań konfiguracyjnych w środowisku Finance and Operations. Wszystkie te zadania muszą być udokumentowane i skwantyfikowane oraz należy do nich przypisać zasoby, ponieważ muszą się mieścić razem z zadaniami technicznymi w limicie czasu przestojów obowiązującym w firmie.

Aby uzyskać szczegółowe informacje, zobacz 
- [Weryfikowanie: Testowanie przełączenia](upgrade-cutover-testing.md)
- [Weryfikowanie: Proces weryfikacji aplikacji](app-validation-process.md)

### Sesja testów funkcjonalnych
<a id="functional-test-pass" class="xliff"></a>
Wykonaj kompletną sesję testów funkcjonalnych dla wszystkich procesów biznesowych. Ta sesja testów będzie kompleksowym sprawdzeniem wszystkich procesów biznesowych, w których uczestniczy program Finance and Operations. Te procesy biznesowe obejmują zarówno stare procesy przeniesione z systemu AX 2012, jak i nowe procesy, w których występują nowe funkcje wprowadzone po raz pierwszy w oprogramowanie Finance and Operations. 

W zależności od jakości kodu źródłowego usuwanie problemów i ponowne testowanie może wymagać kilku iteracji sesji testów funkcjonalnych. Po rozwiązaniu problemu koniecznie przetestuj wszystkie procesy, których dotyczył problem, aby mieć pewność, że zmiana nie wpłynęła na żadne wcześniejsze ani późniejsze procesy.

Aby uzyskać szczegółowe informacje, zobacz [Weryfikowanie: Testowanie funkcjonalne](upgrade-functional-validation.md).

### Lista kontrolna czynności poprzedzających rozpoczęcie eksploatacji
<a id="pre-go-live-checklist" class="xliff"></a>
Lista kontrolna czynności poprzedzających rozpoczęcie eksploatacji to zalecana procedura, która może zmniejszyć prawdopodobieństwo wystąpienia błędów podczas końcowego przełączenia przed rozpoczęciem eksploatacji. Tydzień przed terminem rozpoczęcia eksploatacji przestań wprowadzać zmiany w systemie AX 2012 (tzn. w folderze \<moduł\>\Setup). To ograniczenie wprowadzania zmian w konfiguracji ma charakter wyłącznie proceduralny. Administratorzy systemu Microsoft Dynamics AX po prostu zgodzili się, aby w tym momencie wstrzymać wprowadzanie zmian.

Zalecamy również zaprzestanie wprowadzania zmian w kodzie źródłowym oprogramowania Finance and Operations. Nie powinny być dozwolone żadne dalsze zmiany, chyba że zostaną zweryfikowane i okaże się, że nie blokują rozpoczęcia eksploatacji.  

Po zamrożeniu możliwości wprowadzania zmian w konfiguracji i kodzie źródłowym należy wykonać uaktualnianie danych po raz ostatni przed przełączeniem. W ten sposób możesz się upewnić, że wszystko nadal działa poprawnie. 

Aby uzyskać szczegółowe informacje, zobacz [Weryfikowanie: Przygotowanie do rozpoczęcia eksploatacji](upgrade-go-live-prep.md).



### Obsługiwane ścieżki uaktualniania
<a id="supported-upgrade-paths" class="xliff"></a>
Według stanu na czerwiec 2017 roku uaktualnienia do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition w wersji 0617 można dokonać z systemu Microsoft Dynamics AX 2012 R3. Obsługiwane są wszystkie aktualizacje zbiorcze (CU) systemu AX 2012 R3.

Uaktualnienia z systemów Microsoft Dynamics AX 2012 R2 i Microsoft Dynamics AX 2012 RTM obecnie nie są obsługiwane. Obsługa zostanie dodana w drugiej połowie 2017 roku.

Obsługiwane jest uaktualnianie tylko do chmurowej wersji oprogramowania Finance and Operations. Uaktualnianie do wersji lokalnej nie jest obsługiwane. Obsługa uaktualniania do wersji lokalnej zostanie dodana w drugiej połowie 2017 roku.

