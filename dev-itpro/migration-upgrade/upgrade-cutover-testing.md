---
title: "Testowania przełączenia po uaktualnieniu"
description: "W tym temacie wyjaśniono, jak testować zadania następujące po wyłączeniu systemu AX 2012, ale przed włączeniem programu Dynamics 365 for Finance and Operations Enterprise Edition."
author: tariqbell
manager: AnnBe
ms.date: 05/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations, UnifiedOperations, Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 711ad5cc3aafacf209704349effb4e08019205ac
ms.contentlocale: pl-pl
ms.lasthandoff: 06/15/2017

---

# Uaktualnianie testowania przełączenia
<a id="upgrade-cutover-testing" class="xliff"></a>

[!include[banner](../includes/banner.md)]

[!include[upgrade banner](../includes/upgrade-banner.md)]

*Przełączenie* to określenie stosowane do końcowego procesu rozpoczęcia eksploatacji nowego systemu. Ten proces przełączenia obejmuje zadania wykonywane po wyłączeniu systemu Microsoft Dynamics AX 2012, ale przed włączeniem oprogramowania Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. Celem testowania przełączenia po uaktualnieniu jest przećwiczenie procesu przełączenia, co ma zapewnić płynne wykonywanie czynności przez wszystkie osoby uczestniczące w faktycznym przełączeniu przed rozpoczęciem eksploatacji.

W procesie przełączenia istnieją dwa główne strumienie pracy:

- **Techniczny strumień pracy** — Ten strumień pracy obejmuje proces wykonywania uaktualniania danych. Firma wymusi limit dozwolonego czasu przestoju. Podczas tego przestoju nie będzie dostępne oprogramowanie AX 2012 ani Finance and Operations. W tym strumieniu pracy może być konieczne dostrojenie procedury uaktualniania danych pod kątem wydajności, tak aby spełniała limit czasu przestojów obowiązujący w firmie.
- **Funkcjonalny strumień pracy** — Ten strumień pracy obejmuje zadania konfiguracji wykonywane po zakończeniu uaktualniania danych. Wszystkie te zadania muszą być udokumentowane i skwantyfikowane oraz należy do nich przypisać zasoby, ponieważ oba strumienie pracy — funkcjonalny i techniczny — muszą się mieścić w limicie czasu przestojów obowiązującym w firmie.

Na poniższej ilustracji przedstawiono całościowy proces przełączenia przed rozpoczęciem eksploatacji, który będzie realizowany w środowisku produkcyjnym.

![Proces przełączenia](./media/cutover_1.png)

Ten proces przełączenia różni się od uaktualniania danych podstawowych w środowisku piaskownicy pod następującymi względami:

- Baza danych systemu AX 2012 nie jest kopiowana, a jedynie umieszczana w kopii zapasowej, po czym oryginalna baza danych jest modyfikowana. Takie rozwiązanie jest szybsze, a kopia zapasowa umożliwia wycofywanie, jeśli okaże się to konieczne.
- Ponieważ środowisko produkcyjne programu Finance and Operations ma ograniczony dostęp, zadania, które wcześniej były wykonywane w wystąpieniu piaskownicy serwera obiektów aplikacji (AOS), teraz są wykonywane przez zespół DSE firmy Microsoft. Te zadania obejmują pobranie i zaimportowanie pliku bacpac oraz uruchomienie pakietu MajorversionDataUpgrade.zip.
- Dodaliśmy następujące zadania:

    - Przeprowadzenie testu dymnego.
    - Wykonanie zadań konfigurowania aplikacji. Ten krok może być duży, w zależności od używanej funkcjonalności. W tym kroku zespół funkcjonalny konfiguruje nowe funkcje aplikacji, tak aby były gotowe do użycia w uaktualnionym systemie.
    - Zezwolenie na powrót użytkowników. Powiadom użytkowników, że uaktualnianie zostało ukończone i można ponownie używać systemu.

## Techniczny strumień pracy
<a id="technical-workstream" class="xliff"></a>

W technicznym strumieniu pracy uczestniczą różni członkowie zespołu technicznego: administrator baz danych (DBA), administrator systemu AX 2012, administratorzy serwerów oraz programiści znający oprogramowanie AX 2012 i Finance and Operations. W tym temacie wyjaśniono, które zadania są wykonywane przez poszczególne role.

Podczas testowania przełączenia zespół techniczny koncentruje się na testowaniu wydajności i niezawodność procesu uaktualniania danych, aby mieć pewność, że mieści się on w limicie czasu przestojów ustawionym w firmie. W tym procesie jest zaangażowanych wiele składników sprzętowych i programowych. Niektóre z tych składników są lokalne, a inne umieszczone w chmurze firmy Microsoft. Ponadto uczestniczy wiele elementów z niestandardowym i standardowym kodem źródłowym aplikacji. W wyniku tych testów powinno się uzyskać pewność co do skuteczności wykonania procesu przełączenia w środowisku produkcyjnym organizacji.

### Wyłączanie wystąpień serwera AOS systemu AX 2012
<a id="turn-off-the-ax-2012-aos-instances" class="xliff"></a>

