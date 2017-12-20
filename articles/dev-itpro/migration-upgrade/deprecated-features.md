---
title: "Przestarzałe funkcje"
description: "W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia."
author: sericks007
manager: AnnBe
ms.date: 11/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 6
ms.translationtype: HT
ms.sourcegitcommit: 408854737847590841814ed74209618bbf22ec23
ms.openlocfilehash: b0eb041ee1a4309b010e510e1f7428d6c930e4a0
ms.contentlocale: pl-pl
ms.lasthandoff: 11/27/2017

---

# <a name="deprecated-features"></a>Przestarzałe funkcje

[!include[banner](../includes/banner.md)]

W tym temacie opisano funkcje, które zostały lub zostaną usunięte z programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.

## <a name="features-that-have-been-deprecated-in-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-with-platform-update-8"></a>Funkcje, które wycofano w programie Dynamics 365 for Finance and Operations Enterprise Edition (lipiec 2017 r.) z aktualizacją platformy 8

### <a name="warehouse-mobile-devices-portal"></a>Portal urządzeń przenośnych używanych w magazynie

Portal urządzeń przenośnych używanych w magazynie (WMDP) był autonomicznym składnikiem przeznaczonym do lokalnego samodzielnego instalowania. Ten składnik nie jest już obsługiwany w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. Funkcjonalność portalu WMDP została zastąpiona macierzystą aplikacją o ulepszonej funkcjonalności. 

|                                  |                                                 |
|----------------------------------|-------------------------------------------------|
| **Przyczyna wycofania**       | Pokrywające się funkcje.                        |
| **Zamieniona przez inną funkcję?** | Tak. Ta funkcja została zastąpiona przez moduł Finance and Operations — Magazynowanie. Aby uzyskać więcej informacji na temat konfiguracji i wymagań wstępnych, zobacz [Instalowanie i konfigurowanie programu Microsoft Dynamics 365 for Finance and Operations — Magazynowanie](../../supply-chain/warehousing/install-configure-warehousing-app.md). |
| **Moduły, których dotyczą zmiany**             | Zarządzanie magazynem, Zarządzanie transportem |

### <a name="advanced-bank-reconciliation-matching-rule-for-manual-matching"></a>Reguła zaawansowanego uzgadniania konta bankowego w ręcznym uzgadnianiu

Reguła uzgadniania używana do wybierania i zaznaczania dokumentu bankowego podczas ręcznego uzgadniania dokumentów w arkuszu uzgadniania.

|                                  |                                                                                        |
|----------------------------------|----------------------------------------------------------------------------------------|
| **Przyczyna wycofania**       | Ograniczone użycie.                                                                         |
| **Zamieniona przez inną funkcję?** | Nr Do wyszukiwania dokumentów na potrzeby uzgadniania należy używać funkcji filtrowania kolumn. |
| **Moduły, których dotyczą zmiany**             | Zarządzanie gotówką i bankami                                                               |

### <a name="windows-8-tablet-app"></a>Aplikacja na tablety z systemem Windows 8

Aplikacja na tablety z systemem Windows 8 zawierała funkcje wprowadzania i zatwierdzania wydatków.

|                                  |                                                                                          |
|----------------------------------|------------------------------------------------------------------------------------------|
| **Przyczyna wycofania**       | Program Finance and Operations jest zgodny z tabletami. Aplikacja na tablety przestała być potrzebna. |
| **Zamieniona przez inną funkcję?** | Nr                                                                                      |
| **Moduły, których dotyczą zmiany**             | Zarządzanie wydatkami                                                                       |


## <a name="features-that-have-been-deprecated-in-dynamics-365-for-operations-1611-with-platform-update-3"></a>Funkcje, które wycofano w programie Dynamics 365 for Operations 1611 po aktualizacji platformy 3

### <a name="aeb-payment-formats-for-spain"></a>Formaty płatności AEB dla Hiszpanii

Formaty płatności Consejo Superior Bancario służą do wysyłania plików przekazów do banku dla płatności odbiorcy i dostawcy. Zawartość tych formatów jest określana przez Asociación Española de Banca. Obejmuje ona Cuaderno 19, 32, 58, 34.

|                              |                                                                          |
|------------------------------|--------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Te formaty płatności nie są już używane.                                  |
| **Zamieniona przez inną funkcję?** | Tak, przez formaty płatności poleceniem przelewu i poleceniem zapłaty ISO20022 dla Hiszpanii |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z dostawcami, Rozrachunki z odbiorcami                                    |

### <a name="bank-payments-transfer-for-lithuania"></a>Przelewy płatnościami bankowymi dla Litwy

Przelewy płatnościami bankowymi na Litwie są generowane i drukowane przy użyciu formatu eksportu przelewów (LT). Na litewskim rynku w 2005 r. zaczęto używać ujednoliconego systemu bankowości elektronicznej LITAS.

|                              |                                                            |
|------------------------------|------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Te formaty płatności nie są już używane.                    |
| **Zamieniona przez inną funkcję?** | Tak, przez format płatności poleceniem przelewu ISO20022 dla Litwy |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z dostawcami                                           |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>Formaty płatności BBS Direkte Remittering dla Norwegii

Formaty płatności BBS Direkte Remittering zawierają funkcje eksportu inkasa płatności od odbiorcy (polecenie zapłaty) i importu komunikatu zwrotnego.

|                              |                                                                                                                                                                |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Te formaty płatności nie są już używane.                                                                                                                        |
| **Zamieniona przez inną funkcję?** | Format płatności od odbiorcy AvtaleGiro dla Norwegii może służyć do generowania komunikatów polecenia zapłaty. Import komunikatów zwrotnych zostanie zaimplementowany w przyszłych wersjach. |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z dostawcami, Rozrachunki z odbiorcami                                                                                                                          |

### <a name="chart-of-accounts-tool-for-spain"></a>Narzędzie planu kont dla Hiszpanii

To narzędzie jest używane, gdy plan kont w Hiszpanii wymaga dużych zmian. Użytkownicy mogą zaimportować nowy plan kont w formacie programu Microsoft Excel lub tekstowym, a także zaimportować sprawozdania finansowe.

|                              |                |
|------------------------------|----------------|
| **Przyczyna amortyzacji**       | Ograniczone użycie  |
| **Zamieniona przez inną funkcję?** | Nr             |
| **Moduły, których dotyczą zmiany**             | Księga główna |

### <a name="dom80-payment-format-for-belgium"></a>Format płatności Dom80 dla Belgii

Starszy belgijski format płatności dla inkasa płatności (polecenie zapłaty).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| **Przyczyna amortyzacji**      | Ten format płatności nie jest już używany.                  |
| **Zamieniona przez inną funkcję?** | Tak, przez format płatności poleceniem zapłaty ISO 20022 dla Belgii |
| **Moduły, których dotyczą zmiany**            | Rozrachunki z odbiorcami                                    |

### <a name="dtaezag-payment-formats-for-switzerland"></a>Formaty płatności DTA/EZAG dla Szwajcarii

Formaty DTA/EZAG są zintegrowane w systemie ESR, ponieważ mogą być nośnikami numeru odwołania. Numery odwołania nie są obowiązkowe i dlatego te formaty mogą służyć do przetwarzania wszelkich płatności dla dostawców. Te formaty są używane przez firmy, które mają konta bankowe w lokalizacji innej niż „Postfinance”.

