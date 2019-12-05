---
title: Usuwanie lub przestarzałe funkcje w Finance and Operations
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia.
author: sericks007
manager: AnnBe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 52ed93ae425a821ebce4ed63f154e155cb161e94
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812000"
---
# <a name="removed-or-deprecated-features-for-finance-and-operations"></a>Usuwanie lub przestarzałe funkcje w Finance and Operations

[!include [banner](../includes/banner.md)]

W tym temacie opisano funkcje, które zostały usunięte z Finance and Operations lub są przestarzałe.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu. 

> [!NOTE]
> Począwszy od usługi Finance and Operations w wersji z lipca 2017 z aktualizacją Platform update 8 dla każdej usuniętej lub przestarzałej funkcji podano typy wdrożeń. Wszystkie poprzednie wersje podane w tym temacie obsługiwały tylko wdrożenie w chmurze.

Szczegółowe informacje o obiektów w rozwiązaniu Finance and Operations można znaleźć w [raportach z wykazami parametrów technicznych](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach programu Finance and Operations.

## <a name="finance-1007-with-platform-update-31"></a>Finance 10.0.7 z aktualizacją 31 platformy

### <a name="chinese-voucher-types-without-account-groups-selection"></a>Typy chińskich załączników bez opcji wyboru grupy kont
|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zmieniono na funkcję z opcją wyboru grup kont. |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Zgłoszenia |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: Do 1 grudnia 2020 r. planujemy zakończyć obsługę chińskich typy załączników bez opcji wyboru grup kont. Więcej szczegółów dotyczących nowego projektu funkcji można znaleźć w temacie dotyczącym nowości w wersji 10.0.7 |

## <a name="finance-and-operations-1006-with-platform-update-30"></a>Aktualizacja Platform update 30 rozwiązania Finance and Operations 10.0.6


### <a name="dimensionhashgethashstr-_message"></a>DimensionHash.getHash(str _message)

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Użycie algorytmu SHA1 jest traktowane jako przestarzałe w systemie Windows zgodnie z opisem w temacie [Windows Enforcement of SHA1 Certificates](https://social.technet.microsoft.com/wiki/contents/articles/32288.windows-enforcement-of-sha1-certificates.aspx) (Wymuszanie certyfikatów SHA1 w systemie Windows).  |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Zgłoszenia |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: Do 1 kwietnia 2020 r. deweloperzy muszą zacząć korzystać z nowego interfejsu API. |

### <a name="hashcomputesha1hashstring-message"></a>Hash.ComputeSHA1Hash(komunikat)

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Użycie algorytmu SHA1 jest traktowane jako przestarzałe w systemie Windows zgodnie z opisem w temacie [Windows Enforcement of SHA1 Certificates](https://social.technet.microsoft.com/wiki/contents/articles/32288.windows-enforcement-of-sha1-certificates.aspx) (Wymuszanie certyfikatów SHA1 w systemie Windows).  |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Platforma |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: Do 1 kwietnia 2020 r. deweloperzy muszą zacząć korzystać z nowego interfejsu API. |


### <a name="formdatetimecontrolsetutcstring"></a>FormDateTimeControl.setUtcString()

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Trwa wycofywanie metody **setUtcString ()**, ponieważ dostępna jest lepsza metoda zastępcza. |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Platforma |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: Do 1 października 2020, nie planujemy już obsługiwać metody **setUtcString()**. Zamiast tego deweloperzy powinni korzystać z metody **setUtcDateTime()**. |

### <a name="blacklist-report-it--feature-reference-it-00001"></a>Raport zabronione (IT) — odwołanie do funkcji IT-00001

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Obsługa nie jest wymagana prawnie. |
| **Zamieniona przez inną funkcję?**   | Nie |
| **Powiązane obszary produktów**         | Lokalizacja Włoska |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: przed 1 października 2020, nie planuje już obsługiwania **Raportu zabronione” (IT) — odwołanie do funkcji 00001**. |

### <a name="domestic-tax-report--feature-reference-it-00003"></a>Krajowy raport podatkowy - Odwołanie do funkcji IT-00003

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Obsługa nie jest wymagana prawnie. |
| **Zamieniona przez inną funkcję?**   | Nie |
| **Powiązane obszary produktów**         | Lokalizacja Włoska |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: Do 1 października 2020, nie planujemy już obsługiwać **Krajowy raport podatkowy - Odwołanie do funkcji IT-00003**. |


## <a name="finance-and-operations-1005-with-platform-update-29"></a>Aktualizacja Platform update 29 rozwiązania Finance and Operations 10.0.5

### <a name="us-payroll-tax-updates"></a>Aktualizacje amerykańskiego podatku od wynagrodzeń

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Wycofujemy funkcję aktualizacji amerykańskiego podatku od wynagrodzeń z powodu jej niskiego wykorzystania oraz wprowadzenia rozszerzonej funkcja, która jest teraz dostępna za pośrednictwem strategicznych integracji.  |
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Lista płac |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: do 1 października 2021 planujemy wycofać funkcję aktualizacji amerykańskiego podatku od wynagrodzeń. Funkcjonalność pozostanie w produkcie, jednak ulepszenia nie będą już utrzymywać aktualności funkcjonalności, a wszelkie wady produktu będą oceniane indywidualnie dla każdego przypadku. Aby uzyskać więcej informacji, zobacz [Wycofanie funkcji aktualizacji amerykańskiego podatku od wynagrodzeń w Microsoft Dynamics 365 for Finance and Operations](https://aka.ms/financepayrollfaq). |


### <a name="data-management-staging-clean-up"></a>Czyszczenie przemieszczania zarządzania danych
|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Nie spełnia podstawowych wymagań, które są potrzebne do planowania okresowego oczyszczania. |
| **Zamieniona przez inną funkcję?**   | Tak, funkcja oczyszczania historii zadań jest dodawana w celu całościowego spełnienia tych scenariuszy. |
| **Powiązane obszary produktów**         | Zarządzanie danymi |
| **Opcja wdrażania**              | Wszystkich  |
| **Stan**                         | Wycofane: docelowy okres usuwania funkcji to grudzień 2020 roku. |

## <a name="finance-and-operations-1004-with-platform-update-28"></a>Aktualizacja Platform update 28 rozwiązania Finance and Operations 10.0.4

### <a name="france-fec-accounting-data-export-in-xml"></a>Francja: eksportowanie danych księgowych FEC w XML

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zastąpiony przez format TXT, **francuski plik audytu FEC** jest dostępny za pomocą opcji **Księga główna** \> **Zadania okresowe** \> **Eksportowanie danych**.
| **Zamieniona przez inną funkcję?**   | Tak |
| **Powiązane obszary produktów**         | Księga główna |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Wycofane. Docelowy okres usuwania funkcji to lipiec 2020 r. |


### <a name="legacy-navigation-bar"></a>Pasek nawigacji starego typu

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Wyrównanie nagłówka z innymi produktami Dynamics i Office. Więcej szczegółów można znaleźć w artykule [Zaktualizowany pasek nawigacyjny wyrównany z nagłówkiem pakietu Office](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-finance-operations/updatednavbar).
| **Zamieniona przez inną funkcję?**   | Począwszy od aktualizacji platformy 24, został wprowadzony nowy pasek nawigacyjny z funkcją wyszukiwania. |
| **Powiązane obszary produktów**         | Klient sieci Web |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Wycofane: od kwietnia 2020 r. pasek nawigacyjny starego typu przestanie być dostępny. Do tego momentu odbiorcy mogą powrócić do paska nawigacyjnego starego typu za pośrednictwem strony **Opcje wydajności klienta**. |


## <a name="finance-and-operations-1002-with-platform-update-26"></a>Aktualizacja Platform update 26 rozwiązania Finance and Operations 10.0.2


### <a name="legacy-default-action-behavior"></a>Starsze domyślne zachowanie akcji

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Starsze zachowanie dla domyślnych akcji w siatkach skutkuje tym, że nieoczekiwana kolumna ma łącze do domyślnej akcji, kiedy kolumny siatki zostaną przeorganizowane w procesie personalizacji. Nowa funkcja domyślnej akcji trwałej naprawia ten problem. Aby uzyskać więcej informacji, zobacz [Domyślne akcje trwałe w siatkach](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/sticky-default-action). |
| **Zamieniona przez inną funkcję?**   | Począwszy od aktualizacji platformy 21, została wprowadzona funkcja „domyślne akcje trwałe”. Ta funkcja może być włączona na stronie **opcji wydajności klienta**. |
| **Powiązane obszary produktów**         | Siatki w kliencie sieci web |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Wycofane: Począwszy od kwietnia 2020, domyślne akcje trwałe będą domyślnym zachowaniem, bez mechanizmu odwrócenia starszego zachowania. |

### <a name="legacy-is-one-of-filtering-experience"></a>Starsza wersja "jest jednym z" opcji filtrowania

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Filtrowanie "jest jednym z" zostało zmienione w aktualizacji Platform update 22, z możliwością, że "jest jednym z" będzie jedyną opcją filtrowania. |
| **Zamieniona przez inną funkcję?**   | Począwszy od aktualizacji Platform update 22, ulepszone filtrowanie „jest jednym z” jest dostępne na stronie **opcji wydajności klienta**. Aby dowiedzieć się więcej, zobacz [Optymalizowanie funkcji filtrowania „jest jednym z”](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/improved-isoneof-filtering). |
| **Powiązane obszary produktów**         | Klient sieci Web |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Wycofane: Począwszy od kwietnia 2020, poprawiona funkcja "jest jednym z" będzie domyślnym zachowaniem, bez mechanizmu odwrócenia starszego zachowania. |

### <a name="parameter-to-enable-sales-orders-with-multiple-project-contract-funding-sources"></a>Parametr umożliwia włączenie zamówień sprzedaży z wielu źródeł finansowania umowy dotyczącej projektu
Pomoc w tworzeniu zamówień sprzedaży w oparciu o projekt, gdzie umowa dotycząca projektu ma wiele źródeł finansowania i została włączona za pomocą ustawienia **Zezwalaj na zamówienia sprzedaży w projektach z wieloma źródłami finansowania** w menu **Parametry zarządzania projektem**. Ten parametr nie jest włączony domyślnie. 

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Po usunięciu tego parametru funkcja zawsze będzie włączona. |
| **Zamieniona przez inną funkcję?**   | Nr Funkcje do obsługi zamówień sprzedaży w oparciu o projekt zawierających wiele źródeł finansowania będą zawsze włączone.   |
| **Powiązane obszary produktów**         |Parametr **Zezwalaj na zamówienia sprzedaży w projektach z wieloma źródłami finansowania** zostanie usunięty. Następujące metody zostaną zmodyfikowana po usunięciu parametru: **ctrlSalesOrderTable** w klasie **ProjStatusType**, **sprawdzania poprawności** w polu **ProjId** i **uruchamiania** w formularzu **SalescreateOrder**. Po usunięciu parametru zostaną wycofane następujące metody: **IsSalesOrderAllowedForMultipleFundingSources** w pliku tabeli **ProjTable**, **IsAllowSalesOrdersForMultipleFundingSourcesParamEnabled** w pliku tabeli **ProjTable**, pole danych **AllowSalesOrdersForMultipleFundingSources** w formularzu **ProjParameters** i pliki **ProjParameterEntity**, metoda prywatna **IsAssociatedToMultipleFundingSourcesContract** w pliku tabeli **ProjTable**. |
| **Opcja wdrażania**              | Wszystkich  |
| **Stan**                         | Zakończenie obsługi jest planowane na kwiecień 2020. |

### <a name="legacy-workflow-reports-for-tracking-and-instance-status"></a>Raporty ze starszych przepływów pracy do śledzenia i identyfikacji i stanów wystąpienia

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Raporty ze starszych przepływów pracy do śledzenia i identyfikacji i stanów wystąpienia są wycofywane, pnieważ nie ma już do nich odniesień z nawigacji. Nazwy raportów to WorkflowWorkflowInstanceByStatusReport i WorkflowWorkflowTrackingReport. |
| **Zamieniona przez inną funkcję?**   | Zamiennie można używać formularza historii przepływu pracy. |
| **Powiązane obszary produktów**         | Klient sieci Web |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Wycofane: docelowy okres usuwania funkcji to kwiecień 2020 roku. |

## <a name="finance-and-operations-1001-with-platform-update-25"></a>Aktualizacja Platform update 25 rozwiązania Finance and Operations 10.0.1

### <a name="deprecated-apis-and-potential-breaking-changes"></a>Wycofane interfejsy API i potencjalnie istotne zmiany


#### <a name="deriving-from-internal-classes-is-deprecated"></a>Dziedziczenie z wewnętrznych klas jest przestarzałe

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | W wersjach sprzed aktualizacji platformy 25 można było utworzyć klasę lub tabelę, która pochodzi z wewnętrznej klasy/tabeli zdefiniowanej w innym pakiecie/module. Nie jest to bezpieczna praktyka kodowania. Począwszy od aktualizacji platformy 25 kompilator wyświetli komunikat ostrzegawczy. |
| **Zamieniona przez inną funkcję?**   | Ostrzeżenie kompilatora zostanie zastąpione błędem w nadchodzącej aktualizacji Platform update 26. Ta zmiana jest zgodna z poprzednimi wersjami w czasie wykonywania, co oznacza, że po uruchomieniu aktualizacji platformy 25 lub nowszej można ją wdrożyć w dowolnym środowisku piaskownicy lub produkcji, bez konieczności modyfikowania kodu niestandardowego. Ta zmiana wpływa tylko na czas projektowania i kompilacji.|
| **Powiązane obszary produktów**         | Narzędzia programistyczne Visual Studio. |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe - ostrzeżenie stanie się błędem kompilacji w nadchodzącej aktualizacji platformy 26. |

#### <a name="overriding-internal-methods-is-deprecated"></a>Zastępowanie wewnętrznych metod jest przestarzałe

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | W wersjach sprzed aktualizacji platformy 25 można było zastąpić wewnętrzną metodę w klasie pochodnej zdefiniowanej w innym pakiecie/module. Nie jest to bezpieczna praktyka kodowania. Począwszy od aktualizacji platformy 25 kompilator wyświetli komunikat ostrzegawczy. |
| **Zamieniona przez inną funkcję?**   | Ostrzeżenie zostanie zastąpione błędem kompilacji w nadchodzącej aktualizacji Platform update 26. Ta zmiana jest zgodna z poprzednimi wersjami w czasie wykonywania, co oznacza, że po uruchomieniu aktualizacji platformy 25 lub nowszej można ją wdrożyć w dowolnym środowisku piaskownicy lub produkcji, bez konieczności modyfikowania kodu niestandardowego. Ta zmiana wpływa tylko na czas projektowania i kompilacji. |
| **Powiązane obszary produktów**         | Narzędzia programistyczne Visual Studio. |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe - ostrzeżenie stanie się błędem kompilacji w nadchodzącej aktualizacji platformy 26. |

## <a name="finance-and-operations-1000-with-platform-update-24"></a>Aktualizacja Platform update 24 rozwiązania Finance and Operations 10.0.0

### <a name="renaming-released-products"></a>Zmienianie nazw zwolnionych produktów 
|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | W przypadku użycia funkcji **Zmień nazwę klucza podstawowego** w celu zmiany wartości identyfikatora towaru (ItemId) zwolnionego produktu, aktualizowane są tylko bezpośrednie odwołania do klucza obcego. Wszelkie inne odwołania do zwolnionego produktu, na przykład ze zlecenia produkcyjnego, będą zachowywały stary identyfikator towaru (ItemId). W efekcie mogą istnieć niespójne dane, które ostatecznie zablokują procesy biznesowe. |
| **Zamieniona przez inną funkcję?**   | Nr |
| **Powiązane obszary produktów**         | Zarządzanie informacjami o produktach |
| **Opcja wdrażania**              | Wszystkich  |
| **Stan**                         | Usunięto z aktualizacją Platform update 24 rozwiązania Finance and Operations 10.0.0 W wyjątkowych przypadkach, na przykład w celu cofnięcia poprzedniej zmiany nazwy klucza podstawowego zwolnionego produktu, można wysłać prośbę do Microsoftu o tymczasowe usunięce tego ograniczenia operacji zmiany nazwy klucza podstawowego dla zwolnionych produktów. |


## <a name="finance-and-operations-813-with-platform-update-23"></a>Aktualizacja Platform update 23 rozwiązania Finance and Operations 8.1.3

### <a name="sql-server-reporting-services-reportviewer-control"></a>Formant SQL Server Reporting Services ReportViewer
Klienci mogą używać akcji **eksportowania** wbudowanych w formant SQL Server Reporting Services (SSRS) ReportViewer w celu pobierania dokumentów wytwarzanych przez aplikacje Finance and Operations. Ta prezentacja raportu oparta na języku HTML oferuje podgląd dokumentu niedzielonego na strony.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Podgląd HTML bez podziału na strony **nie** zapewnia dokładności takiej, jak mają fizyczne dokumenty z Finance and Operations. Dzięki wdrożeniu PDF jako standardowego formatu dla dokumentów biznesowych, użytkownicy będą mogli wykorzystać nowoczesne widoki z lepszą wydajnością podczas sporządzania raportów aplikacji. |
| **Zamieniona przez inną funkcję?**   | W przyszłości, dokumenty PDF będą formatami domyślnymi dla reportów renderowanych przez Finance and Operations.   |
| **Powiązane obszary produktów**         | Ta zmiana **nie** wpływa na scenariusze klientów, kiedy raporty są rozsyłane elektronicznie lub wysyłane bezpośrednio do drukarki.    |
| **Opcja wdrażania**              | Wszyscy  |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. Wprowadzenie funkcji automatycznego podglądania raportów używającej wbudowanej przeglądarki PDF jest planowane w majowej aktualizacji platformy 2019. |

### <a name="client-kpi-controls"></a>Formanty KPI klienta
Wbudowanie kluczowych wskaźników wydajności (KPI) może być modelowane w Visual Studio przez dewelopera i dodatkowo dostosowane przez użytkownika końcowego.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Natywne formanty klienta używane do zdefiniowania KPI są rzadko pobierane i od dewelopera zależy dodanie miar, które można śledzić. |
| **Zamieniona przez inną funkcję?**   | Usługa PowerBI.com oferuje światowej klasy narzędzie do definiowania KPI i zarządzania nimi na podstawie danych z zewnętrznych źródeł.  W nowej wersji planujemy umożliwienia osadzania rozwiązań hostowanych przez PowerBI.com w aplikacjach roboczych.   |
| **Powiązane obszary produktów**         | Ta aktualizacja uniemożliwi deweloperom wprowadzenie nowych formantów KPI w Visual Studio designer.    |
| **Opcja wdrażania**              | Wszyscy  |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="deprecated-apis-and-future-breaking-changes"></a>Wycofane interfejsy API i przyszłe ważne zmiany

#### <a name="field-groups-containing-invalid-field-references"></a>Grupy pól zawierających nieprawidłowe pole odwołania

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Definicje metadanych tabeli mogą mieć grupy pól zawierające nieprawidłowe odniesienia do pól. Ten problem jest obecnie zaliczony do kategorii *ostrzeżenia kompilatora*, a nie *błąd*, co oznacza, że można tworzyć pakiety możliwe do wdrożenia i wdrażać je bez naprawiania problemu. W razie wdrożenia może to spowodować błędy raportowania finansowego i usług SQL Server Reporting Services (SSRS). Aby rozwiązać ten problem:<br><br>1. Usuń nieprawidłowe odwołanie pola z definicji grupy pól tabel.<br><br>2. Kompiluj ponownie.<br><br>3. Upewnij się, ostrzeżenia lub błędy zostały naprawione. |
| **Zamieniona przez inną funkcję?**   | Ostrzeżenie kompilatora zostanie zastąpione błędem w przyszłości.  |
| **Powiązane obszary produktów**         | Narzędzia programistyczne Visual Studio. |
| **Opcja wdrażania**              | Wszystko. |
| **Stan**                         | Przestarzałe — ostrzeżenie będzie w przyszłości błędem czasu kompilacji. W tej chwili planujemy aktualizację platformy 30. |

#### <a name="complete-list"></a>Pełna lista
Aby wyświetlić listę wszystkich interfejsów API, które zostaną wycofane, zobacz [Wycofanie metod i elementów metadanych](deprecation-deletion-apis.md).

## <a name="finance-and-operations-81-with-platform-update-20"></a>Aktualizacja Platform update 20 rozwiązania Finance and Operations 8.1

### <a name="batch-transfer-rules-for-subledger-journal-account-entries"></a>Reguły przetwarzania wsadowego zapisów na koncie w arkuszu księgi podrzędnej
Tryb przesyłania synchronicznego jest usuwany z parametrów księgi głównej.  Zastępują go tryby przesyłania asynchronicznego i zaplanowanych zadań wsadowych, które już istnieją jako opcje przesyłania. Aby uzyskać dodatkowe informacje, zobacz [blog Parametry księgi głównej — reguły przetwarzania wsadowego](https://community.dynamics.com/365/financeandoperations/b/financials/archive/2019/03/15/general-ledger-parameters-batch-transfer-rules).

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Opcja przesyłania synchronicznego jest usuwana ze względu na wpływ na wydajność systemu. |
| **Zamieniona przez inną funkcję?**   | Zamiast przesyłania synchronicznego należy używać opcji przesyłania asynchronicznego i zaplanowanych zadań wsadowych.   |
| **Powiązane obszary produktów**         | Księga główna, Rozrachunki z dostawcami, Rozrachunki z odbiorcami, Zaopatrzenie, Wydatek    |
| **Opcja wdrażania**              | Wszyscy  |
| **Stan**                         | Wycofane — docelowy okres usuwania funkcji to publikacja wersji 10.0.|

### <a name="electronic-reporting-for-russia"></a>Raportowanie elektroniczne dla Rosji
Funkcja do konfigurowania formatów plików .txt i .xml dla deklaracji. 

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zastąpiono modułem Raportowanie elektroniczne. |
| **Zamieniona przez inną funkcję?**   | Tak. |
| **Powiązane obszary produktów**         | Księga główna |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Usunięto z aktualizacją Platform update 20 rozwiązania Finance and Operations 8.1 |

### <a name="financial-reports-generator-for-russia"></a>Generator raportów finansowych dla Rosji
Narzędzie do konfigurowania zbierania danych na potrzeby raportów księgowych i podatkowych i eksportowanie danych do szablonów raportów XLS i DOC. Części funkcjonalne: usunięto funkcje eksportowania danych do szablonów raportów w formatach XLS i DOC, zapytań i stałych wymagań. 

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Usunięte części są zastąpione modułem Raportowanie elektroniczne. |
| **Zamieniona przez inną funkcję?**   | Tak. Interfejs użytkownika konfigurowania raportów finansowych powinien być używany do konfigurowania reguł zbierania danych do kont KG i rejestrów podatkowych. W module Raportowanie elektroniczne należy skonfigurować funkcje eksportowania danych do różnych typów plików, stałych wymagań i reguł zbierania danych za pomocą mechanizmu przypominającego zapytania. |
| **Powiązane obszary produktów**         | Księga główna. |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Usunięto z aktualizacją Platform update 20 rozwiązania Finance and Operations 8.1 |

### <a name="integration-with-external-providers-for-sending-electronic-reporting-through-communication-channels-for-russia"></a>Integracja z zewnętrznymi dostawcami na potrzeby wysyłania raportów elektronicznych poprzez kanały komunikacyjne dla Rosji
Funkcja eksportowania wygenerowanych plików elektronicznych deklaracji do folderu w celu dalszego przesłania do oficjalnych dostawców raportowania elektronicznego, a także zaimportowanie stanu z powrotem.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zastąpiono konfigurowalną funkcją komunikatów elektronicznych. |
| **Zamieniona przez inną funkcję?**   | Tak.  |
| **Powiązane obszary produktów**         | Księga główna, Podatek |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Usunięto z aktualizacją Platform update 20 rozwiązania Finance and Operations 8.1 |


### <a name="profit-tax-register-wizard"></a>Kreator tworzenia rejestru podatku dochodowego.
Funkcja do tworzenia szablonów dla nowych rejestrów podatku dochodowego. Ta funkcja tworzy obiekty X ++ dla rejestracji nowych rejestrów, które są tworzone jako szablony z dodaną odpowiednią logiką obliczeń.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Funkcja jest niezgodna z modelem rozszerzenia dla rozwiązania Finance and Operations. |
| **Zamieniona przez inną funkcję?**   | Nie |
| **Powiązane obszary produktów**         | Podatek |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Usunięto z aktualizacją Platform update 20 rozwiązania Finance and Operations 8.1 |


## <a name="finance-and-operations-80-with-platform-update-15"></a>Aktualizacja Platform update 15 rozwiązania Finance and Operations 8.0
Żadne funkcje nie zostały usunięte ani wycofane w tej wersji. Aktualizacja platformy 15 jest zbiorcza i zawiera nowe oraz zmienione funkcje z aktualizacji platformy 13, 14 i 15.

## <a name="finance-and-operations-enterprise-edition-73-with-platform-update-12"></a>Rozwiązanie Finance and Operations Enterprise edition 7.3 z aktualizacją Platform update 12

### <a name="personalized-product-recommendations"></a>Spersonalizowane rekomendacje produktów 
Począwszy od 15 lutego 2018 roku sprzedawcy detaliczni nie będą już mogli wyświetlać spersonalizowanych rekomendacji produktów na urządzeniach w punktach sprzedaży (POS). Aby uzyskać więcej informacji, zobacz [Omówienie rekomendacji produktów](../../../commerce/product-recommendations.md).  

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Usuwamy obecną wersję usługi rekomendowania produktów, ponieważ w nowej wersji wprowadzamy lepszy algorytm i nowsze funkcje zorientowane na handel detaliczny.  |
| **Zamieniona przez inną funkcję?**   | Nr Po wiośnie 2018 roku planujemy przywrócić tę funkcję, ale będzie ona wykorzystywała nową usługę rekomendacji.   |
| **Powiązane obszary produktów**         | Spersonalizowane rekomendacje produktów w punkcie sprzedaży.                                                    |
| **Opcja wdrażania**              | Wszyscy                                                                                      |
| **Stan**                         |Usunięto 15 lutego 2018 r. Dotyczy to klientów używających programu Dynamics 365 for Operations w wersji 1611 i nowszych.  |

### <a name="extension-of-the-list-of-electronic-reporting-er-functions"></a>Poszerzanie listy funkcji raportowania elektronicznego (ER)
Możliwość wprowadzenia niestandardowych funkcji w celu użycia w Konstruktorze wyrażeń ER (aby uzyskać więcej informacji, zobacz [Rozszerzenie wykazu funkcje raportowania elektronicznego (ER)](../../dev-itpro/analytics/general-electronic-reporting-formulas-list-extension.md)) nie jest już obsługiwana. Z powodu zmian w interfejsie API ER interfejs API do wywoływania wbudowanych funkcji z konstruktora wyrażeń jest wewnętrzny i nie można go już rozszerzyć.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Inicjatywa dotycząca uszczelnienia kodu  |
| **Zamieniona przez inną funkcję?**   | Brak. W każdym przypadku, w którym potrzebna jest nowa wbudowana funkcja, należy przesłać nowy wniosek o rozszerzenie do zespołu platformy ER.<br><br>Jako tymczasowe rozwiązanie na czas tworzenia wymaganej funkcji przez zespół ER wymaganą logikę można zaprogramować jako metodę niestandardowej klasy aplikacji. Ta metoda jest dostępna w wyrażeniu ER jako właściwość dodanego źródła danych ER typu **Aplikacja\Klasa** dotyczącego tej niestandardowej klasy aplikacji.  |
| **Powiązane obszary produktów**         | Struktura raportowania elektronicznego                                                      |
| **Opcja wdrażania**              | Wszystkich                                                                                      |
| **Stan**                         | Usunięto w wersji Finance and Operations Enterprise Edition 7.3.    |

### <a name="inventory-by-item-group-and-inventory-by-inventory-dimension-aging-reports"></a>Raporty Zapasy według grupy towarów i Wiekowanie zapasów z podziałem na wymiary magazynowe

Te dwa raporty nie są już obsługiwane w rozwiązaniu Finance and Operations. Zamiast tego raportu **Wiekowanie zapasów** można użyć do lepszej obsługi użytkownika.

|   |  |
|--------------|-----------------------|
| **Przyczyna amortyzacji**       | Pokrywające się funkcje  |
| **Zamieniona przez inną funkcję?** | Tak. Te dwa raporty zostały zastąpione przez raport **Wiekowanie zapasów**.     |
| **Powiązane obszary produktów**       | Zarządzanie zapasami, Zarządzania kosztami        |
| **Opcja wdrażania**        | Wszyscy|
| **Stan**                       | Wycofane: elementy ,emu tych dwóch raportów zostały usunięte w wersji 7.3. Jednakże kod raportów jest nadal dostępny w produkcie. Planowane jest usunięcie kodu w kolejnych wersjach. |

### <a name="power-bi-content-packs-available-on-appsource"></a>Pakiety zawartości usługi Power BI dostępne w usłudze AppSource
Pakiety zawartości **Zarządzanie kosztami**, **Wyniki finansowe** i **Retail Channel Performance**, które są opublikowane w witrynie [Microsoft AppSource](https://appsource.microsoft.com), zostały wycofane w konsekwencji aktualizacji produktu w usłudze Microsoft Power BI. Formularze administracji systemu używane do wdrażania tych pakietów zawartości w witrynie PowerBI.com także zostały wycofane z rozwiązania Finance and Operations.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Aktualizacje produktu w usłudze Microsoft Power BI. |
| **Zamieniona przez inną funkcję?**   | Pakiety zawartości **Zarządzanie kosztami**, **Wyniki finansowe** i **Retail Channel Performance**, które opublikowano w witrynie [AppSource](https://appsource.microsoft.com), są zastępowane aplikacjami analitycznymi, które umożliwiają integrację rozwiązań na poziomie bazy danych. Aby uzyskać więcej informacji o aplikacjach analitycznych, zobacz [Osadzona usługa Power BI w obszarach roboczych](../../dev-itpro/analytics/embed-power-bi-workspaces.md).    |
| **Powiązane obszary produktów**         | Zarządzanie kosztami, Finanse i Handel detaliczny                                                                                               |
| **Opcja wdrażania**              | Tylko w chmurze (integracja z witryną PowerBI.com nie jest obsługiwana we wdrożeniach lokalnych.)                                                                                                            |
| **Stan**                         | Wycofane: docelowy okres usuwania funkcji to drugi kwartał 2018 roku.    |

### <a name="standard-ui-in-data-management-workspace"></a>Standardowy interfejs użytkownika w obszarze roboczym zarządzania danymi

Standardowy interfejs użytkownika w zarządzaniu danymi to starszy interfejs użytkownika, który jest domyślnym interfejsem użytkownika dostępnym dla użytkowników, gdy wyświetlą obszar roboczy zarządzania danymi.

|   |  |
|------------------|-------------------------|
| **Przyczyna wycofania/usunięcia** | Inwestujemy w nowe doświadczenia użytkownika w nowym interfejsie użytkownika.             |
| **Zamieniona przez inną funkcję?**   | Nowy interfejs użytkownika o nazwie *Widoki rozszerzone* zastępuje stary interfejs użytkownika.            |
| **Powiązane obszary produktów**         | Obszar roboczy zarządzania danymi                                                     |
| **Opcja wdrażania**              | Wszyscy                                                                           |
| **Stan**                         | Wycofane: docelowy okres usuwania funkcji to drugi kwartał 2018 roku. |

### <a name="excise-sales-tax-service-tax-for-india"></a>Akcyza, Podatek, Podatek od usług w Indiach

Te podatki zostały zsumowane w hinduskim PTU.

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Przyczyna usunięcia lub wycofania**       | Te podatki zostały zsumowane w hinduskim PTU.                          |
| **Zamieniona przez inną funkcję?**            | Hinduski PTU                                                              |
| **Powiązane obszary produktów**                  | Podatek                                                                     |
| **Opcja wdrażania**                       | Wszystkie moduły                                                   |
| **Stan**                                  | Wycofane: nie określono daty usunięcia dla tej funkcji. |    

### <a name="file-validation-utility-fvu-for-india"></a>Narzędzie File Validation Utility (FVU) dla Indii

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Przyczyna usunięcia lub wycofania**       | Brak wykorzystywania przez odbiorców.                                                  |
| **Zamieniona przez inną funkcję?**            | Nr                                                                      |
| **Powiązane obszary produktów**                  | Hinduska potrącona zaliczka na podatek                                                  |
| **Opcja wdrażania**                       | Wszystkie moduły                                                                    |
| **Stan**                                  | Wycofane: nie określono daty usunięcia dla tej funkcji.   |        

### <a name="tdstcs-certificate-for-india"></a>Certyfikat TDS/SKT dla Indii

Użytkownicy mogą pobrać go z portalu rządowego.

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Przyczyna usunięcia lub wycofania**       | Brak wykorzystywania przez odbiorców.                                                  |
| **Zamieniona przez inną funkcję?**            | Nr                                                                      |
| **Powiązane obszary produktów**                  | Hinduska potrącona zaliczka na podatek                                                  |
| **Opcja wdrażania**                       | Wszystkie moduły                                                                   |
| **Stan**                                  | Wycofane: nie określono daty usunięcia dla tej funkcji.     |    

### <a name="exportimport-exim-incentive-scheme-for-india"></a>Schemat motywacji dotyczący eksportu/importu (EXIM) dla Indii


|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Przyczyna usunięcia lub wycofania**       | Brak wykorzystywania przez odbiorców.                                                  |
| **Zamieniona przez inną funkcję?**            | Nr                                                                      |
| **Powiązane obszary produktów**                  | Import i eksport                                                       |
| **Opcja wdrażania**                       | Wszystkie moduły                                                                    |
| **Stan**                                  | Wycofane: nie określono daty usunięcia dla tej funkcji.  |    


## <a name="dynamics-365-for-retail-72"></a>Dynamics 365 for Retail 7.2

### <a name="personalized-product-recommendations"></a>Spersonalizowane rekomendacje produktów 
Począwszy od 15 lutego 2018 roku sprzedawcy detaliczni nie będą już mogli wyświetlać spersonalizowanych rekomendacji produktów na urządzeniach w punktach sprzedaży (POS). Aby uzyskać więcej informacji, zobacz [Omówienie rekomendacji produktów](../../../commerce/product-recommendations.md).  

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Usuwamy obecną wersję usługi rekomendowania produktów, ponieważ w nowej wersji wprowadzamy lepszy algorytm i nowsze funkcje zorientowane na handel detaliczny.  |
| **Zamieniona przez inną funkcję?**   | Nr Po wiośnie 2018 roku planujemy przywrócić tę funkcję, ale będzie ona wykorzystywała nową usługę rekomendacji.   |
| **Powiązane obszary produktów**         | Spersonalizowane rekomendacje produktów w punkcie sprzedaży.                                                    |
| **Opcja wdrażania**              | Wszyscy                                                                                      |
| **Stan**                         |Usunięto 15 lutego 2018 r. Dotyczy to klientów używających programu Dynamics 365 for Retail w wersji 7.2 i nowszych. |


## <a name="finance-and-operations-enterprise-edition-july-2017-with-platform-update-8"></a>Rozwiązanie Finance and Operations Enterprise edition lipiec 2017 z aktualizacją Platform update 8

### <a name="currency-conversion-for-accounting-and-reporting-currencies"></a>Konwersja waluty rozliczeniowych i raportowania

Mechanizm konwersji dla waluty rozliczeniowych i raportowania został wprowadzony wraz z wprowadzeniem euro.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ograniczone użycie oraz dodanie funkcji Kopiuj dane firmy jako zamiennika.      |
| **Zamieniona przez inną funkcję?**   | Nie, ale dodano funkcje Kopiuj dane firmy i Konfiguracje, które ułatwiają przechodzenie do firmy mającej zmienne podstawowe wymagania. |
| **Powiązane obszary produktów**         | Zarządzanie finansami     |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.   |


### <a name="warehouse-mobile-devices-portal"></a>Portal urządzeń przenośnych używanych w magazynie

Portal urządzeń przenośnych używanych w magazynie (WMDP) był autonomicznym składnikiem przeznaczonym do lokalnego samodzielnego instalowania. Ten składnik nie jest już obsługiwany w rozwiązaniu Finance and Operations. Funkcjonalność portalu WMDP została zastąpiona macierzystą aplikacją o ulepszonej funkcjonalności.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Pokrywające się funkcje.       |
| **Zamieniona przez inną funkcję?**   | Tak. Ta funkcja została zastąpiona przez moduł Finance and Operations — Magazynowanie. Aby uzyskać więcej informacji na temat konfiguracji i wymagań wstępnych, zobacz [Omówienie instalowania i konfiguracji aplikacji Magazynowanie](../../../supply-chain/warehousing/install-configure-warehousing-app.md). |
| **Powiązane obszary produktów**         | Zarządzanie magazynem, Zarządzanie transportem     |
| **Opcja wdrażania**              | Portal urządzeń przenośnych używanych w magazynie (WMDP) był autonomicznym składnikiem przeznaczonym do lokalnego samodzielnego instalowania.               |
| **Stan**                         | Wycofane: docelowy okres usuwania funkcji to czwarty kwartał 2019 roku.   |

### <a name="advanced-bank-reconciliation-matching-rule-for-manual-matching"></a>Reguła zaawansowanego uzgadniania konta bankowego w ręcznym uzgadnianiu

Reguła uzgadniania używana do wybierania i zaznaczania dokumentu bankowego podczas ręcznego uzgadniania dokumentów w arkuszu uzgadniania.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ograniczone użycie.                                                                         |
| **Zamieniona przez inną funkcję?**   | Nr Do wyszukiwania dokumentów na potrzeby uzgadniania należy używać funkcji filtrowania kolumn. |
| **Powiązane obszary produktów**         | Zarządzanie gotówką i bankami                                                               |
| **Opcja wdrażania**              | Wszystkich                                                                                    |
| **Stan**                         | Usunięto w lipcu 2017 r.                                                               |

## <a name="dynamics-365-for-operations-1611-with-platform-update-3"></a>Dynamics 365 for Operations 1611 z aktualizacją platformy 3

### <a name="aeb-payment-formats-for-spain"></a>Formaty płatności AEB dla Hiszpanii

Formaty płatności Consejo Superior Bancario służyły do wysyłania plików przekazów do banku dla płatności odbiorcy i dostawcy. Zawartość tych formatów była określana przez Asociación Española de Banca. Obejmuje ona Cuaderno 19, 32, 58, 34.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Te formaty płatności nie są już używane.                                  |
| **Zamieniona przez inną funkcję?**   | Tak, przez formaty płatności poleceniem przelewu i poleceniem zapłaty ISO20022 dla Hiszpanii |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami, Rozrachunki z odbiorcami                                    |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.           |

### <a name="bank-payments-transfer-for-lithuania"></a>Przelewy płatnościami bankowymi dla Litwy

Przelewy płatnościami bankowymi na Litwie były generowane i drukowane przy użyciu formatu eksportu przelewów (LT). Na litewskim rynku w 2005 r. zaczęto używać ujednoliconego systemu bankowości elektronicznej LITAS.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Te formaty płatności nie są już używane.                        |
| **Zamieniona przez inną funkcję?**   | Tak, przez format płatności poleceniem przelewu ISO20022 dla Litwy     |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami                                               |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>Formaty płatności BBS Direkte Remittering dla Norwegii

Formaty płatności BBS Direkte Remittering zawierają funkcje eksportu inkasa płatności od odbiorcy (polecenie zapłaty) i importu komunikatu zwrotnego.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Te formaty płatności nie są już używane.  |
| **Zamieniona przez inną funkcję?**   | Format płatności od odbiorcy AvtaleGiro dla Norwegii może służyć do generowania komunikatów polecenia zapłaty. Import komunikatów zwrotnych zostanie zaimplementowany w przyszłych wersjach. |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami, Rozrachunki z odbiorcami   |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.                                                                                                 |

### <a name="chart-of-accounts-tool-for-spain"></a>Narzędzie planu kont dla Hiszpanii

To narzędzie jest używane, gdy plan kont w Hiszpanii wymaga dużych zmian. Użytkownicy mogą zaimportować nowy plan kont w formacie programu Microsoft Excel lub tekstowym, a także zaimportować sprawozdania finansowe.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ograniczone użycie                                                  |
| **Zamieniona przez inną funkcję?**   | Nr                                                             |
| **Powiązane obszary produktów**         | Księga główna                                                 |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="dom80-payment-format-for-belgium"></a>Format płatności Dom80 dla Belgii

Starszy belgijski format płatności dla inkasa płatności (polecenie zapłaty).

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ten format płatności nie jest już używany.                          |
| **Zamieniona przez inną funkcję?**   | Tak, przez format płatności poleceniem zapłaty ISO 20022 dla Belgii         |
| **Powiązane obszary produktów**         | Rozrachunki z odbiorcami                                            |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="dtaezag-payment-formats-for-switzerland"></a>Formaty płatności DTA/EZAG dla Szwajcarii

Formaty DTA/EZAG są zintegrowane w systemie ESR, ponieważ mogą być nośnikami numeru odwołania. Numery odwołania nie są obowiązkowe i dlatego te formaty mogą służyć do przetwarzania wszelkich płatności dla dostawców. Te formaty są używane przez firmy, które mają konta bankowe w lokalizacji innej niż „Postfinance”.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Te formaty płatności nie są już używane.                        |
| **Zamieniona przez inną funkcję?**   | Tak, przez format płatności poleceniem przelewu ISO20022 dla Szwajcarii   |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami                                               |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>Format płatności EDIFACT-DIRDEB dla Austrii

Format płatności EDIFACT-DIRDEB dla inkasa płatności (polecenie zapłaty).

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ten format płatności nie jest już używany.                          |
| **Zamieniona przez inną funkcję?**   | Tak, przez format płatności poleceniem zapłaty ISO 20022 dla Austrii         |
| **Powiązane obszary produktów**         | Rozrachunki z odbiorcami                                            |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="edivat-for-belgium"></a>EDIVAT dla Belgii

EDIVAT to starszy belgijski standard wysyłania deklaracji elektronicznych za pośrednictwem bezpiecznej poczty. Dynamics AX 2012 zachowuje rozwiązanie tylko do odczytu, aby umożliwić dostęp do danych historycznych.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ta funkcjonalność nie jest już używana.                           |
| **Zamieniona przez inną funkcję?**   | Nr                                                             |
| **Powiązane obszary produktów**         | Księga główna                                                 |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>Format importu płatności eGiro EDIFACT CREMUL dla Norwegii

eGiro opiera się na międzynarodowym standardzie ONZ EDIFACT CREMUL (Multiple Credit Advice Message), który jest używany do automatycznego księgowania płatności od odbiorców. W Dynamics AX funkcjonalność eGiro jest zaimplementowana jako format importu płatności od odbiorców.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ten format płatności nie jest już używany.                                                     |
| **Zamieniona przez inną funkcję?**   | Nr Ten format zostanie zastąpiony formatami importu wyciągów ISO 20022 w przyszłych wersjach. |
| **Powiązane obszary produktów**         | Rozrachunki z odbiorcami                                                                       |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.                            |

### <a name="external-inventory-for-poland"></a>Zapasy zewnętrzne dla Polski

Dowód przyjęcia towarów, które otrzymano od dostawcy do sprzedaży bez zakupu. Towary, które są obsługiwane w zewnętrznych zapasach, nie mają wpływu na zapasy standardowe i mogą być sprzedawane, a następnie automatycznie kupowane. Ten proces tworzy faktyczne przesunięcia magazynowe.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zamieniona przez inną funkcję                                    |
| **Zamieniona przez inną funkcję?**   | Tak, przez podstawową funkcjonalność konsygnacji przychodzącej                |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami, Zarządzanie zapasami                         |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="financial-reports-generator-for-eastern-europe"></a>Generator raportów finansowych dla Europy Wschodniej

Narzędzie służące do konfigurowania zbierania danych na potrzeby raportów księgowych i podatkowych oraz eksportowania danych do szablonów raportów XLS i DOC.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ograniczone użycie                                                                            |
| **Zamieniona przez inną funkcję?**   | Nr Narzędzie zostanie zastąpione konfiguracjami raportowania elektronicznego w przyszłych wersjach. |
| **Powiązane obszary produktów**         | Księga główna                                                                           |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Import transakcji płatności od odbiorców dla Finlandii

Można wybrać formatu importu dla płatności fińskich, który importuje transakcje płatności od odbiorców z zewnętrznego pliku dostarczonego przez bank.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ten format płatności nie jest już używany.                                                     |
| **Zamieniona przez inną funkcję?**   | Nr Ten format zostanie zastąpiony formatami importu wyciągów ISO 20022 w przyszłych wersjach. |
| **Powiązane obszary produktów**         | Rozrachunki z odbiorcami                                                                       |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.                            |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>Import transakcji płatności do arkusza księgi głównej dla Finlandii

Format specyficzny dla Finlandii służy do importowania transakcji księgowych do księgi głównej.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ten format płatności nie jest już używany.                                                     |
| **Zamieniona przez inną funkcję?**   | Nr Ten format zostanie zastąpiony formatami importu wyciągów ISO 20022 w przyszłych wersjach. |
| **Powiązane obszary produktów**         | Rozrachunki z odbiorcami                                                                       |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.                            |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>Integracja z systemem Isabel zsynchronizowana (CIS) dla Belgii

Isabel jest systemem szkieletowym bankowości elektronicznej w Europie i de facto normą w Belgii.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Integracja z klientami systemu Isabel została wycofana.   |
| **Zamieniona przez inną funkcję?**   | Nr Nieużywane formaty płatności zostały zastąpione formatem płatności poleceniem przelewu ISO20022 dla Belgii. |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami     |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.    |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>Zmiany w planie kont i regułach księgowania dla Hiszpanii

Ta funkcja jest stosowana dla zmian w planie kont i regułach księgowania w Hiszpanii. Mapuje konta, ułatwiając przekształcanie starych planów kont na nowe plany kont oraz porównuje poprzedni rok obrachunkowy z nowym rokiem obrachunkowym, nawet jeśli zostały one zaksięgowane pod różnymi numerami kont.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ograniczone użycie                                                  |
| **Zamieniona przez inną funkcję?**   | Nr                                                             |
| **Powiązane obszary produktów**         | Księga główna                                                 |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Format płatności od dostawców Pagamento Fornittori

Starszy włoski format płatności dla poleceń przelewu.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ten format płatności nie jest już używany.                          |
| **Zamieniona przez inną funkcję?**   | Tak, przez format płatności poleceniem przelewu ISO20022 dla Włoch         |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami                                               |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="payment-export-formats-for-estonia"></a>Formaty eksportu płatności dla Estonii

Formaty Telehansa i Teleservice są używane do eksportu płatności bankowych.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Te formaty płatności nie są już używane.                        |
| **Zamieniona przez inną funkcję?**   | Tak, przez format płatności poleceniem przelewu ISO20022 dla Estonii       |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami                                               |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="payment-file-archive-for-norway"></a>Archiwum plików płatności dla Norwegii

Podczas generowania plików płatności są one automatycznie umieszczane w archiwum. Dotyczy to nawet plików, które zostały wcześniej zapisane lub odczytane.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zamieniona przez inną funkcję                                        |
| **Zamieniona przez inną funkcję?**   | Tak, przez zarchiwizowane zadania raportowania elektronicznego                            |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami, Rozrachunki z odbiorcami, Administrowanie organizacją |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.     |

### <a name="payment-import-formats-for-estonia"></a>Formaty importu płatności dla Estonii

Formaty Telehansa i TeleTeenus są używane do importu płatności bankowych.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Te formaty płatności nie są już używane.                                                    |
| **Zamieniona przez inną funkcję?**   | Nr Te formaty zostaną zastąpione formatami importu wyciągów ISO 20022 w przyszłych wersjach. |
| **Powiązane obszary produktów**         | Rozrachunki z odbiorcami                                                                        |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.                             |

### <a name="payroll-information-in-human-resources"></a>Informacje listy płac w module Zasoby ludzkie

Informacje listy płac w module Zasoby ludzkie

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ta funkcja została zastąpiona stronami podstawowych modułów Lista płac i Zasoby ludzkie.  |
| **Zamieniona przez inną funkcję?**   | **Świadczenia**, **Zarobki** i inne pokrewne strony, które były poprzednio używane w module US Payroll, otrzymały nową konfigurację i są teraz częścią konfiguracji podstawowych modułów Zasoby ludzkie, aby ułatwić zewnętrzne przetwarzanie listy płac. Ta funkcja jest dostępna za pomocą klucza konfiguracji **Zasoby ludzkie 1** \> **Lista płac**. |
| **Powiązane obszary produktów**         | Zasoby ludzkie, Lista płac   |
| **Stan**                         | Usunięto w rozwiązaniu Dynamics 365 for Operations w wersji 1611.    |

### <a name="performance-management-goal-workflow"></a>Przepływ pracy celu zarządzania wydajnością

Zarządzanie wydajnością obejmuje zarządzanie celami oraz integrację z przeglądami wydajności.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Moduł zarządzania wydajnością został przeprojektowany. Zmniejszono liczbę stron dotyczących celów, aby uprościć proces.                 |
| **Zamieniona przez inną funkcję?**   | Nr Cele są wyświetlane menedżerom w samoobsługowym portalu dla menedżerów i mogą być zmieniane oraz wyświetlane przez menedżerów. |
| **Powiązane obszary produktów**         | Zarządzanie kapitałem ludzkim       |
| **Stan**                         | Usunięto w rozwiązaniu Dynamics 365 for Operations w wersji 1611.    |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>Formaty płatności Postgirot i Postgirot Utland dla Szwecji

Formaty płatności Postgirot i Postgirot Utland dla Szwecji.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Te formaty płatności nie są już używane.                        |
| **Zamieniona przez inną funkcję?**   | Tak, przez format płatności poleceniem przelewu ISO20022 dla Szwecji        |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami                                               |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="radio-frequency-identifier"></a>Identyfikacja radiowa (RFID)

Identyfikacja radiowa (RFID) to technologia zbierania danych przy użyciu elektronicznych znaczników do przechowywania danych identyfikacyjnych bez konieczności bezpośredniego dostępu do czytnika w celu odczytania danych identyfikacyjnych.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Brak wykorzystywania przez odbiorców i ograniczony zestaw funkcji.   |
| **Zamieniona przez inną funkcję?**   | Nr                                              |
| **Powiązane obszary produktów**         | Zarządzanie zapasami                            |
| **Stan**                         | Usunięto w rozwiązaniu Dynamics 365 for Operations w wersji 1611. |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>Raport o urzędowej numeracji faktur dla Łotwy

Łotewskie prawo zawiera określone reguły numerowania faktur sprzedaży. Funkcja pozwala przypisywać konkretne numery do faktur sprzedaży na podstawie użytkownika lub grupy użytkowników. Następnie można wygenerować raport lub plik XML. Można również wydrukować raport o użytych numerach faktur.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Urzędowa numeracja faktur nie musi już być stosowana. Raport o użytych numerach faktur nie jest już wymagany. |
| **Zamieniona przez inną funkcję?**   | Nr       |
| **Powiązane obszary produktów**         | Rozrachunki z odbiorcami    |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.  |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Ustawianie imion i nazwisk menedżera i głównego księgowego firmy dla Litwy

Imiona i nazwiska menedżera oraz głównego księgowego firmy można podać w danych firmy i następnie używać w różnych raportach drukowanych lokalnie.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zamieniona przez inną funkcję                                     |
| **Zamieniona przez inną funkcję?**   | Tak, w tym samym celu można używać konfiguracji urzędników.   |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami, Rozrachunki z odbiorcami, Zaawansowane uzgadnianie konta bankowego |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.  |

### <a name="shipping-carrier-interface"></a>Interfejs firmy przewozowej

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Pokrywające się funkcje   |
| **Zamieniona przez inną funkcję?**   | Częściowo zastąpione przez Zarządzanie transportem |
| **Powiązane obszary produktów**         | Sprzedaż i marketing, Zarządzanie magazynem  |
| **Stan**                         | Usunięto w rozwiązaniu Dynamics 365 for Operations w wersji 1611.  |

### <a name="telepay-payment-formats-for-norway"></a>Formaty płatności TelePay dla Norwegii

Formaty płatności TelePay obejmują funkcje eksportu płatności dla dostawców (polecenie przelewu) i inkasa płatności od odbiorców (polecenie zapłaty).

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Te formaty płatności nie są już używane.                                                        |
| **Zamieniona przez inną funkcję?**   | Tak, przez format płatności poleceniem przelewu ISO20022 i format płatności od odbiorcy AvtaleGiro dla Norwegii |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami, Rozrachunki z odbiorcami                                                          |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.                                 |

### <a name="vendor-payment-export-formats-for-finland"></a>Formaty eksportu płatności dla dostawców dla Finlandii

Dwa formaty eksportowania płatności są dostępne dla Finlandii. LM02 (FI) jest używany w przypadku krajowych płatności, a LUM2 (FI) jest używany w przypadku płatności zagranicznych.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Te formaty płatności nie są już używane.                        |
| **Zamieniona przez inną funkcję?**   | Tak, przez format płatności poleceniem przelewu ISO20022 dla Finlandii       |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami                                               |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="warehouse-management-ii"></a>Zarządzanie magazynem II

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Rozwiązanie WMS II (Zarządzania magazynem II), które było dostępne w module **Zarządzanie zapasami**, dubluje funkcje dostępne w module **Zarządzanie magazynem**, który został udostępniony w Dynamics AX 2012 R3.                                                                         |
| **Zamieniona przez inną funkcję?**   | Moduł **Zarządzanie magazynem**, który został udostępniony w wersjach systemu AX 2012 R3, Dynamics AX 2012 R3 CU8 i Dynamics AX 2012 R3 CU9, zastępuje funkcje modułu WMS II. Nowy moduł ma bardziej zaawansowane funkcje i elastyczniejsze procesy zarządzania magazynem niż oferowane w module Zarządzanie magazynem II. |
| **Powiązane obszary produktów**         | Zarządzanie zapasami, sprzedaż i marketing, zaopatrzenie i sourcing   |
| **Stan**                         | Usunięto w rozwiązaniu Dynamics 365 for Operations w wersji 1611.    |

### <a name="worker-reminders-in-human-resources"></a>Przypomnienia dla pracowników w module Zasoby ludzkie

Informacje listy płac w module Zasoby ludzkie

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Niskie wykorzystanie                                                           |
| **Zamieniona przez inną funkcję?**   | Nr                                                                  |
| **Powiązane obszary produktów**         | Zasoby ludzkie                                                     |
| **Stan**                         | Usunięto w rozwiązaniu Dynamics 365 for Operations w wersji 1611 |

### <a name="workflow-for-creating-goals"></a>Przepływ pracy tworzenia celów

Przepływ pracy zarządzania tworzeniem celów dla pracowników jest jednym z kilku przepływów pracy, które były dostępne jako pomoc w koordynowaniu procesu zarządzania wydajnością.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Zarządzanie wydajnością zostało całkowicie przeprojektowane w rozwiązaniu Finance and Operations.     |
| **Zamieniona przez inną funkcję?**   | Przeprojektowana funkcjonalność zarządzania wydajnością zapewnia większą kontrolę nad treścią celów, miarami służącymi do śledzenia postępów oraz dołączaniem towarzyszącej dokumentacji. Cele można zapisywać jako szablony i ponownie wykorzystywać. Ta funkcja może pomóc szybciej konfigurować dodatkowe cele dla pracowników. |
| **Powiązane obszary produktów**         | Zarządzanie kapitałem ludzkim                 |
| **Stan**                         | Usunięto w rozwiązaniu Dynamics 365 for Operations w wersji 1611. |

## <a name="dynamics-ax-70"></a>Dynamics AX 7.0 


### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Możliwość anulowania zmian na fakturze od dostawcy

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Chęć poprawy wydajności.        |
| **Zamieniona przez inną funkcję?**   | Nr                             |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami               |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0. |

### <a name="aif-axd-and-axbc-integrations"></a>Integracja z AIF, AxD i AxBC

W narzędziach integracji aplikacji (AIF) może dochodzić do wymiany danych z zewnętrznymi systemami poprzez logikę biznesową powiązaną z usługami. System Dynamics AX zawiera usługi, które są oparte na dokumentach i programie .NET Business Connector (AxBC). Dokument jest tworzony przy użyciu języka XML. Kod XML zawiera informacje nagłówka dodawane w celu tworzenia *komunikatów*, które mogą być przesyłane do systemu Dynamics AX lub z niego wysyłane. Przykłady dokumentów obejmują zamówienia sprzedaży i zamówienia zakupu. Jednak niemal wszystkie podmioty, np. odbiorca, mogą być reprezentowane przez dokument. Usługi oparte na dokumentach używają menu **Axd \<Dokument\>** klasy

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Nie dało się przeskalować architektury narzędzi AIF i AxD na potrzeby usługi chmurowej. Wystąpiły problemy z wydajnością wokół importu zbiorczego.                                        |
| **Zamieniona przez inną funkcję?**   | Ta funkcja zastępuje strukturę importu/eksportu danych, która obsługuje cykliczny import/eksport zbiorczy. Dla klasy AxBC zaleca się użycie samych tabel. |
| **Powiązane obszary produktów**         | AxD, AxBC i AIF   |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.   |

### <a name="billing-code-rate-scripts"></a>Skryptów stawek dla kodów fakturowania

Skrypty fakturowania były używane do obliczania stawki fakturowania dla kodów rozliczeń. Te skrypty wymagały niestandardowego projektowania w C Sharp lub Visual Basic. W bieżącej wersji systemu Dynamics AX, **skrypty stawek dla kodów fakturowania** nie są obsługiwane.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Obsługa niestandardowych skryptów C Sharp lub Visual Basic nie została dodana w systemie Dynamics AX 7.0. |
| **Zamieniona przez inną funkcję?**   | Nie                                                                                      |
| **Powiązane obszary produktów**         | Rozrachunki z odbiorcami (sektor publiczny)                                    |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.                                                          |

### <a name="boms-without-bom-versions"></a>BOM bez wersji BOM

Po wyłączeniu klucza konfiguracji **Wersje BOM** wersje list składowych (BOM) były ukrywane we wszystkich formularzach, a system wymuszał relację 1:1 między zwolnionymi produktami i listami BOM. W bieżącej wersji systemu Dynamics AX klucza konfiguracji **Wersje BOM** nie da się wyłączyć.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Obsługa klucza konfiguracji do kontrolowania wersji BOM nie jest dopasowana do skali środowiska chmurowego. |
| **Zamieniona przez inną funkcję?**   | Nr                                                                                      |
| **Powiązane obszary produktów**         | Zarządzanie informacjami o produktach, Zarządzanie zapasami                                    |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.                                                          |

### <a name="brazilian-bordero"></a>Brazylijski format Bordero

Specjalna metoda płatności dla firm brazylijskich

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Obsługa brazylijskiej metody płatności Bordero została wycofana dla lokalizacji w Brazylii |
| **Zamieniona przez inną funkcję?**   | Nr   |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami   |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="brazilian-sintegra-statement"></a>Brazylijska deklaracja Sintegra

Krajowa deklaracja podatku ICMS

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ta deklaracja nie ma już zastosowania w niektórych stanach Brazylii. |
| **Zamieniona przez inną funkcję?**   | Nr Użytkownicy mogą użyć narzędzia Ogólne raportowanie elektroniczne do skonfigurowania deklaracji, jeśli jest to wymagane w określonych sytuacjach. |
| **Powiązane obszary produktów**         | Księgi podatkowe    |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.   |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Brazylijski tryb sytuacji awaryjnych SCAN dla NF-e

Środowisko awaryjne (SCAN) jest używane do generowania, eksportowania i importowania stanu z portalu Nota Fiscal eletrônica (NF-e), gdy środowisko Secretaria da Fazenda (SEFAZ) jest niedostępne.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ta metoda pracy awaryjnej nie jest już stosowana w niektórych stanach w Brazylii |
| **Zamieniona przez inną funkcję?**   | Nr                                                                          |
| **Powiązane obszary produktów**         | Rozrachunki z odbiorcami                                                         |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.              |

### <a name="business-analyzer"></a>Aplikacja Business Analyzer

Ta aplikacja mobilna pozwala użytkownikom przeglądać kluczowe pomiary biznesowe.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ta funkcja została zastąpiona inną funkcją.   |
| **Zamieniona przez inną funkcję?**   | Pakiet materiałów do monitorowania wyników finansowych dla usługi Microsoft Power BI będzie zawierał najważniejsze mierniki finansowe, które wcześniej były dostępne w aplikacji Business Analyzer. |
| **Powiązane obszary produktów**         | Księga główna      |
| **Stan**                         | Wycofane: użycie aplikacji Business Analyzer zostało wycofane.    |

### <a name="business-statistics"></a>Statystyki

Konfiguracja zapytań o statystyki biznesowe, które mogą ułatwić analizowanie funkcjonowania organizacji.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Istniejące podejście do analizy biznesowej (BI), niskie wykorzystanie przez odbiorców i ograniczony zestaw funkcji. |
| **Zamieniona przez inną funkcję?**   | Nowe rozwiązanie BI dla aktualnej wersji systemu Dynamics AX                                      |
| **Powiązane obszary produktów**         | Zaopatrzenie i sourcing, Rozrachunki z dostawcami, Sprzedaż i marketing, Rozrachunki z odbiorcami         |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.                                                               |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>Funkcja zmiany daty dokumentu w Arkuszu zatwierdzania faktur

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Niskie wykorzystanie                                                               |
| **Zamieniona przez inną funkcję?**   | Tak. Można zmienić datę dokumentu dla zaksięgowanej transakcji dostawcy. |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami                                                        |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.                                          |

### <a name="clieop03-payment-format-for-the-netherlands"></a>Format płatności ClieOp03 dla Holandii

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ten format nie jest już używany w Holandii, ponieważ został zastąpiony przez funkcję SEPA. |
| **Zamieniona przez inną funkcję?**   | Eksport płatności SEPA  |
| **Powiązane obszary produktów**         | Wszystkie moduły     |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.   |

### <a name="compliance-center"></a>Centrum zgodności

Centrum zgodności było witryną Enterprise Portal do zarządzania wymaganiami dokumentacji dla inicjatyw zgodności związanych z ustawą Sarbanes-Oxley.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Brak wykorzystywania przez odbiorców. Program Microsoft SharePoint oferuje te same funkcje, które były dostępne w Centrum zgodności. |
| **Zamieniona przez inną funkcję?**   | Nr   |
| **Powiązane obszary produktów**         | Zgodność z przepisami i kontrole wewnętrzne  |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.    |

### <a name="connector-for-microsoft-dynamics"></a>Connector for Microsoft Dynamics

To narzędzie zostało użyte do integracji najważniejszych danych z programu Microsoft Dynamics CRM do aplikacji Dynamics ERP.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ta funkcja została zastąpiona inną funkcją. |
| **Zamieniona przez inną funkcję?**   | Common data service                                      |
| **Powiązane obszary produktów**         | Connector dla Dynamics                         |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.                           |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Jednostka kontenera i wielowymiarowe zapasy na stanie

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Pokrywające się funkcje |
| **Zamieniona przez inną funkcję?**   | Tak. Od wersji AX 2012 ta funkcja jest zastąpiona zestawem funkcji skonsolidowanych szarż produkcyjnych. Zestaw zawiera skonsolidowany widok dostępnych zapasów. |
| **Powiązane obszary produktów**         | Zarządzanie informacjami o produktach, Kontrola produkcji, Zarządzanie zapasami, Sprzedaż i marketing  |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0. |

### <a name="cue-group-metadata"></a>Metadane grupy wskaźników

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Grupy wskaźników były używane do wyświetlania jednego lub kilku wskaźników w obszarze pola informacji. Liczba pobrań była ograniczona i występowały też problemy z wydajnością, ponieważ zmiana rekordu w formularzu nadrzędnym powodowała tworzenie jednej kwerendy na wskaźnik w grupie wskaźników. |
| **Zamieniona przez inną funkcję?**   | Nr      |
| **Powiązane obszary produktów**         | Wszystkie moduły    |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.  |

### <a name="cue-metadata"></a>Metadane wskaźnika

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Metadane wskaźnika były ograniczone do liczby lub sumy.    |
| **Zamieniona przez inną funkcję?**   | Wprowadzono metadane kafelka, by poprawić elastyczność modelowania. Można na przykład modelować aktualne liczby, nawigację i kluczowe wskaźniki wydajności (KPI). Metadane wskaźnika zostały bezpośrednio zastąpione przez metadane kafelka z liczbami. |
| **Powiązane obszary produktów**         | Wszystkie moduły           |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0      |

### <a name="danish-check-format"></a>Duński format czeku

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Obsługa duńskiego układu formatu czeku została wycofana i raport został usunięty z lokalizacji DK. |
| **Zamieniona przez inną funkcję?**   | Nr    |
| **Powiązane obszary produktów**         | Wszystkie moduły    |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.  |

### <a name="data-partitions"></a>Partycje danych

Partycje danych zapewniają logiczne oddzielenie danych w bazie danych systemu Dynamics AX.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Partycje danych zostały wprowadzone w systemie Dynamics AX 2012 R2, aby umożliwić izolowanie danych. W typowym scenariuszu firma ma oddziały. Dane z jednego oddziału firmy nie powinny być widoczne w innym oddziale, mimo że oba oddziały są zarządzane przez ten sam dział IT. Jednak były wymagane dodatkowe skrypty i towarzyszące zarządzanie programem w celu utworzenia nowych partycji i wypełnienia ich danymi oraz utworzenia kopii zapasowych danych partycji. W chmurze, gdzie mamy dostęp do usług bazy danych (baza danych SQL Microsoft Azure) w postaci platformy jako usługi (PaaS), znacznie bardziej efektywne jest używanie bazy danych jako kontenera izolacji niż konfigurowanie izolacji w programie. Niezależnie od tego, czy partycjonowanie danych jest wymagane dla oddziałów, wielu dzierżawców czy tylko ze względu na skalę, jesteśmy przekonani, że wszystkie scenariusze można lepiej obsługiwać za pomocą wielu wystąpień systemu Finance and Operations. |
| **Zamieniona przez inną funkcję?**   | Jeśli separacja poziomów bazy danych ma krytyczne znaczenie, klienci korzystający z partycji danych muszą używać wielu wystąpień systemu Finance and Operations.    |
| **Powiązane obszary produktów**         | Wszystkie moduły  |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.  |


### <a name="database-and-file-share-storage-for-attachments"></a>Przechowywanie załączników w bazach danych i udziałach plików

System Dynamics AX 2012 pozwalał na przechowywania załączników w bazach danych i udziałach plików. Obie te opcje nie są już obsługiwane.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Przechowywanie w udziałach plików nie jest już obsługiwane, ponieważ środowiska hostowane w chmurze nie mogą się komunikować z lokalnymi udziałami plików. Przechowywanie w bazie danych zostało zastąpione magazynem obiektów blob w usłudze Azure. Magazyn obiektów blob Azure odpowiada przechowywaniu w bazie danych, ponieważ dokumenty są dostępne wyłącznie za pośrednictwem formularzy klienta rozwiązania Finance and Operations. Zapewnia to dodatkową korzyść w postaci magazynu, który nie wpływa negatywnie na wydajność bazy danych. Magazyn obiektów blob jest domyślnym mechanizmem przechowywania modułu Zarządzanie dokumentami i działa natychmiast. |
| **Zamieniona przez inną funkcję?**   | Przechowywanie w bazie danych zostało zastąpione magazynem obiektów blob w usłudze Azure.   |
| **Powiązane obszary produktów**         | Wszystkie moduły  |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.   |

### <a name="delimitation"></a>Ogranicznik

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Nie stwierdzono używania funkcji. |
| **Zamieniona przez inną funkcję?**   | Nr                                     |
| **Powiązane obszary produktów**         | Czas i frekwencja                    |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.         |

### <a name="desktop-client"></a>Klient komputerowy

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Środowisko klienta systemu Dynamics AX zostało przeprojektowane, by poprawić funkcjonalność wielu platform i urządzeń.                      |
| **Zamieniona przez inną funkcję?**   | Nowy klient sieci web jest oparty na metadanych formatu dla komputerów i modelu programowania, który został dostosowany do potrzeb rozszerzonej platformy internetowej. |
| **Powiązane obszary produktów**         | Wszystkie moduły  |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.   |

### <a name="direct-database-connection"></a>Bezpośrednie połączenie z bazą danych

W programie Dynamics AX 2012 R3 aplikacja Retail Modern POS mogła się łączyć bezpośrednio z bazą danych kanału w podobny sposób, jak robi to aplikacja Enterprise POS. Było to uzupełnienie standardowej metody komunikacji używanej przez aplikację Retail Modern POS, czyli korzystania z pośrednictwa serwera sieci sprzedaży.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Bezpośrednia łączność z bazą danych wymagała protokołów o słabszych zabezpieczeniach i była używana głównie do osiągnięcia najwyższej wydajności. Ze względu na ulepszenia w dziedzinach wydajności i zabezpieczeń, które wprowadzono w rozwiązaniu Finance and Operations, ta funkcjonalność wywołuje teraz więcej problemów, niż rozwiązuje. |
| **Zamieniona przez inną funkcję?**   | Nr Teraz jest obsługiwana tylko standardowa komunikacja za pośrednictwem serwera sieci sprzedaży.  |
| **Powiązane obszary produktów**         | Baza danych kanału/Retail Modern POS   |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.  |

### <a name="dutch-swift-mt940"></a>Holenderski SWIFT MT940

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | W miejsce funkcji zlokalizowanej używana jest teraz funkcja ogólna.                    |
| **Zamieniona przez inną funkcję?**   | Tak, ta funkcja została zastąpiona funkcją zaawansowanego uzgadniania kont bankowych. |
| **Powiązane obszary produktów**         | Wszystkie moduły                                                                              |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.                           |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL dla Niemiec)

Ta funkcja generowała dane wyjściowe w formacie eXtensible Business Reporting Language (XBRL) dostosowane specjalnie do niemieckiej taksonomii eBilanz.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Brak wykorzystywania przez odbiorców.  |
| **Zamieniona przez inną funkcję?**   | Ta funkcja nie została zastąpiona przez inną funkcję, ale dla rynku niemieckiego jest dostępnych wiele wyspecjalizowanych pakietów XBRL oferujących rozbudowane funkcje XBRL. |
| **Powiązane obszary produktów**         | Management Reporter      |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.  |

### <a name="enterprise-portal-client"></a>Klient witryny Enterprise Portal

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Udostępnione jedną platformę kliencką.  |
| **Zamieniona przez inną funkcję?**   | Nowy klient sieci web jest oparty na metadanych formatu dla komputerów i modelu programowania, który został dostosowany do potrzeb rozszerzonej platformy internetowej. |
| **Powiązane obszary produktów**         | Wszystkie moduły  |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.   |

### <a name="environmental-sustainability"></a>Równowaga środowiskowa

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Brak wykorzystywania przez odbiorców i ograniczony zestaw funkcji.  |
| **Zamieniona przez inną funkcję?**   | Nr              |
| **Powiązane obszary produktów**         | Zgodność z przepisami i kontrole wewnętrzne, Rozrachunki z dostawcami  |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0. |

### <a name="form-activex-and-managed-host-controls"></a>Formanty ActiveX i Zarządzany host

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Formanty ActiveX i Zarządzany host są oparte na kliencie dla komputerów, który został wycofany. |
| **Zamieniona przez inną funkcję?**   | Rozszerzana struktura formantów pozwala tworzyć nowe formanty oparte na HTML, CSS i JavaScript i jest formantem pierwszej klasy w środowisku narzędziowym Microsoft Visual Studio. |
| **Powiązane obszary produktów**         | Wszystkie moduły     |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.       |

### <a name="generate-prenotes-by-using-a-batch"></a>Generowanie przelewów testowych przy użyciu zadania wsadowego

Przelewu testowego nie da się wygenerować za pomocą zadania wsadowego, ale może to zrobić użytkownik.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Nie istnieje żaden formularz do utrwalania i wyświetlania powstałego pliku przelewu testowego po jego wygenerowaniu przy użyciu zadania wsadowego. |
| **Zamieniona przez inną funkcję?**   | Przelewy testowe nadal można wygenerować, a użytkownik ma kontrolę nad miejscem zapisu pliku.   |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami, Rozrachunki z odbiorcami, Zaawansowane uzgadnianie konta bankowego  |
| **Stan**                         | Usunięto w rozwiązaniu AX w wersji 7.0.    |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Niemiecki eksport płatności i import wyciągu z konta DTAUS (sumy i transakcje)

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ten format nie jest już używany w Niemczech, ponieważ został zastąpiony przez funkcję Jednolity Obszar Płatniczy w Euro (SEPA).                    |
| **Zamieniona przez inną funkcję?**   | Tak, ta funkcja została zastąpiona funkcjami eksportu płatności SEPA i zaawansowanego uzgadniania kont bankowych w imporcie wyciągów z kont. |
| **Powiązane obszary produktów**         | Wszystkie moduły  |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="german-dtazv-payment-format"></a>Niemiecki format płatności DTAZV

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ten format nie jest już używany w Niemczech, ponieważ został zastąpiony przez funkcję SEPA. |
| **Zamieniona przez inną funkcję?**   | Eksport płatności SEPA    |
| **Powiązane obszary produktów**         | Wszystkie moduły   |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.    |

### <a name="german-mt940-import"></a>Niemiecki import MT940

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | W miejsce funkcji zlokalizowanej używana jest teraz funkcja ogólna.                    |
| **Zamieniona przez inną funkcję?**   | Tak, ta funkcja została zastąpiona funkcją zaawansowanego uzgadniania kont bankowych. |
| **Powiązane obszary produktów**         | Wszystkie moduły                                                                              |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.                           |

### <a name="german-xml-eu-sales-list"></a>Niemiecka lista sprzedaży do UE w formacie XML

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Format XML na potrzeby raportowania niemieckiej listy sprzedaży do UE nie jest już obsługiwany. W celu przesyłania raportu list sprzedaży do UE do niemieckiego urzędu skarbowego można używać tylko plików tekstowych w formacie ELMA5. |
| **Zamieniona przez inną funkcję?**   | Nr         |
| **Powiązane obszary produktów**         | Podatek        |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.   |

### <a name="gl-ssrs-reports"></a>Raporty GL SSRS

Usunięto raporty zawierające następujące elementy menu: **Sumaryczny bilans próbny**, **Szczegółowy bilans próbny**, **Plan kont**, **Dziennik inspekcji**, **Salda** i **Lista sald**.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Raporty finansowe Microsoft SQL Server Reporting Services (SSRS) zostały zastąpione funkcjami programu Management Reporter i domyślnymi raportami. |
| **Zamieniona przez inną funkcję?**   | Program Management Reporter (oznaczony jako **Raporty finansowe** w bieżącej wersji systemu Dynamics AX)    |
| **Powiązane obszary produktów**         | Księga główna   |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.   |

### <a name="infopart-and-formpart-metadata"></a>Metadane InfoPart i FormPart

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Włączona obsługa metadanych InfoPart i FormPart do tworzenia pól informacyjnych dla dwóch różnych klientów. |
| **Zamieniona przez inną funkcję?**   | Metadane InfoPart, które były uproszczoną definicję formularza, są konwertowane na formularz przez narzędzia uaktualniania. Metadane FormPart odwołujące się do formularza są zastępowane przez bardziej bezpośrednie odwołanie tworzone przez narzędzia uaktualniania. |
| **Powiązane obszary produktów**         | Wszystkie moduły    |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.        |

### <a name="main-account-list-page"></a>Strona listy konta głównego

Lista kont dla podmiotu prawnego i powiązane informacje o saldzie

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Informacje o saldzie są dostępne na stronie listy **Bilans próbnego** według konta i wymiaru.  |
| **Zamieniona przez inną funkcję?**   | Strona **Konta główne** zawiera tę samą listę kont, która jest dostępna na stronie listy **Konto główne**. Widok siatki na stronie **Konta główne** również pokazuje nawet mniejszy widok przypominający siatkę. |
| **Powiązane obszary produktów**         | Księga główna      |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.    |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>Raport dotyczący bankowych przepływów pieniężnych w Malezji i Singapurze

Ta funkcja umożliwia drukowanie raportu przepływów pieniężnych, który przedstawia transakcje oraz szczegóły przychodów i rozchodów gotówkowych w określonym zakresie dat dla wybranych kont bankowych.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Te same informacje można uzyskać z transakcji bankowej Informacje. |
| **Zamieniona przez inną funkcję?**   | Transakcja bankowa Informacje.                                            |
| **Powiązane obszary produktów**         | Zarządzanie gotówką i bankami                                                |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji.          |

### <a name="mexican-cfd-electronic-invoice"></a>Meksykański faktura elektroniczna CFD

Ta funkcja służyła do generowania meksykańskich faktur elektronicznych za pomocą metody Comprobante Fiscal Digital (CFD), gdzie firma podpisuje fakturę, żądając powiązanej autoryzacji od rządu. Ta funkcja obejmuje też miesięczne raporty zawierające wszystkie faktury elektroniczne, które zostały wystawione w danym okresie.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Metoda nie jest już stosowana. Metoda generowania faktur elektronicznych za pomocą metody CFD została wycofana przez urzędy skarbowe i zastąpiona metodą Comprobante Fiscal Digital a través de Internet (CFDI) , w której podpis składa zewnętrzny dostawca (PAC). Miesięczny raport został usunięty, a opcja Informacje pozwala użytkownikom wysyłać zapytania o transakcje historyczne. |
| **Zamieniona przez inną funkcję?**   | Nr    |
| **Powiązane obszary produktów**         | Rozrachunki z odbiorcami, Projekt   |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="mexico-realized-and-unrealized-vat"></a>Zrealizowany i niezrealizowany podatek VAT w Meksyku

Zarządzanie podatkiem od towarów i usług (VAT) w systemie Dynamics AX 2012 odbywało się przy użyciu właściwej dla Meksyku funkcji dla podatku niezrealizowanego.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Pokrywające się funkcje  |
| **Zamieniona przez inną funkcję?**   | Tak, ta funkcja została zastąpiona standardową funkcją podatku warunkowego dostępną w module podstawowym. |
| **Powiązane obszary produktów**         | Podatek   |
| **Stan**                         | Wycofane: nie określono daty usunięcia dla tej funkcji. |

### <a name="microsoft-outlook-integration"></a>Integracja z programem Microsoft Outlook


|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ta funkcja została zastąpiona integracją z Microsoft Exchange Server. |
| **Zamieniona przez inną funkcję?**   | Tak                                                                            |
| **Powiązane obszary produktów**         | Sales and Marketing                                                            |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.                                                 |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Prywatne blokowanie arkuszy zarządzania zapasami i magazynem

Nie da się już oznaczyć arkusza zapasów i lub arkusza magazynu jako prywatnego. Możliwe jest jedynie blokowanie arkuszy jako prywatnych dla grup użytkowników oraz blokowanie podczas edycji.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Nie stwierdzono używania funkcji. |
| **Zamieniona przez inną funkcję?**   | Nr                                     |
| **Powiązane obszary produktów**         | Zarządzanie zapasami                   |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.         |

### <a name="product-builder"></a>Konstruktor produktów

Konstruktor produktów był używany do dynamicznego konfigurowania elementów z zamówienia sprzedaży, zamówienia zakupu, zlecenia produkcyjnego, wyceny, oferty w ramach projektu lub zapotrzebowania na towary. Na podstawie modelu produktu, który miał zmienne modelowania użytkownik mógł wybrać wartości w celu spełnienia wymagań odbiorcy i uzyskać unikatowy wariant produktu, który miał BOM i marszrutę.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Konstruktor produktów pokazywał kod X ++ użytkownikom końcowym, a w aktualnej wersji systemu Dynamics AX nie powinno do tego dochodzić. Funkcja została usunięta, by uniknąć duplikowania się działań na zachodzących na siebie, dużych podstawach kodu.  |
| **Zamieniona przez inną funkcję?**   | Tak. Konfigurację opartą na ograniczeniach wprowadzono w systemie Dynamics AX 2012, w którym ogłoszono już wycofanie funkcji Konstruktor produktów w przyszłych wersjach. Technologia konfiguracji opartej na ograniczeniach jest wybierana w produktach głównych w celu włączenia konfiguracji. Aby dowiedzieć się więcej, zobacz [Omówienie konfiguracji produktu](../../../supply-chain/pim/build-product-configuration-model.md). |
| **Powiązane obszary produktów**         | Zarządzanie informacjami o produktach, Sprzedaż i marketing  |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.      |

### <a name="production-floor-app"></a>Aplikacja Production Floor
Jest to aplikacja dla urządzeń typu tablet z systemem Windows 8.1 RT i Windows 8.1 Pro.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | W przypadku zmiany klienta opartego na sieci web można uzyskać podobną funkcjonalność za pośrednictwem natywnego klienta Dynamics AX 7.0. Urządzenie karty zadań udostępnia interfejs użytkownika hali produkcyjnej zoptymalizowany pod kątem płytki dotykowej i tabletów. |
| **Zamieniona przez inną funkcję?**   | Tak. Urządzenie karty zadań, którego częścią jest natywna część Dynamics AX 7.0.                                                                           |
| **Powiązane obszary produktów**         | Kontrola produkcji                                                |
| **Stan**                         | Wycofane: Data usunięcia tej funkcji z Microsoft store nie jest jeszcze ustalona.                                                |


### <a name="rename-product-dimension"></a>Zmiana nazwy wymiaru produktu

Ta funkcja pozwala zmienić nazwę jednego z trzech standardowych wymiarów produktów (rozmiar, kolor lub styl) na taką, która lepiej pasuje do wymagań firmy. Można było zmieniać wszystkie etykiety, dla których użyto nazwy wymiaru produktu.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Bieżąca wersja systemu Dynamics AX nie obsługuje zmian etykiet w czasie wykonywania. |
| **Zamieniona przez inną funkcję?**   | Nr                                                                            |
| **Powiązane obszary produktów**         | Zarządzanie informacjami o produktach                                                |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.                                                |

### <a name="retail-server-connectivity-using-http"></a>Łączność serwera sieci sprzedaży przy użyciu protokołu HTTP

W programie Dynamics AX 2012 R3 serwer sieci sprzedaży mógł wykorzystywać komunikację za pośrednictwem protokołu HTTP (niezabezpieczonego). Było to uzupełnienie standardowej komunikacji wykorzystującej protokół HTTPS.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ze względu na nowe wymagania w kwestii bezpieczeństwa obecnie jest obsługiwana tylko zabezpieczona komunikacja przy użyciu protokołu TLS 1.2 (lub nowszego, jeśli jest dostępny). Samoobsługowy instalator automatycznie skonfiguruje komputer do obsługi tej komunikacji. |
| **Zamieniona przez inną funkcję?**   | Nr Teraz jest obsługiwana tylko standardowa komunikacja za pośrednictwem protokołu HTTPS. |
| **Powiązane obszary produktów**         | Serwer sprzedaży detalicznej  |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0. |

### <a name="role-center-pages"></a>Strony widoków głównych użytkownika

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Strony widoków głównych użytkownika zostały zbudowane na platformie przestarzałego modułu Enterprise Portal, który został zastąpiony przez platformę nowego klienta sieci web w bieżącej wersji systemu Dynamics AX. |
| **Zamieniona przez inną funkcję?**   | Nowy wzór formularza obszaru roboczego oferuje użytkownikom architekturę ukierunkowaną na proces z łatwym dostępem do często używanych zadań w ramach procesu.                       |
| **Powiązane obszary produktów**         | Wszystkie moduły    |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0   |

### <a name="sales-tax-jurisdictions"></a>Właściwe miejscowo urzędy skarbowe

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Brak wykorzystywania przez odbiorców i ograniczony zestaw funkcji. |
| **Zamieniona przez inną funkcję?**   | Nr                                           |
| **Powiązane obszary produktów**         | Podatki (od sprzedaży) na rynek amerykański                                 |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.               |

### <a name="sites-services"></a>Sites Services

Usługi Sites Services pozwalają tworzyć witryny internetowe, które poszerzają zasięg procesów biznesowych o Internet bez wsparcia działu informatycznego.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Infrastruktura Microsoft Azure używana w systemie Dynamics AX zawiera nowe funkcje, które z powodzeniem zastępują wycofane (np. witryny Azure). |
| **Zamieniona przez inną funkcję?**   | Nr   |
| **Powiązane obszary produktów**         | Rekrutacja kadr, Zarządzanie sprawami, Zapytania ofertowe, Rejestracja dostawcy, Obszary robocze współpracy dla możliwości i kampanii  |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.    |

### <a name="ssas-demand-forecasting-strategy"></a>Funkcjonalność strategii prognozowania popytu na platformie SSAS

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Konstrukcja funkcji nie jest obsługiwana w nowej architekturze chmury. |
| **Zamieniona przez inną funkcję?**   | Funkcja strategii prognozowania popytu wykorzystująca usługę Uczenie maszynowe Azure                           |
| **Powiązane obszary produktów**         | Planowanie główne                                                              |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.                                               |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Szczegóły puli faktur od dostawcy bez księgowania

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Niskie wykorzystanie. Ta funkcja została zastąpiona arkuszem faktur, który ma funkcje przepływu pracy. |
| **Zamieniona przez inną funkcję?**   | Funkcje przepływu pracy w arkuszu faktur.     |
| **Powiązane obszary produktów**         | Rozrachunki z dostawcami |
| **Stan**                         | Usunięto w systemie Dynamics AX 7.0.    |


### <a name="virtual-company-accounts"></a>Firmy wirtualne

Funkcja firm wirtualnych nie jest już obsługiwana w systemie Dynamics AX. Funkcja firm wirtualnych pozwalała użytkownikom na konfigurowanie tabel wspólnych dla zbioru firm. Opis tej funkcji można znaleźć w temacie [Firmy oraz firmy wirtualne](https://msdn.microsoft.com/library/aa834382(v=ax.10).aspx). Funkcja działa poprzez grupowanie tabel w zbiory przypisane do wirtualnych firm będących grupami istniejących „rzeczywistych” firm. Tworzone są zapytania, tak aby wszystkie firmy w firmie wirtualnej miały dostęp do danych w tabelach skojarzonych zbiorów tabel.

|   |  | 
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | - Firmy wirtualne należy skonfigurować przed zapisaniem danych w tabelach. Dostosowywanie firm wirtualnych do istniejącego wdrożenia jest bardzo trudne.<br><br>- Ponieważ w bieżącej wersji systemu Dynamics AX dokonano rozległej normalizacji danych, bardzo trudne stało się ustalanie danych, które należało dodać do zbiorów tabel. Na przykład trudno stwierdzić, które tabele należy udostępnić. Wszystkie tabele z odwołaniami z tabel, które były w firmie wirtualnej, też muszą być dodane. Z powodu normalizacji tabel nawet proste dane główne rozłożone między wiele tabel muszą być częścią firmy wirtualnej. Wszelkie popełnione tutaj błędy wywołają problemy funkcjonalne.<br><br>- Jeśli tabela jest częścią firmy wirtualnej, traci informacje o źródle danych i rejestrowane są tylko dane firmy wirtualnej.   |
| **Zamieniona przez inną funkcję?** | Tabele globalne mogą służyć do udostępniania tabel ze wszystkich firm. Obecnie nie ma funkcji zastępczej. |   
| **Powiązane obszary produktów**       | Wszystkie moduły |   
| **Stan**                       | Usunięto w systemie Dynamics AX 7.0.   |   

### <a name="windows-8-tablet-app"></a>Aplikacja na tablety z systemem Windows 8

Aplikacja na tablety z systemem Windows 8 zawierała funkcje wprowadzania i zatwierdzania wydatków.

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Program Finance and Operations jest zgodny z tabletami. Aplikacja na tablety przestała być potrzebna.    |
| **Zamieniona przez inną funkcję?**   | Nr          |
| **Powiązane obszary produktów**         | Zarządzanie wydatkami   |
| **Stan**                         | Usunięte: ta funkcja jest dostępna tylko w systemie Dynamics AX 2012 R3. |

### <a name="workplanner"></a>Planowanie pracy

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Niskie wykorzystanie |
| **Zamieniona przez inną funkcję?**   | Nie, ale strona **Relacja profilu**, którą można otworzyć ze strony **Grupy profilów**, obsługuje ten sam scenariusz biznesowy, co wycofana strona **Planowanie produkcji**. |
| **Powiązane obszary produktów**         | Czas i frekwencja     |
| **Stan**                         | Kod nie został usunięty. Jednakże formularz JmgWorkPlanner nie został zmigrowany.    |

### <a name="x-financial-statements"></a>Sprawozdania finansowe X++

|                                                 |                                                                                                          |
|-------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| <strong>Przyczyna wycofania/usunięcia</strong> |                         Ta funkcja została zastąpiona inną funkcją.                         |
|  <strong>Zamieniona przez inną funkcję?</strong>  | Program Management Reporter (oznaczony jako <strong>Raporty finansowe</strong> w bieżącej wersji systemu Dynamics AX) |
|     <strong>Powiązane obszary produktów</strong>     |                                              Księga główna                                              |
|             <strong>Stan</strong>             |                                      Usunięto w systemie Dynamics AX 2012                                      |