W tym zadaniu uczestniczą administrator systemu AX 2012 i administratorzy serwerów.

Należy zweryfikować następujące obszary:

- **Zadania wsadowe wykonywane w czasie przełączenia** — Długotrwałe zadanie wsadowe, które już się rozpoczęło, uniemożliwi zatrzymanie systemu. Planuj z wyprzedzeniem, tak aby zatrzymać wystąpienia serwera AOS w żądanym momencie. Może być konieczne takie zaplanowanie zadań wsadowych, aby zostały ukończone pewien czas przed wyłączeniem systemu AX 2012.
- **Zintegrowane systemy** — Mogą istnieć inne systemy zintegrowane ze środowiskiem AX 2012. Systemy te trzeba uwzględnić w planie wyłączenia systemu AX 2012. Na przykład może być konieczne wyłączenie zintegrowanych systemów pewien czas przed wyłączeniem samego systemu AX 2012, tak aby zostały ukończone wszelkie pozostałe transakcje będące w toku. Wymagania dotyczące zintegrowanych systemów różnią się znacznie w zależności od firmy. Z tego względu zespół ekspertów firmy musi niezależnie zaplanować ten scenariusz.

### Tworzenie kopii zapasowej bazy danych systemu AX 2012
<a id="create-a-backup-of-the-ax-2012-database" class="xliff"></a>

W tym zadaniu uczestniczy administrator baz danych. Kopia zapasowa będzie używana w razie konieczności wycofania. Będzie również służyła przez pewien czas jako punkt odniesienia, który pokazuje stanu systemu w momencie przełączenia.

Należy zweryfikować następujące obszary:

- Ustalenie konkretnych czasów dla procesu wykonywania kopii zapasowej.
- Dostosowanie opcji wykonywania kopii zapasowej (na przykład stosowanie lub niestosowanie kompresji) w celu zagwarantowania jak najszybszego utworzenia kopii zapasowej.

### Eksportowanie bazy danych do pliku bacpac
<a id="export-the-database-to-bacpac" class="xliff"></a>

W tym zadaniu uczestniczy administrator baz danych. Produktem wyjściowym tego zadania jest plik eksportu, który zostanie przekazany do usługi Microsoft Azure dla nowego systemu.

Należy zweryfikować następujące obszary:

- Ustalenie konkretnych czasów dla procesu wykonywania kopii zapasowej.
- Optymalizacja procesu eksportu w celu zagwarantowania jego jak najszybszego działania. Optymalizacja może wymagać wykonania następujących zadań:

    - Pomiar zasobów systemowych — procesora CPU, operacji we/wy na dysku, pamięci operacyjnej — podczas eksportu.
    - W przypadku znalezienia wąskich gardeł w zasobach należy utworzyć plan minimalizujący dolegliwość tych ograniczeń. Na ogół minimalizowanie dolegliwości tych wąskich gardeł polega na przydzieleniu większej ilości potrzebnego zasobu.

### Przekazanie pliku bacpac do magazynu Azure
<a id="upload-the-bacpac-file-to-azure-storage" class="xliff"></a>

W tym zadaniu uczestniczy administrator baz danych lub administratorzy serwerów. Podczas tego zadania plik bacpac jest przenoszony do środowiska Azure.

Należy zweryfikować następujące obszary:

- Wybierz komputer, który będzie używany do przekazywania, i upewnij się, że narzędzie eksploratora magazynu Azure jest skonfigurowane i gotowe do użytku.
- Ustalenie konkretnych czasów dla procesu przekazywania poprzez ich kilkukrotne zmierzenie. Czasy przekazywania różnią się w zależności od szybkości połączenia z Internetem i od położenia geograficznego centrum przetwarzania danych Azure w odniesieniu do Twojej lokalizacji.

### Pobieranie i importowanie pliku bacpac do bazy danych Azure SQL
<a id="download-and-import-the-bacpac-file-to-the-azure-sql-database" class="xliff"></a>

Gdy to zadanie odbywa się podczas rozpoczynania eksploatacji, wykonuje je zespół DSE firmy Microsoft. Jednak podczas testowania przełączenia jest wykonywane przez administratora baz danych. Produktem wyjściowym tego zadania jest plik eksportu, który zostanie przekazany do usługi Azure dla nowego systemu.

Należy zweryfikować następujące obszary:

- Ustalenie konkretnych czasów dla procesu importu.
- Optymalizacja procesu eksportu w celu zagwarantowania jego jak najszybszego działania. Optymalizacja może wymagać wykonania następujących zadań:

    - Pomiar zasobów systemowych podczas eksportu. Oto kilka przykładów:

        - **Na komputerze serwera AOS:** procesor CPU, operacje we/wy na dysku i pamięć operacyjna
        - **W wystąpieniu bazy danych SQL Azure:** przepustowość bazy danych SQL (DTU) Parametr DTU bazy danych Azure SQL można monitorować z programu Microsoft SQL Server Management Studio na komputerze z serwerem AOS, używając widoku systemowego sys.dm_resource_stats.

    - W przypadku znalezienia wąskich gardeł w zasobach należy utworzyć plan minimalizujący dolegliwość tych ograniczeń. Na ogół minimalizowanie dolegliwości tych wąskich gardeł polega na przydzieleniu większej ilości potrzebnego zasobu. Ponieważ ten komputer jest prowadzony przez Microsoft, w razie stwierdzenia wąskiego gardła musisz przesłać wniosek do firmy Microsoft o zwiększenie ilości zasobów.