|                              |                                                              |
|------------------------------|--------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Te formaty płatności nie są już używane.                      |
| **Zamieniona przez inną funkcję?** | Tak, przez format płatności poleceniem przelewu ISO20022 dla Szwajcarii |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z dostawcami                                             |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>Format płatności EDIFACT-DIRDEB dla Austrii

Format płatności EDIFACT-DIRDEB dla inkasa płatności (polecenie zapłaty).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ten format płatności nie jest już używany.                  |
| **Zamieniona przez inną funkcję?** | Tak, przez format płatności poleceniem zapłaty ISO 20022 dla Austrii |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z odbiorcami                                    |

### <a name="edivat-for-belgium"></a>EDIVAT dla Belgii

EDIVAT to starszy belgijski standard wysyłania deklaracji elektronicznych za pośrednictwem bezpiecznej poczty. System Microsoft Dynamics AX 2012 zachowuje rozwiązanie tylko do odczytu, aby umożliwić dostęp do danych historycznych.

|                              |                                      |
|------------------------------|--------------------------------------|
| **Przyczyna amortyzacji**       | Ta funkcjonalność nie jest już używana. |
| **Zamieniona przez inną funkcję?** | Nr                                   |
| **Moduły, których dotyczą zmiany**             | Księga główna                       |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>Format importu płatności eGiro EDIFACT CREMUL dla Norwegii

eGiro opiera się na międzynarodowym standardzie ONZ EDIFACT CREMUL (Multiple Credit Advice Message), który jest używany do automatycznego księgowania płatności od odbiorców. W systemie Microsoft Dynamics AX funkcjonalność eGiro jest zaimplementowana jako format importu płatności od odbiorców.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ten format płatności nie jest już używany.                                                     |
| **Zamieniona przez inną funkcję?** | Nr Ten format zostanie zastąpiony formatami importu wyciągów ISO 20022 w przyszłych wersjach. |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z odbiorcami                                                                       |

### <a name="external-inventory-for-poland"></a>Zapasy zewnętrzne dla Polski

Dowód przyjęcia towarów, które otrzymano od dostawcy do sprzedaży bez zakupu. Towary, które są obsługiwane w zewnętrznych zapasach, nie mają wpływu na zapasy standardowe i mogą być sprzedawane, a następnie automatycznie kupowane. Ten proces tworzy faktyczne przesunięcia magazynowe.

|                              |                                                 |
|------------------------------|-------------------------------------------------|
| **Przyczyna amortyzacji**       | Zamieniona przez inną funkcję                     |
| **Zamieniona przez inną funkcję?** | Tak, przez podstawową funkcjonalność konsygnacji przychodzącej |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z dostawcami, Zarządzanie zapasami          |

### <a name="financial-reports-generator-for-eastern-europe"></a>Generator raportów finansowych dla Europy Wschodniej

Narzędzie służące do konfigurowania zbierania danych na potrzeby raportów księgowych i podatkowych oraz eksportowania danych do szablonów raportów XLS i DOC.

|                              |                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ograniczone użycie                                                                            |
| **Zamieniona przez inną funkcję?** | Nr Narzędzie zostanie zastąpione konfiguracjami raportowania elektronicznego w przyszłych wersjach. |
| **Moduły, których dotyczą zmiany**             | Księga główna                                                                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Import transakcji płatności od odbiorców dla Finlandii

Można wybrać formatu importu dla płatności fińskich, który importuje transakcje płatności od odbiorców z zewnętrznego pliku dostarczonego przez bank.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ten format płatności nie jest już używany.                                                     |
| **Zamieniona przez inną funkcję?** | Nr Ten format zostanie zastąpiony formatami importu wyciągów ISO 20022 w przyszłych wersjach. |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z odbiorcami                                                                       |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>Import transakcji płatności do arkusza księgi głównej dla Finlandii

Format specyficzny dla Finlandii służy do importowania transakcji księgowych do księgi głównej.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ten format płatności nie jest już używany.                                                     |
| **Zamieniona przez inną funkcję?** | Nr Ten format zostanie zastąpiony formatami importu wyciągów ISO 20022 w przyszłych wersjach. |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z odbiorcami                                                                       |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>Integracja z systemem Isabel zsynchronizowana (CIS) dla Belgii

Isabel jest systemem szkieletowym bankowości elektronicznej w Europie i de facto normą w Belgii.

|                              |                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Integracja z klientami systemu Isabel została wycofana.                                                                |
| **Zamieniona przez inną funkcję?** | Nr Nieużywane formaty płatności zostały zastąpione formatem płatności poleceniem przelewu ISO20022 dla Belgii. |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z dostawcami                                                                                                     |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>Zmiany w planie kont i regułach księgowania dla Hiszpanii

Ta funkcja jest stosowana dla zmian w planie kont i regułach księgowania w Hiszpanii. Mapuje konta, ułatwiając przekształcanie starych planów kont na nowe plany kont oraz porównuje poprzedni rok obrachunkowy z nowym rokiem obrachunkowym, nawet jeśli zostały one zaksięgowane pod różnymi numerami kont.

|                              |                |
|------------------------------|----------------|
| **Przyczyna amortyzacji**       | Ograniczone użycie  |
| **Zamieniona przez inną funkcję?** | Nr             |
| **Moduły, których dotyczą zmiany**             | Księga główna |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Format płatności od dostawców Pagamento Fornittori

Starszy włoski format płatności dla poleceń przelewu.

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ten format płatności nie jest już używany.                  |
| **Zamieniona przez inną funkcję?** | Tak, przez format płatności poleceniem przelewu ISO20022 dla Włoch |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z dostawcami                                       |

### <a name="payment-export-formats-for-estonia"></a>Formaty eksportu płatności dla Estonii

Formaty Telehansa i Teleservice są używane do eksportu płatności bankowych.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| **Przyczyna amortyzacji**      | Te formaty płatności nie są już używane.                  |
| **Zamieniona przez inną funkcję?** | Tak, przez format płatności poleceniem przelewu ISO20022 dla Estonii |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z dostawcami                                         |

### <a name="payment-file-archive-for-norway"></a>Archiwum plików płatności dla Norwegii

Podczas generowania plików płatności są one automatycznie umieszczane w archiwum. Dotyczy to nawet plików, które zostały wcześniej zapisane lub odczytane.

|                              |                                                                    |
|------------------------------|--------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Zamieniona przez inną funkcję                                        |
| **Zamieniona przez inną funkcję?** | Tak, przez zarchiwizowane zadania raportowania elektronicznego                            |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z dostawcami, Rozrachunki z odbiorcami, Administrowanie organizacją |

### <a name="payment-import-formats-for-estonia"></a>Formaty importu płatności dla Estonii

Formaty Telehansa i TeleTeenus są używane do importu płatności bankowych.

|                              |                                                                                            |
|------------------------------|--------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Te formaty płatności nie są już używane.                                                    |
| **Zamieniona przez inną funkcję?** | Nr Te formaty zostaną zastąpione formatami importu wyciągów ISO 20022 w przyszłych wersjach. |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z odbiorcami                                                                        |

### <a name="performance-management-goal-workflow"></a>Przepływ pracy celu zarządzania wydajnością

Zarządzanie wydajnością obejmuje zarządzanie celami oraz integrację z przeglądami wydajności.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Moduł zarządzania wydajnością został przeprojektowany. Zmniejszono liczbę stron dotyczących celów, aby uprościć proces.                 |
| **Zamieniona przez inną funkcję?** | Nr Cele są wyświetlane menedżerom w samoobsługowym portalu dla menedżerów i mogą być zmieniane oraz wyświetlane przez menedżerów. |
| **Moduły, których dotyczą zmiany**             | Zarządzanie kapitałem ludzkim                                                                                                 |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>Formaty płatności Postgirot i Postgirot Utland dla Szwecji

Formaty płatności Postgirot i Postgirot Utland dla Szwecji.

|                              |                                                         |
|------------------------------|---------------------------------------------------------|
| **Przyczyna amortyzacji**       | Te formaty płatności nie są już używane.                 |
| **Zamieniona przez inną funkcję?** | Tak, przez format płatności poleceniem przelewu ISO20022 dla Szwecji |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z dostawcami                                        |

### <a name="radio-frequency-identifier"></a>Identyfikacja radiowa (RFID)

Identyfikacja radiowa (RFID) to technologia zbierania danych przy użyciu elektronicznych znaczników do przechowywania danych identyfikacyjnych bez konieczności bezpośredniego dostępu do czytnika w celu odczytania danych identyfikacyjnych.

|                              |                                               |
|------------------------------|-----------------------------------------------|
| **Przyczyna amortyzacji**       | Brak wykorzystywania przez odbiorców i ograniczony zestaw funkcji. |
| **Zamieniona przez inną funkcję?** | Nr                                            |
| **Moduły, których dotyczą zmiany**             | Zarządzanie zapasami                          |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>Raport o urzędowej numeracji faktur dla Łotwy

Łotewskie prawo zawiera określone reguły numerowania faktur sprzedaży. Funkcja pozwala przypisywać konkretne numery do faktur sprzedaży na podstawie użytkownika lub grupy użytkowników. Następnie można wygenerować raport lub plik XML. Można również wydrukować raport o użytych numerach faktur.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Urzędowa numeracja faktur nie musi już być stosowana. Raport o użytych numerach faktur nie jest już wymagany. |
| **Zamieniona przez inną funkcję?** | Nr                                                                                                                       |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z odbiorcami                                                                                                      |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Ustawianie imion i nazwisk menedżera i głównego księgowego firmy dla Litwy

Imiona i nazwiska menedżera oraz głównego księgowego firmy można podać w danych firmy i następnie używać w różnych raportach drukowanych lokalnie.

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Zamieniona przez inną funkcję                                     |
| **Zamieniona przez inną funkcję?** | Tak, w tym samym celu można używać konfiguracji urzędników.   |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z dostawcami, Rozrachunki z odbiorcami, Zaawansowane uzgadnianie konta bankowego |

### <a name="telepay-payment-formats-for-norway"></a>Formaty płatności TelePay dla Norwegii

Formaty płatności TelePay obejmują funkcje eksportu płatności dla dostawców (polecenie przelewu) i inkasa płatności od odbiorców (polecenie zapłaty).

|                              |                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Te formaty płatności nie są już używane.                                                        |
| **Zamieniona przez inną funkcję?** | Tak, przez format płatności poleceniem przelewu ISO20022 i format płatności od odbiorcy AvtaleGiro dla Norwegii |
| **Moduły, których dotyczą zmiany**            | Rozrachunki z dostawcami, Rozrachunki z odbiorcami                                                          |

### <a name="vendor-payment-export-formats-for-finland"></a>Formaty eksportu płatności dla dostawców dla Finlandii

Dwa formaty eksportowania płatności są dostępne dla Finlandii. LM02 (FI) jest używany w przypadku krajowych płatności, a LUM2 (FI) jest używany w przypadku płatności zagranicznych.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| **Przyczyna amortyzacji**       | Te formaty płatności nie są już używane.                  |
| **Zamieniona przez inną funkcję?** | Tak, przez format płatności poleceniem przelewu ISO20022 dla Finlandii |
| **Moduły, których dotyczą zmiany**            | Rozrachunki z dostawcami                                         |

### <a name="workflow-for-creating-goals"></a>Przepływ pracy tworzenia celów

Przepływ pracy zarządzania tworzeniem celów dla pracowników jest jednym z kilku przepływów pracy, które były dostępne jako pomoc w koordynowaniu procesu zarządzania wydajnością.

|                              |                                                                                                                                                                                                                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Zarządzanie wydajnością zostało całkowicie przeprojektowane w programie Microsoft Dynamics 365 for Finance and Operations.                                                                                                                                                                                                                                        |
| **Zamieniona przez inną funkcję?** | Przeprojektowana funkcjonalność zarządzania wydajnością zapewnia większą kontrolę nad treścią celów, miarami służącymi do śledzenia postępów oraz dołączaniem towarzyszącej dokumentacji. Cele można zapisywać jako szablony i ponownie wykorzystywać. Ta funkcja może pomóc szybciej konfigurować dodatkowe cele dla pracowników. |
| **Moduły, których dotyczą zmiany**            | Zarządzanie kapitałem ludzkim                                                                                                                                                                                                                                                                                                               |

## <a name="features-that-have-been-deprecated-in-dynamics-ax-70-releases"></a>Funkcje wycofane w wydaniach systemu Dynamics AX 7.0

### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Możliwość anulowania zmian na fakturze od dostawcy

|                              |                         |
|------------------------------|-------------------------|
| **Przyczyna amortyzacji**       | Chęć poprawy wydajności. |
| **Zamieniona przez inną funkcję?** | Nie                      |
| **Moduły, których dotyczą zmiany**            | Rozrachunki z dostawcami        |

### <a name="aif-axd-and-axbc-integrations"></a>Integracja z AIF, AxD i AxBC

W narzędziach integracji aplikacji (AIF) może dochodzić do wymiany danych z zewnętrznymi systemami poprzez logikę biznesową powiązaną z usługami. System Dynamics AX zawiera usługi, które są oparte na dokumentach i programie .NET Business Connector (AxBC). Dokument jest tworzony przy użyciu języka XML. Kod XML zawiera informacje nagłówka dodawane w celu tworzenia *komunikatów*, które mogą być przesyłane do systemu Dynamics AX lub z niego wysyłane. Przykłady dokumentów obejmują zamówienia sprzedaży i zamówienia zakupu. Jednak niemal wszystkie podmioty, np. odbiorca, mogą być reprezentowane przez dokument. Usługi oparte na dokumentach używają klas **Axd &lt;*dokument*&gt;**.

|                              |                                                                                                                                                                                                          |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Nie dało się przeskalować architektury narzędzi AIF i AxD na potrzeby usługi chmurowej. Wystąpiły problemy z wydajnością wokół importu zbiorczego.                                                                               |
| **Zamieniona przez inną funkcję?** | W bieżącej wersji systemu Dynamics AX ta funkcja jest zastąpiona strukturą importu/eksportu danych, która obsługuje cykliczny import/eksport zbiorczy. Dla klasy AxBC zaleca się użycie samych tabel. |
| **Moduły, których dotyczą zmiany**             | AxD, AxBC i AIF                                                                                                                                                                                     |