### Uruchamianie pakietu MajorVersiondataUpgrade.zip
<a id="run-the-majorversiondataupgradezip-package" class="xliff"></a>

Gdy to zadanie odbywa się podczas rozpoczynania eksploatacji, wykonuje je zespół DSE firmy Microsoft. Jednak podczas testowania przełączenia jest wykonywane przez programistów. Podczas tego zadania stara struktura bazy danych jest przekształcana na strukturę nowego systemu.

W ramach tego zadania jest uruchamiany proces synchronizacji bazy danych. Synchronizacja bazy danych może zająć dużo czasu w niektórych sytuacjach, na przykład gdy zmienił się indeks klastrowany tabeli, ponieważ ta operacja mocno angażuje system bazodanowy SQL.

Stanowczo zalecamy, aby najpierw wykonać analizę i proces debugowania w środowisku projektowym. W środowisku piaskownicy opcje debugowania i analizy są bardziej ograniczone. Celem jest ograniczenie liczby lub w ogóle wyeliminowanie problemów, którymi należy się zająć podczas testowania przełączenia.

Należy zweryfikować następujące obszary:

- Ustalenie konkretnych czasów dla procesu importu.
- Optymalizacja procesu w celu zagwarantowania jego jak najszybszego działania. Optymalizacja może wymagać wykonania następujących zadań:

    - Monitorowanie wydajności poszczególnych skryptów uaktualniania za pośrednictwem tabeli ReleaseUpdateScriptsExecution.
    - Korygowanie skryptów w celu zoptymalizowania wydajności. To zadanie może wymagać dostosowania kodu źródłowego języka X++ skryptu w celu jego zoptymalizowania dla używanego zestawu danych.
    - Monitorowanie wskaźnika DTU bazy danych Azure SQL przy użyciu funkcji monitorowania w usłudze Microsoft Dynamics Lifecycle Services (LCS) lub w widoku systemowego sys.dm_resources_stats dostępnego w programie Management Studio. Jeśli zasoby są maksymalnie wykorzystane, może zajść potrzeba wnioskowania o wyższy poziom bazy danych do zespołu DSE firmy Microsoft.

### Wycofanie do systemu AX 2012
<a id="roll-back-to-ax-2012" class="xliff"></a>

Celem tego zadania jest przywrócenie bazy danych przy użyciu kopii zapasowej wykonanej podczas wyłączania systemu AX 2012, a następnie ponowne włączenie systemu AX 2012. Może być również konieczne przywrócenie stanu zintegrowanych systemów. Jednak ponieważ zintegrowane systemy różnią się w zależności od firmy, trzeba zaplanować ten scenariuszu niezależnie, zgodnie z konkretną sytuacją w firmie. Chociaż jest mało prawdopodobne, że wycofanie okaże się konieczne, bardzo ważne jest przetestowanie tego procesu na wszelki wypadek.

## Funkcjonalny strumień pracy
<a id="functional-workstream" class="xliff"></a>

Po uaktualnieniu danych wymagane będzie wykonanie kilku zadań konfiguracyjnych w nowym środowisku. Celem tego strumienia pracy jest udokumentowanie i skwantyfikowanie wszystkich zadań konfiguracyjnych oraz przydzielenie zasobu do każdego zadania, co ma zagwarantować możliwość wykonania tych zadań razem z technicznym strumieniem pracy w granicach okna czasowego przestoju.

Na ogół zadania funkcjonalne obejmują zmianę wartości określonych parametrów systemowych lub innych danych konfiguracyjnych. Te zadania są identyfikowane w całej sesji testów funkcjonalnych, która jest osobnym działaniem od testowania przełączenia. Jeśli zadanie tego typu zostanie zidentyfikowane, powinno zostać zweryfikowane z udziałem członka zespołu funkcjonalnego i programisty.

Większe zmiany mogą wymagać napisania nowego niestandardowego skryptu uaktualniania danych, który będzie aktualizował dane w trakcie procesu uaktualniania danych. Natomiast mniejsze zmiany członek zespołu funkcjonalnego może wprowadzać ręcznie w nowym systemie po wykonaniu uaktualnienia danych.

Większe zmiany, które mają nowe skrypty uaktualniania danych, muszą być testowane. W związku z tym trzeba uruchomić jedną lub więcej dodatkowych iteracji pakietu MajorVersionDataUpgrade.zip. Należy pamiętać, aby porównać koszt ponownego uruchomienia pakietu z kosztem ręcznego wprowadzania danych.

Dla każdej ręcznej zmiany należy dodać zadanie do planu dokumentu przełączenia. To zadanie musi zawierać następujące informacje:

-   Na czym polega zadanie i co należy zrobić?
-   Kto ma to zrobić?
-   Jak długo to potrwa?