### <a name="boms-without-bom-versions"></a>BOM bez wersji BOM

Po wyłączeniu klucza konfiguracji **Wersje BOM** wersje list składowych (BOM) były ukrywane we wszystkich formularzach, a system wymuszał relację 1:1 między zwolnionymi produktami i listami BOM. W bieżącej wersji systemu Dynamics AX klucza konfiguracji **Wersje BOM** nie da się wyłączyć.

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**      | Obsługa klucza konfiguracji do kontrolowania wersji BOM nie jest dopasowana do skali środowiska chmurowego. |
| **Zamieniona przez inną funkcję?** | Nie                                                                                      |
| **Moduły, których dotyczą zmiany**            | Zarządzanie informacjami o produktach, Zarządzanie zapasami                                    |

### <a name="brazilian-bordero"></a>Brazylijski format Bordero

Specjalna metoda płatności dla firm brazylijskich

|                              |                                                                                                       |
|------------------------------|-------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Obsługa brazylijskiej metody płatności Bordero została wycofana dla lokalizacji w Brazylii |
| **Zamieniona przez inną funkcję?** | Nr                                                                                                    |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z dostawcami                                                                                      |

### <a name="brazilian-sintegra-statement"></a>Brazylijska deklaracja Sintegra

Krajowa deklaracja podatku ICMS

|                              |                                                                                                                       |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ta deklaracja nie ma już zastosowania w niektórych stanach Brazylii.                                                     |
| **Zamieniona przez inną funkcję?** | Nr Użytkownicy mogą użyć narzędzia Ogólne raportowanie elektroniczne do skonfigurowania deklaracji, jeśli jest to wymagane w określonych sytuacjach. |
| **Moduły, których dotyczą zmiany**             | Księgi podatkowe                                                                                                          |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Brazylijski tryb sytuacji awaryjnych SCAN dla NF-e

Środowisko awaryjne (SCAN) jest używane do generowania, eksportowania i importowania stanu z portalu Nota Fiscal eletrônica (NF-e), gdy środowisko Secretaria da Fazenda (SEFAZ) jest niedostępne.

|                              |                                                                             |
|------------------------------|-----------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ta metoda pracy awaryjnej nie jest już stosowana w niektórych stanach w Brazylii |
| **Zamieniona przez inną funkcję?** | Nr                                                                          |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z odbiorcami                                                         |

### <a name="business-analyzer"></a>Aplikacja Business Analyzer

Ta aplikacja mobilna pozwala użytkownikom przeglądać kluczowe pomiary biznesowe.

|                              |                                                                                                                                                               |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ta funkcja została zastąpiona inną funkcją.                                                                                                      |
| **Zamieniona przez inną funkcję?** | Pakiet materiałów do monitorowania wyników finansowych dla usługi Microsoft Power BI będzie zawierał najważniejsze mierniki finansowe, które wcześniej były dostępne w aplikacji Business Analyzer. |
| **Moduły, których dotyczą zmiany**             | Księga główna                                                                                                                                                |

### <a name="business-statistics"></a>Statystyki

Konfiguracja zapytań o statystyki biznesowe, które mogą ułatwić analizowanie funkcjonowania organizacji.

|                              |                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Istniejące podejście do analizy biznesowej (BI), niskie wykorzystanie przez odbiorców i ograniczony zestaw funkcji. |
| **Zamieniona przez inną funkcję?** | Nowe rozwiązanie BI dla aktualnej wersji systemu Dynamics AX.                                      |
| **Moduły, których dotyczą zmiany**             | Zaopatrzenie i sourcing, Rozrachunki z dostawcami, Sprzedaż i marketing, Rozrachunki z odbiorcami         |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>Funkcja zmiany daty dokumentu w Arkuszu zatwierdzania faktur

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Niskie wykorzystanie                                                               |
| **Zamieniona przez inną funkcję?** | Tak. Można zmienić datę dokumentu dla zaksięgowanej transakcji dostawcy. |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z dostawcami                                                        |

### <a name="clieop03-payment-format-for-the-netherlands"></a>Format płatności ClieOp03 dla Holandii

|                              |                                                                                                            |
|------------------------------|------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ten format nie jest już używany w Holandii, ponieważ został zastąpiony przez funkcję SEPA. |
| **Zamieniona przez inną funkcję?** | Eksport płatności SEPA                                                                                       |
| **Moduły, których dotyczą zmiany**             | Wszyscy                                                                                                        |

### <a name="compliance-center"></a>Centrum zgodności

Centrum zgodności było witryną Enterprise Portal do zarządzania wymaganiami dokumentacji dla inicjatyw zgodności związanych z ustawą Sarbanes-Oxley.

|                              |                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Brak wykorzystywania przez odbiorców. Program Microsoft SharePoint oferuje te same funkcje, które były dostępne w Centrum zgodności. |
| **Zamieniona przez inną funkcję?** | Nie                                                                                                                     |
| **Moduły, których dotyczą zmiany**             | Zgodność z przepisami i kontrole wewnętrzne                                                                                       |

### <a name="connector-for-microsoft-dynamics"></a>Connector for Microsoft Dynamics

To narzędzie zostało użyte do integracji najważniejszych danych z programu Microsoft Dynamics CRM do aplikacji systemu Microsoft Dynamics ERP.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ta funkcja została zastąpiona inną funkcją. |
| **Zamieniona przez inną funkcję?** | Integrator systemu Dynamics                                      |
| **Moduły, których dotyczą zmiany**             | Connector for Microsoft Dynamics                         |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Jednostka kontenera i wielowymiarowe zapasy na stanie

|                              |                                                                                                                                                                 |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Pokrywające się funkcje                                                                                                                                         |
| **Zamieniona przez inną funkcję?** | Tak. Od wersji AX 2012 ta funkcja jest zastąpiona zestawem funkcji skonsolidowanych szarż produkcyjnych. Zestaw zawiera skonsolidowany widok dostępnych zapasów. |
| **Moduły, których dotyczą zmiany**             | Zarządzanie informacjami o produktach, Kontrola produkcji, Zarządzanie zapasami, Sprzedaż i marketing                                                                   |

### <a name="cue-group-metadata"></a>Metadane grupy wskaźników

|                              |                                                                                                                                                                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Grupy wskaźników były używane do wyświetlania jednego lub kilku wskaźników w obszarze pola informacji. Liczba pobrań była ograniczona i występowały też problemy z wydajnością, ponieważ zmiana rekordu w formularzu nadrzędnym powodowała tworzenie jednej kwerendy na wskaźnik w grupie wskaźników. |
| **Zamieniona przez inną funkcję?** | Nie                                                                                                                                                                                                                            |
| **Moduły, których dotyczą zmiany**             | Wszyscy                                                                                                                                                                                                                           |

### <a name="cue-metadata"></a>Metadane wskaźnika

|                              |                                                                                                                                                                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Metadane wskaźnika były ograniczone do liczby lub sumy.                                                                                                                                                                                   |
| **Zamieniona przez inną funkcję?** | Wprowadzono metadane kafelka, by poprawić elastyczność modelowania. Można na przykład modelować aktualne liczby, nawigację i kluczowe wskaźniki wydajności (KPI). Metadane wskaźnika zostały bezpośrednio zastąpione przez metadane kafelka z liczbami. |
| **Moduły, których dotyczą zmiany**             | Wszyscy                                                                                                                                                                                                                                     |

### <a name="danish-check-format"></a>Duński format czeku

|                              |                                                                                                                         |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Obsługa duńskiego układu formatu czeku została wycofana i raport został usunięty z lokalizacji DK. |
| **Zamieniona przez inną funkcję?** | Nie                                                                                                                      |
| **Moduły, których dotyczą zmiany**             | Wszyscy                                                                                                                     |

### <a name="data-partitions"></a>Partycje danych

Partycje danych zapewniają logiczne oddzielenie danych w bazie danych systemu Microsoft Dynamics AX.

|   |   |
|---|---|
| **Przyczyna amortyzacji**       | Partycje danych zostały wprowadzone w systemie Microsoft Dynamics AX 2012 R2, aby umożliwić izolowanie danych. W typowym scenariuszu firma ma oddziały. Dane z jednego oddziału firmy nie powinny być widoczne w innym oddziale, mimo że oba oddziały są zarządzane przez ten sam dział IT. Jednak były wymagane dodatkowe skrypty i towarzyszące zarządzanie programem w celu utworzenia nowych partycji i wypełnienia ich danymi oraz utworzenia kopii zapasowych danych partycji. W chmurze, gdzie mamy dostęp do usług bazy danych (baza danych SQL Microsoft Azure) w postaci platformy jako usługi (PaaS), znacznie bardziej efektywne jest używanie bazy danych jako kontenera izolacji niż konfigurowanie izolacji w programie. Niezależnie od tego, czy partycjonowanie danych jest wymagane dla oddziałów, wielu dzierżawców czy tylko ze względu na skalę, jesteśmy przekonani, że wszystkie scenariusze można lepiej obsługiwać za pomocą wielu wystąpień systemu Finance and Operations. |
| **Zamieniona przez inną funkcję?** | Jeśli separacja poziomów bazy danych ma krytyczne znaczenie, klienci korzystający z partycji danych muszą używać wielu wystąpień systemu Finance and Operations.    |
| **Moduły, których dotyczą zmiany**             | Wszyscy  |

### <a name="database-and-file-share-storage-for-attachments"></a>Przechowywanie załączników w bazach danych i udziałach plików
System Microsoft Dynamics AX 2012 pozwalał na przechowywania załączników w bazach danych i udziałach plików. Obie te opcje nie są już obsługiwane.

|                              |                                        |
|------------------------------|----------------------------------------|
| **Przyczyna amortyzacji**       | Przechowywanie w udziałach plików nie jest już obsługiwane, ponieważ środowiska hostowane w chmurze nie mogą się komunikować z lokalnymi udziałami plików. Przechowywanie w bazie danych zostało zastąpione magazynem obiektów blob w usłudze Azure. Magazyn obiektów blob Azure odpowiada przechowywaniu w bazie danych, ponieważ dokumenty są dostępne wyłącznie za pośrednictwem formularzy klienta programu Dynamics 365 for Finance and Operations. Zapewnia to dodatkową korzyść w postaci magazynu, który nie wpływa negatywnie na wydajność bazy danych. Magazyn obiektów blob jest domyślnym mechanizmem przechowywania modułu Zarządzanie dokumentami i działa natychmiast. |
| **Zamieniona przez inną funkcję?** | Przechowywanie w bazie danych zostało zastąpione magazynem obiektów blob w usłudze Azure.       |
| **Moduły, których dotyczą zmiany**             | Wszystko                   |

### <a name="delimitation"></a>Ogranicznik

|                              |                                        |
|------------------------------|----------------------------------------|
| **Przyczyna amortyzacji**       | Nie stwierdzono używania funkcji. |
| **Zamieniona przez inną funkcję?** | Nie                                     |
| **Moduły, których dotyczą zmiany**             | Czas i frekwencja                    |

### <a name="desktop-client"></a>Klient komputerowy

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Środowisko klienta systemu Dynamics AX zostało przeprojektowane, by poprawić funkcjonalność wielu platform i urządzeń.                      |
| **Zamieniona przez inną funkcję?** | Nowy klient sieci web jest oparty na metadanych formatu dla komputerów i modelu programowania, który został dostosowany do potrzeb rozszerzonej platformy internetowej. |
| **Moduły, których dotyczą zmiany**             | Wszystko                                                                                                                                    |

### <a name="direct-database-connection"></a>Bezpośrednie połączenie z bazą danych

W programie Dynamics AX 2012 R3 aplikacja Retail Modern POS mogła się łączyć bezpośrednio z bazą danych kanału w podobny sposób, jak robi to aplikacja Enterprise POS. Było to uzupełnienie standardowej metody komunikacji używanej przez aplikację Retail Modern POS, czyli korzystania z pośrednictwa serwera sieci sprzedaży.  

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Bezpośrednia łączność z bazą danych wymagała protokołów o słabszych zabezpieczeniach i była używana głównie do osiągnięcia najwyższej wydajności. Ze względu na ulepszenia w dziedzinach wydajności i zabezpieczeń, które wprowadzono przy okazji programu Dynamics 365 for Finance and Operations, ta funkcjonalność wywołuje teraz więcej problemów, niż rozwiązuje. |
| **Zamieniona przez inną funkcję?** | Nr Teraz jest obsługiwana tylko standardowa komunikacja za pośrednictwem serwera sieci sprzedaży.    |
| **Moduły, których dotyczą zmiany**             | Baza danych kanału/Retail Modern POS                                    |

### <a name="dutch-swift-mt940"></a>Holenderski SWIFT MT940

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | W miejsce funkcji zlokalizowanej używana jest teraz funkcja ogólna.                                                                                                                                                                 |
| **Zamieniona przez inną funkcję?** | Tak, ta funkcja została zastąpiona funkcją zaawansowanego uzgadniania kont bankowych. |
| **Moduły, których dotyczą zmiany**             | Wszystko                                                                                                                                                                                                                                   |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL dla Niemiec)

Ta funkcja generowała dane wyjściowe w formacie eXtensible Business Reporting Language (XBRL) dostosowane specjalnie do niemieckiej taksonomii eBilanz.

|                              |                                                                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Brak wykorzystywania przez odbiorców.                                                                                                                                                 |
| **Zamieniona przez inną funkcję?** | Ta funkcja nie została zastąpiona przez inną funkcję, ale dla rynku niemieckiego jest dostępnych wiele wyspecjalizowanych pakietów XBRL oferujących rozbudowane funkcje XBRL. |
| **Moduły, których dotyczą zmiany**             | Program Management Reporter                                                                                                                                                    |

### <a name="enterprise-portal-client"></a>Klient witryny Enterprise Portal

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Udostępnione jedną platformę kliencką.                                                                                            |
| **Zamieniona przez inną funkcję?** | Nowy klient sieci web jest oparty na metadanych formatu dla komputerów i modelu programowania, który został dostosowany do potrzeb rozszerzonej platformy internetowej. |
| **Moduły, których dotyczą zmiany**             | Wszyscy                                                                                                                                    |

### <a name="environmental-sustainability"></a>Równowaga środowiskowa

|                              |                                                    |
|------------------------------|----------------------------------------------------|
| **Przyczyna amortyzacji**       | Brak wykorzystywania przez odbiorców i ograniczony zestaw funkcji.       |
| **Zamieniona przez inną funkcję?** | Nie                                                 |
| **Moduły, których dotyczą zmiany**             | Zgodność z przepisami i kontrole wewnętrzne, Rozrachunki z dostawcami |

### <a name="form-activex-and-managed-host-controls"></a>Formanty ActiveX i Zarządzany host

|                              |                                                                                                                                                                                               |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Formanty ActiveX i Zarządzany host są oparte na kliencie dla komputerów, który został wycofany.                                                                                                             |
| **Zamieniona przez inną funkcję?** | Rozszerzana struktura formantów pozwala tworzyć nowe formanty oparte na HTML, CSS i JavaScript i jest formantem pierwszej klasy w środowisku narzędziowym Microsoft Visual Studio. |
| **Moduły, których dotyczą zmiany**             | Wszyscy                                                                                                                                                                                           |

### <a name="generate-prenotes-by-using-a-batch"></a>Generowanie przelewów testowych przy użyciu zadania wsadowego

Przelewu testowego nie da się wygenerować za pomocą zadania wsadowego, ale może to zrobić użytkownik.

|                              |                                                                                                        |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Nie istnieje żaden formularz do utrwalania i wyświetlania powstałego pliku przelewu testowego po jego wygenerowaniu przy użyciu zadania wsadowego. |
| **Zamieniona przez inną funkcję?** | Przelewy testowe nadal można wygenerować, a użytkownik ma kontrolę nad miejscem zapisu pliku.   |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z dostawcami, Rozrachunki z odbiorcami, Zaawansowane uzgadnianie konta bankowego                                        |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Niemiecki eksport płatności i import wyciągu z konta DTAUS (sumy i transakcje)

|                              |                                                                                                                                                                                                                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ten format nie jest już używany w Niemczech, ponieważ został zastąpiony przez funkcję Jednolity Obszar Płatniczy w Euro (SEPA).                                                                                                                                                                 |
| **Zamieniona przez inną funkcję?** | Tak, ta funkcja została zastąpiona funkcjami eksportu płatności SEPA i zaawansowanego uzgadniania kont bankowych w imporcie wyciągów z kont. |
| **Moduły, których dotyczą zmiany**             | Wszystko                                                                                                                                                                                                                                                                                            |

### <a name="german-dtazv-payment-format"></a>Niemiecki format płatności DTAZV

|                              |                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ten format nie jest już używany w Niemczech, ponieważ został zastąpiony przez funkcję SEPA. |
| **Zamieniona przez inną funkcję?** | Eksport płatności SEPA                                                                               |
| **Moduły, których dotyczą zmiany**             | Wszyscy                                                                                                |

### <a name="german-mt940-import"></a>Niemiecki import MT940

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | W miejsce funkcji zlokalizowanej używana jest teraz funkcja ogólna.                                                                                                                                                                 |
| **Zamieniona przez inną funkcję?** | Tak, ta funkcja została zastąpiona funkcją zaawansowanego uzgadniania kont bankowych. |
| **Moduły, których dotyczą zmiany**             | Wszystko                                                                                                                                                                                                                                   |

### <a name="german-xml-eu-sales-list"></a>Niemiecka lista sprzedaży do UE w formacie XML

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Format XML na potrzeby raportowania niemieckiej listy sprzedaży do UE nie jest już obsługiwany. W celu przesyłania raportu list sprzedaży do UE do niemieckiego urzędu skarbowego można używać tylko plików tekstowych w formacie ELMA5. |
| **Zamieniona przez inną funkcję?** | Nie                                                                                                                                                                                 |
| **Moduły, których dotyczą zmiany**             | Podatek                                                                                                                                                                                |

### <a name="gl-ssrs-reports"></a>Raporty GL SSRS

Usunięto raporty zawierające następujące elementy menu: **Sumaryczny bilans próbny**, **Szczegółowy bilans próbny**, **Plan kont**, **Dziennik inspekcji**, **Salda** i **Lista sald**.

|                              |                                                                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Raporty finansowe Microsoft SQL Server Reporting Services (SSRS) zostały zastąpione funkcjami programu Management Reporter i domyślnymi raportami. |
| **Zamieniona przez inną funkcję?** | Program Management Reporter (oznaczony jako **Raporty finansowe** w bieżącej wersji systemu Dynamics AX)                                                  |
| **Moduły, których dotyczą zmiany**            | Księga główna                                                                                                                               |

### <a name="infopart-and-formpart-metadata"></a>Metadane InfoPart i FormPart

|                              |                                                                                                                                                                                                                                |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Włączona obsługa metadanych InfoPart i FormPart do tworzenia pól informacyjnych dla dwóch różnych klientów.                                                                                                                                    |
| **Zamieniona przez inną funkcję?** | Metadane InfoPart, które były uproszczoną definicję formularza, są konwertowane na formularz przez narzędzia uaktualniania. Metadane FormPart odwołujące się do formularza są zastępowane przez bardziej bezpośrednie odwołanie tworzone przez narzędzia uaktualniania. |
| **Moduły, których dotyczą zmiany**             | Wszyscy                                                                                                                                                                                                                            |

### <a name="main-account-list-page"></a>Strona listy konta głównego

Lista kont dla podmiotu prawnego i powiązane informacje o saldzie

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Informacje o saldzie są dostępne na stronie listy **Bilans próbnego** według konta i wymiaru.                                                                                      |
| **Zamieniona przez inną funkcję?** | Strona **Konta główne** zawiera tę samą listę kont, która jest dostępna na stronie listy **Konto główne**. Widok siatki na stronie **Konta główne** również pokazuje nawet mniejszy widok przypominający siatkę. |
| **Moduły, których dotyczą zmiany**             | Księga główna                                                                                                                                                                     |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>Raport dotyczący bankowych przepływów pieniężnych w Malezji i Singapurze

Ta funkcja umożliwia drukowanie raportu przepływów pieniężnych, który przedstawia transakcje oraz szczegóły przychodów i rozchodów gotówkowych w określonym zakresie dat dla wybranych kont bankowych.

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Te same informacje można uzyskać z transakcji bankowej Informacje. |
| **Zamieniona przez inną funkcję?** | Transakcja bankowa Informacje.                                            |
| **Moduły, których dotyczą zmiany**             | Zarządzanie gotówką i bankami                                                |

### <a name="mexican-cfd-electronic-invoice"></a>Meksykański faktura elektroniczna CFD

Ta funkcja służyła do generowania meksykańskich faktur elektronicznych za pomocą metody Comprobante Fiscal Digital (CFD), gdzie firma podpisuje fakturę, żądając powiązanej autoryzacji od rządu. Ta funkcja obejmuje też miesięczne raporty zawierające wszystkie faktury elektroniczne, które zostały wystawione w danym okresie.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                           |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Metoda nie jest już stosowana. Metoda generowania faktur elektronicznych za pomocą metody CFD została wycofana przez urzędy skarbowe i zastąpiona metodą Comprobante Fiscal Digital a través de Internet (CFDI) , w której podpis składa zewnętrzny dostawca (PAC). Miesięczny raport został usunięty, a opcja Informacje pozwala użytkownikom wysyłać zapytania o transakcje historyczne. |
| **Zamieniona przez inną funkcję?** | Nie                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z odbiorcami, Projekt                                                                                                                                                                                                                                                                                                                                                                              |

### <a name="mexico-realized-and-unrealized-vat"></a>Zrealizowany i niezrealizowany podatek VAT w Meksyku

Zarządzanie podatkiem od towarów i usług (VAT) w systemie Microsoft Dynamics AX 2012 odbywało się przy użyciu właściwej dla Meksyku funkcji dla „podatku niezrealizowanego”.

|                              |                                                                                                                     |
|------------------------------|---------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Pokrywające się funkcje                                                                                             |
| **Zamieniona przez inną funkcję?** | Tak, ta funkcja została zastąpiona standardową funkcją podatku warunkowego dostępną w module podstawowym. |
| **Moduły, których dotyczą zmiany**             | Podatek                                                                                                                 |

### <a name="microsoft-outlook-integration"></a>Integracja z programem Microsoft Outlook

|                              |                                                                                |
|------------------------------|--------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ta funkcja została zastąpiona integracją z serwerem programu Microsoft Exchange. |
| **Zamieniona przez inną funkcję?** | Tak                                                                            |
| **Moduły, których dotyczą zmiany**             | Sprzedaż i marketing                                                            |

### <a name="payroll-information-in-human-resources"></a>Informacje listy płac w module Zasoby ludzkie

Informacje listy płac w module Zasoby ludzkie

|                              |                                                                                                                                                                                                                                                                                                                              |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ta funkcja została zastąpiona stronami podstawowych modułów Lista płac i Zasoby ludzkie.                                                                                                                                                                                                                                              |
| **Zamieniona przez inną funkcję?** | **Świadczenia**, **Zarobki** i inne pokrewne strony, które były poprzednio używane w module US Payroll, otrzymały nową konfigurację i są teraz częścią konfiguracji podstawowych modułów Zasoby ludzkie, aby ułatwić zewnętrzne przetwarzanie listy płac. Ta funkcja jest dostępna za pomocą klucza konfiguracji **Zasoby ludzkie 1** &gt; **Lista płac**. |
| **Moduły, których dotyczą zmiany**             | Zasoby ludzkie, Lista płac                                                                                                                                                                                                                                                                                                     |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Prywatne blokowanie arkuszy zarządzania zapasami i magazynem

Nie da się już oznaczyć arkusza zapasów i lub arkusza magazynu jako prywatnego. Możliwe jest jedynie blokowanie arkuszy jako prywatnych dla grup użytkowników oraz blokowanie podczas edycji.

|                              |                                        |
|------------------------------|----------------------------------------|
| **Przyczyna amortyzacji**       | Nie stwierdzono używania funkcji. |
| **Zamieniona przez inną funkcję?** | Nie                                     |
| **Moduły, których dotyczą zmiany**             | Zarządzanie zapasami                   |

### <a name="product-builder"></a>Konstruktor produktów

Konstruktor produktów był używany do dynamicznego konfigurowania elementów z zamówienia sprzedaży, zamówienia zakupu, zlecenia produkcyjnego, wyceny, oferty w ramach projektu lub zapotrzebowania na towary. Na podstawie modelu produktu, który miał zmienne modelowania użytkownik mógł wybrać wartości w celu spełnienia wymagań odbiorcy i uzyskać unikatowy wariant produktu, który miał BOM i marszrutę.

|                              |                                                                                                                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Konstruktor produktów pokazywał kod X ++ użytkownikom końcowym, a w aktualnej wersji systemu Dynamics AX nie powinno do tego dochodzić. Funkcja została usunięta, by uniknąć duplikowania się działań na zachodzących na siebie, dużych podstawach kodu. |
| **Zamieniona przez inną funkcję?** | Konfiguracja produktu                                                                                                                                                                                   |
| **Moduły, których dotyczą zmiany**             | Zarządzanie informacjami o produktach, Sprzedaż i marketing                                                                                                                                                     |

### <a name="rename-product-dimension"></a>Zmiana nazwy wymiaru produktu

Ta funkcja pozwala zmienić nazwę jednego z trzech standardowych wymiarów produktów (rozmiar, kolor lub styl) na taką, która lepiej pasuje do wymagań firmy. Można było zmieniać wszystkie etykiety, dla których użyto nazwy wymiaru produktu.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Bieżąca wersja systemu Dynamics AX nie obsługuje zmian etykiet w czasie wykonywania. |
| **Zamieniona przez inną funkcję?** | Nr                                                                            |
| **Moduły, których dotyczą zmiany**             | Zarządzanie informacjami o produktach                                                |

### <a name="retail-server-connectivity-using-http"></a>Łączność serwera sieci sprzedaży przy użyciu protokołu HTTP

W programie Dynamics AX 2012 R3 serwer sieci sprzedaży mógł wykorzystywać komunikację za pośrednictwem protokołu HTTP (niezabezpieczonego). Było to uzupełnienie standardowej komunikacji wykorzystującej protokół HTTPS.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ze względu na nowe wymagania w kwestii bezpieczeństwa obecnie jest obsługiwana tylko zabezpieczona komunikacja przy użyciu protokołu TLS 1.2 (lub nowszego, jeśli jest dostępny). Samoobsługowy instalator automatycznie skonfiguruje komputer do obsługi tej komunikacji. |
| **Zamieniona przez inną funkcję?** | Nr Teraz jest obsługiwana tylko standardowa komunikacja za pośrednictwem protokołu HTTPS.                                                                           |
| **Moduły, których dotyczą zmiany**             | Serwer sprzedaży detalicznej                                                |

### <a name="role-center-pages"></a>Strony widoków głównych użytkownika

|                              |                                                                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Strony widoków głównych użytkownika zostały zbudowane na platformie przestarzałego modułu Enterprise Portal, który został zastąpiony przez platformę nowego klienta sieci web w bieżącej wersji systemu Dynamics AX. |
| **Zamieniona przez inną funkcję?** | Nowy wzór formularza obszaru roboczego oferuje użytkownikom architekturę ukierunkowaną na proces z łatwym dostępem do często używanych zadań w ramach procesu.                       |
| **Moduły, których dotyczą zmiany**             | Wszyscy                                                                                                                                                                      |

### <a name="sales-tax-jurisdictions"></a>Właściwe miejscowo urzędy skarbowe

|                              |                                              |
|------------------------------|----------------------------------------------|
| **Przyczyna amortyzacji**       | Brak wykorzystywania przez odbiorców i ograniczony zestaw funkcji. |
| **Zamieniona przez inną funkcję?** | Nie                                           |
| **Moduły, których dotyczą zmiany**             | Podatki (od sprzedaży) na rynek amerykański                                 |

### <a name="shipping-carrier-interface"></a>Interfejs firmy przewozowej

|                              |                                                                                                                                                 |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Pokrywające się funkcje                                                                                                                         |
| **Zamieniona przez inną funkcję?** | Tak, ta funkcja została częściowo zastąpiona funkcjami modułu Zarządzanie transportem, ale nie jest jeszcze zastąpiona w podstawowym module Zarządzanie magazynem (WMS I). |
| **Moduły, których dotyczą zmiany**             | Sprzedaż i marketing, Zarządzanie magazynem                                                                                                       |

### <a name="sites-services"></a>Sites Services

Usługi Sites Services pozwalają tworzyć witryny internetowe, które poszerzają zasięg procesów biznesowych o Internet bez wsparcia działu informatycznego.

|                              |                                                                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Infrastruktura Microsoft Azure używana w systemie Dynamics AX zawiera nowe funkcje, które z powodzeniem zastępują wycofane (np. witryny Azure). |
| **Zamieniona przez inną funkcję?** | Nie                                                                                                                                       |
| **Moduły, których dotyczą zmiany**             | Rekrutacja kadr, zarządzanie sprawami, zapytania ofertowe, rejestracji dostawców                                                                  |

### <a name="ssas-demand-forecasting-strategy"></a>Funkcjonalność strategii prognozowania popytu na platformie SSAS

|                              |                                                                              |
|------------------------------|------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Konstrukcja funkcji nie jest obsługiwana w nowej architekturze chmury. |
| **Zamieniona przez inną funkcję?** | Funkcja strategii prognozowania popytu wykorzystująca usługę Uczenie maszynowe Azure                           |
| **Moduły, których dotyczą zmiany**             | Planowanie                                                                     |

### <a name="travel-requisitions"></a>Wnioski wyjazdowe

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Niskie wykorzystanie i większość funkcji była dostępna w witrynie Enterprise Portal. |
| **Zamieniona przez inną funkcję?** | Nie                                                              |
| **Moduły, których dotyczą zmiany**             | Zarządzanie wydatkami                                              |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Szczegóły puli faktur od dostawcy bez księgowania

|                              |                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Niskie wykorzystanie. Ta funkcja została zastąpiona arkuszem faktur, który ma funkcje przepływu pracy. |
| **Zamieniona przez inną funkcję?** | Funkcje przepływu pracy w arkuszu faktur.                                                           |
| **Moduły, których dotyczą zmiany**             | Rozrachunki z dostawcami                                                                                        |

### <a name="virtual-company-accounts"></a>Firmy wirtualne

Funkcja firm wirtualnych nie jest już obsługiwana w systemie Dynamics AX. Funkcja firm wirtualnych pozwalała użytkownikom na konfigurowanie tabel wspólnych dla zbioru firm. Opis tej funkcji można znaleźć w temacie [Firmy oraz firmy wirtualne](https://msdn.microsoft.com/en-us/library/aa834382(v=ax.10).aspx). Funkcja działa poprzez grupowanie tabel w zbiory przypisane do wirtualnych firm będących grupami istniejących „rzeczywistych” firm. Tworzone są zapytania, tak aby wszystkie firmy w firmie wirtualnej miały dostęp do danych w tabelach skojarzonych zbiorów tabel.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><b>Przyczyna amortyzacji</b></td>
<td><ul>
<li>Firmy wirtualne należy skonfigurować przed zapisaniem danych w tabelach. Dostosowywanie firm wirtualnych do istniejącego wdrożenia jest bardzo trudne.</li>
<li>Ponieważ w bieżącej wersji systemu Microsoft Dynamics AX dokonano rozległej normalizacji danych, bardzo trudne stało się ustalanie danych, które należało dodać do zbiorów tabel. Na przykład trudno stwierdzić, które tabele należy udostępnić. Wszystkie tabele z odwołaniami z tabel, które były w firmie wirtualnej, też muszą być dodane. Z powodu normalizacji tabel nawet proste dane główne rozłożone między wiele tabel muszą być częścią firmy wirtualnej. Wszelkie popełnione tutaj błędy wywołają problemy funkcjonalne.</li>
<li>Jeśli tabela jest częścią firmy wirtualnej, traci informacje o źródle danych i rejestrowane są tylko dane firmy wirtualnej.</li>
</ul></td>
</tr>
<tr class="even">
<td><b>Zamieniona przez inną funkcję?</b></td>
<td>Tabele globalne mogą służyć do udostępniania tabel ze wszystkich firm. Obecnie nie ma funkcji zastępczej.</td>
</tr>
<tr class="odd">
<td><b>Moduły, których dotyczą zmiany</b></td>
<td>Nie dotyczy</td>
</tr>
</tbody>
</table>

### <a name="warehouse-management-ii"></a>Zarządzanie magazynem II

|                              |                                                                                                                                                                                                                                                                                                             |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Rozwiązanie WMS II (Zarządzania magazynem II), które było dostępne w module **Zarządzanie zapasami**, dubluje funkcje dostępne w module **Zarządzanie magazynem**, który został udostępniony w systemie Microsoft Dynamics AX 2012 R3.                                                                         |
| **Zamieniona przez inną funkcję?** | Moduł **Zarządzanie magazynem**, który został udostępniony w wersjach systemu AX 2012 R3, Microsoft Dynamics AX 2012 R3 CU8 i Microsoft Dynamics AX 2012 R3 CU9, zastępuje funkcje modułu WMS II. Nowy moduł ma bardziej zaawansowane funkcje i elastyczniejsze procesy zarządzania magazynem niż oferowane w module Zarządzanie magazynem II. |
| **Moduły, których dotyczą zmiany**             | Zarządzanie zapasami, sprzedaż i marketing, zaopatrzenie i sourcing                                                                                                                                                                                                                                         |

### <a name="worker-reminders-in-human-resources"></a>Przypomnienia dla pracowników w module Zasoby ludzkie

Informacje listy płac w module Zasoby ludzkie

|                              |                 |
|------------------------------|-----------------|
| **Przyczyna amortyzacji**       | Niskie wykorzystanie       |
| **Zamieniona przez inną funkcję?** | Nie              |
| **Moduły, których dotyczą zmiany**             | Zasoby ludzkie |

### <a name="workplanner"></a>Planowanie pracy

|                              |                                                                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Niskie wykorzystanie                                                                                                                                                            |
| **Zamieniona przez inną funkcję?** | Nie, ale strona **Relacja profilu**, którą można otworzyć ze strony **Grupy profilów**, obsługuje ten sam scenariusz biznesowy, co wycofana strona **Planowanie produkcji**. |
| **Moduły, których dotyczą zmiany**             | Czas i frekwencja                                                                                                                                                  |

### <a name="x-financial-statements"></a>Sprawozdania finansowe X++

|                              |                                                                                             |
|------------------------------|---------------------------------------------------------------------------------------------|
| **Przyczyna amortyzacji**       | Ta funkcja została zastąpiona inną funkcją.                                    |
| **Zamieniona przez inną funkcję?** | Program Management Reporter (oznaczony jako **Raporty finansowe** w bieżącej wersji systemu Dynamics AX) |
| **Moduły, których dotyczą zmiany**             | Księga główna                                                                              |


