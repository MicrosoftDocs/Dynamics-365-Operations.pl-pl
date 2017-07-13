---
title: "Przestarzałe funkcje"
description: "W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia."
author: sericks007
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Platform
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 6
ms.translationtype: Human Translation
ms.sourcegitcommit: 3267bd1cbd738b5ced9996fc3b28eee211627591
ms.openlocfilehash: 8feffb27b5d08a9c90e97ac0d7e00abf0448d0df
ms.contentlocale: pl-pl
ms.lasthandoff: 06/16/2017


---

# Przestarzałe funkcje
<a id="deprecated-features" class="xliff"></a>

[!include[banner](../includes/banner.md)]

W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia.

## Funkcje, które wycofano w programie Dynamics 365 for Finance and Operations Enterprise Edition z aktualizacją z lipca 2017 r.
<a id="features-that-have-been-deprecated-in-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-update" class="xliff"></a>

### Portal urządzeń przenośnych używanych w magazynie
<a id="warehouse-mobile-devices-portal" class="xliff"></a>

Portal urządzeń przenośnych używanych w magazynie (WMDP) był autonomicznym składnikiem przeznaczonym do lokalnego samodzielnego instalowania. Ten składnik nie jest już obsługiwany w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. Funkcjonalność portalu WMDP została zastąpiona macierzystą aplikacją o ulepszonej funkcjonalności. 

|                                  |                                                 |
|----------------------------------|-------------------------------------------------|
| **Przyczyna wycofania**       | Pokrywające się funkcje.                        |
| **Zamieniona przez inną funkcję?** | Tak. Ta funkcja została zastąpiona przez moduł Finance and Operations — Magazynowanie. Aby uzyskać więcej informacji na temat konfiguracji i wymagań wstępnych, zobacz [Instalowanie i konfigurowanie programu Microsoft Dynamics 365 for Finance and Operations — Magazynowanie](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/warehousing/install-configure-warehousing-app). |
| **Moduły, których dotyczą zmiany**             | Zarządzanie magazynem, Zarządzanie transportem |

### Reguła zaawansowanego uzgadniania konta bankowego w ręcznym uzgadnianiu
<a id="advanced-bank-reconciliation-matching-rule-for-manual-matching" class="xliff"></a>

Reguła uzgadniania używana do wybierania i zaznaczania dokumentu bankowego podczas ręcznego uzgadniania dokumentów w arkuszu uzgadniania.

|                                  |                                                                                        |
|----------------------------------|----------------------------------------------------------------------------------------|
| **Przyczyna wycofania**       | Ograniczone użycie.                                                                         |
| **Zamieniona przez inną funkcję?** | Nr Do wyszukiwania dokumentów na potrzeby uzgadniania należy używać funkcji filtrowania kolumn. |
| **Moduły, których dotyczą zmiany**             | Zarządzanie gotówką i bankami                                                               |

### Aplikacja na tablety z systemem Windows 8
<a id="windows-8-tablet-app" class="xliff"></a>

Aplikacja na tablety z systemem Windows 8 zawierała funkcje wprowadzania i zatwierdzania wydatków.

|                                  |                                                                                          |
|----------------------------------|------------------------------------------------------------------------------------------|
| **Przyczyna wycofania**       | Program Finance and Operations jest zgodny z tabletami. Aplikacja na tablety przestała być potrzebna. |
| **Zamieniona przez inną funkcję?** | Nr                                                                                      |
| **Moduły, których dotyczą zmiany**             | Zarządzanie wydatkami                                                                       |


Funkcje, które wycofano w programie Dynamics 365 for Operations 1611 po aktualizacji platformy 3
<a id="features-that-have-been-deprecated-in-dynamics-365-for-operations-1611-with-platform-update-3" class="xliff"></a>
---------------------------------------------------------------------------------------------

### Formaty płatności AEB dla Hiszpanii
<a id="aeb-payment-formats-for-spain" class="xliff"></a>

Formaty płatności Consejo Superior Bancario służą do wysyłania plików przekazów do banku dla płatności odbiorcy i dostawcy. Zawartość tych formatów jest określana przez Asociación Española de Banca. Obejmuje ona Cuaderno 19, 32, 58, 34.

|                              |                                                                          |
|------------------------------|--------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Te formaty płatności nie są już używane.                                  |
| Zamieniona przez inną funkcję? | Tak, przez formaty płatności poleceniem przelewu i poleceniem zapłaty ISO20022 dla Hiszpanii |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami, Rozrachunki z odbiorcami                                    |

### Przelewy płatnościami bankowymi dla Litwy
<a id="bank-payments-transfer-for-lithuania" class="xliff"></a>

Przelewy płatnościami bankowymi na Litwie są generowane i drukowane przy użyciu formatu eksportu przelewów (LT). Na litewskim rynku w 2005 r. zaczęto używać ujednoliconego systemu bankowości elektronicznej LITAS.

|                              |                                                            |
|------------------------------|------------------------------------------------------------|
| Przyczyna amortyzacji       | Te formaty płatności nie są już używane.                    |
| Zamieniona przez inną funkcję? | Tak, przez format płatności poleceniem przelewu ISO20022 dla Litwy |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami                                           |

### Formaty płatności BBS Direkte Remittering dla Norwegii
<a id="bbs-direkte-remittering-payment-formats-for-norway" class="xliff"></a>

Formaty płatności BBS Direkte Remittering zawierają funkcje eksportu inkasa płatności od odbiorcy (polecenie zapłaty) i importu komunikatu zwrotnego.

|                              |                                                                                                                                                                |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Te formaty płatności nie są już używane.                                                                                                                        |
| Zamieniona przez inną funkcję? | Format płatności od odbiorcy AvtaleGiro dla Norwegii może służyć do generowania komunikatów polecenia zapłaty. Import komunikatów zwrotnych zostanie zaimplementowany w przyszłych wersjach. |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami, Rozrachunki z odbiorcami                                                                                                                          |

### Narzędzie planu kont dla Hiszpanii
<a id="chart-of-accounts-tool-for-spain" class="xliff"></a>

To narzędzie jest używane, gdy plan kont w Hiszpanii wymaga dużych zmian. Użytkownicy mogą zaimportować nowy plan kont w formacie programu Microsoft Excel lub tekstowym, a także zaimportować sprawozdania finansowe.

|                              |                |
|------------------------------|----------------|
| Przyczyna amortyzacji       | Ograniczone użycie  |
| Zamieniona przez inną funkcję? | Nr             |
| Moduły, których dotyczą zmiany             | Księga główna |

### Format płatności Dom80 dla Belgii
<a id="dom80-payment-format-for-belgium" class="xliff"></a>

Starszy belgijski format płatności dla inkasa płatności (polecenie zapłaty).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Przyczyna amortyzacji       | Ten format płatności nie jest już używany.                  |
| Zamieniona przez inną funkcję? | Tak, przez format płatności poleceniem zapłaty ISO 20022 dla Belgii |
| Moduły, których dotyczą zmiany             | Rozrachunki z odbiorcami                                    |

### Formaty płatności DTA/EZAG dla Szwajcarii
<a id="dtaezag-payment-formats-for-switzerland" class="xliff"></a>

Formaty DTA/EZAG są zintegrowane w systemie ESR, ponieważ mogą być nośnikami numeru odwołania. Numery odwołania nie są obowiązkowe i dlatego te formaty mogą służyć do przetwarzania wszelkich płatności dla dostawców. Te formaty są używane przez firmy, które mają konta bankowe w lokalizacji innej niż „Postfinance”.

|                              |                                                              |
|------------------------------|--------------------------------------------------------------|
| Przyczyna amortyzacji       | Te formaty płatności nie są już używane.                      |
| Zamieniona przez inną funkcję? | Tak, przez format płatności poleceniem przelewu ISO20022 dla Szwajcarii |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami                                             |

### Format płatności EDIFACT-DIRDEB dla Austrii
<a id="edifact-dirdeb-payment-format-for-austria" class="xliff"></a>

Format płatności EDIFACT-DIRDEB dla inkasa płatności (polecenie zapłaty).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Przyczyna amortyzacji       | Ten format płatności nie jest już używany.                  |
| Zamieniona przez inną funkcję? | Tak, przez format płatności poleceniem zapłaty ISO 20022 dla Austrii |
| Moduły, których dotyczą zmiany             | Rozrachunki z odbiorcami                                    |

### EDIVAT dla Belgii
<a id="edivat-for-belgium" class="xliff"></a>

EDIVAT to starszy belgijski standard wysyłania deklaracji elektronicznych za pośrednictwem bezpiecznej poczty. System Microsoft Dynamics AX 2012 zachowuje rozwiązanie tylko do odczytu, aby umożliwić dostęp do danych historycznych.

|                              |                                      |
|------------------------------|--------------------------------------|
| Przyczyna amortyzacji       | Ta funkcjonalność nie jest już używana. |
| Zamieniona przez inną funkcję? | Nr                                   |
| Moduły, których dotyczą zmiany             | Księga główna                       |

### Format importu płatności eGiro EDIFACT CREMUL dla Norwegii
<a id="egiro-edifact-cremul-payment-import-format-for-norway" class="xliff"></a>

eGiro opiera się na międzynarodowym standardzie ONZ EDIFACT CREMUL (Multiple Credit Advice Message), który jest używany do automatycznego księgowania płatności od odbiorców. W systemie Microsoft Dynamics AX funkcjonalność eGiro jest zaimplementowana jako format importu płatności od odbiorców.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Ten format płatności nie jest już używany.                                                     |
| Zamieniona przez inną funkcję? | Nr Ten format zostanie zastąpiony formatami importu wyciągów ISO 20022 w przyszłych wersjach. |
| Moduły, których dotyczą zmiany             | Rozrachunki z odbiorcami                                                                       |

### Zapasy zewnętrzne dla Polski
<a id="external-inventory-for-poland" class="xliff"></a>

Dowód przyjęcia towarów, które otrzymano od dostawcy do sprzedaży bez zakupu. Towary, które są obsługiwane w zewnętrznych zapasach, nie mają wpływu na zapasy standardowe i mogą być sprzedawane, a następnie automatycznie kupowane. Ten proces tworzy faktyczne przesunięcia magazynowe.

|                              |                                                 |
|------------------------------|-------------------------------------------------|
| Przyczyna amortyzacji       | Zamieniona przez inną funkcję                     |
| Zamieniona przez inną funkcję? | Tak, przez podstawową funkcjonalność konsygnacji przychodzącej |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami, Zarządzanie zapasami          |

### Generator raportów finansowych dla Europy Wschodniej
<a id="financial-reports-generator-for-eastern-europe" class="xliff"></a>

Narzędzie służące do konfigurowania zbierania danych na potrzeby raportów księgowych i podatkowych oraz eksportowania danych do szablonów raportów XLS i DOC.

|                              |                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Ograniczone użycie                                                                            |
| Zamieniona przez inną funkcję? | Nr Narzędzie zostanie zastąpione konfiguracjami raportowania elektronicznego w przyszłych wersjach. |
| Moduły, których dotyczą zmiany             | Księga główna                                                                           |

### Import transakcji płatności od odbiorców dla Finlandii
<a id="import-of-customer-payment-transactions-for-finland" class="xliff"></a>

Można wybrać formatu importu dla płatności fińskich, który importuje transakcje płatności od odbiorców z zewnętrznego pliku dostarczonego przez bank.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Ten format płatności nie jest już używany.                                                     |
| Zamieniona przez inną funkcję? | Nr Ten format zostanie zastąpiony formatami importu wyciągów ISO 20022 w przyszłych wersjach. |
| Moduły, których dotyczą zmiany             | Rozrachunki z odbiorcami                                                                       |

### Import transakcji płatności do arkusza księgi głównej dla Finlandii
<a id="import-of-payment-transactions-into-a-general-ledger-journal-for-finland" class="xliff"></a>

Format specyficzny dla Finlandii służy do importowania transakcji księgowych do księgi głównej.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Ten format płatności nie jest już używany.                                                     |
| Zamieniona przez inną funkcję? | Nr Ten format zostanie zastąpiony formatami importu wyciągów ISO 20022 w przyszłych wersjach. |
| Moduły, których dotyczą zmiany             | Rozrachunki z odbiorcami                                                                       |

### Integracja z systemem Isabel zsynchronizowana (CIS) dla Belgii
<a id="integration-with-isabel-synchronized-cis-for-belgium" class="xliff"></a>

Isabel jest systemem szkieletowym bankowości elektronicznej w Europie i de facto normą w Belgii.

|                              |                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Integracja z klientami systemu Isabel została wycofana.                                                                |
| Zamieniona przez inną funkcję? | Nr Nieużywane formaty płatności zostały zastąpione formatem płatności poleceniem przelewu ISO20022 dla Belgii. |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami                                                                                                     |

### Zmiany w planie kont i regułach księgowania dla Hiszpanii
<a id="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain" class="xliff"></a>

Ta funkcja jest stosowana dla zmian w planie kont i regułach księgowania w Hiszpanii. Mapuje konta, ułatwiając przekształcanie starych planów kont na nowe plany kont oraz porównuje poprzedni rok obrachunkowy z nowym rokiem obrachunkowym, nawet jeśli zostały one zaksięgowane pod różnymi numerami kont.

|                              |                |
|------------------------------|----------------|
| Przyczyna amortyzacji       | Ograniczone użycie  |
| Zamieniona przez inną funkcję? | Nr             |
| Moduły, których dotyczą zmiany             | Księga główna |

### Format płatności od dostawców Pagamento Fornittori
<a id="pagamento-fornittori-vendor-payment-format" class="xliff"></a>

Starszy włoski format płatności dla poleceń przelewu.

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Przyczyna amortyzacji       | Ten format płatności nie jest już używany.                  |
| Zamieniona przez inną funkcję? | Tak, przez format płatności poleceniem przelewu ISO20022 dla Włoch |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami                                       |

### Formaty eksportu płatności dla Estonii
<a id="payment-export-formats-for-estonia" class="xliff"></a>

Formaty Telehansa i Teleservice są używane do eksportu płatności bankowych.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Przyczyna amortyzacji       | Te formaty płatności nie są już używane.                  |
| Zamieniona przez inną funkcję? | Tak, przez format płatności poleceniem przelewu ISO20022 dla Estonii |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami                                         |

### Archiwum plików płatności dla Norwegii
<a id="payment-file-archive-for-norway" class="xliff"></a>

Podczas generowania plików płatności są one automatycznie umieszczane w archiwum. Dotyczy to nawet plików, które zostały wcześniej zapisane lub odczytane.

|                              |                                                                    |
|------------------------------|--------------------------------------------------------------------|
| Przyczyna amortyzacji       | Zamieniona przez inną funkcję                                        |
| Zamieniona przez inną funkcję? | Tak, przez zarchiwizowane zadania raportowania elektronicznego                            |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami, Rozrachunki z odbiorcami, Administrowanie organizacją |

### Formaty importu płatności dla Estonii
<a id="payment-import-formats-for-estonia" class="xliff"></a>

Formaty Telehansa i TeleTeenus są używane do importu płatności bankowych.

|                              |                                                                                            |
|------------------------------|--------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Te formaty płatności nie są już używane.                                                    |
| Zamieniona przez inną funkcję? | Nr Te formaty zostaną zastąpione formatami importu wyciągów ISO 20022 w przyszłych wersjach. |
| Moduły, których dotyczą zmiany             | Rozrachunki z odbiorcami                                                                        |

### Przepływ pracy celu zarządzania wydajnością
<a id="performance-management-goal-workflow" class="xliff"></a>

Zarządzanie wydajnością obejmuje zarządzanie celami oraz integrację z przeglądami wydajności.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Moduł zarządzania wydajnością został przeprojektowany. Zmniejszono liczbę stron dotyczących celów, aby uprościć proces.                 |
| Zamieniona przez inną funkcję? | Nr Cele są wyświetlane menedżerom w samoobsługowym portalu dla menedżerów i mogą być zmieniane oraz wyświetlane przez menedżerów. |
| Moduły, których dotyczą zmiany             | Zarządzanie kapitałem ludzkim                                                                                                 |

### Formaty płatności Postgirot i Postgirot Utland dla Szwecji
<a id="postgirot-and-postgirot-utland-payment-formats-for-sweden" class="xliff"></a>

Formaty płatności Postgirot i Postgirot Utland dla Szwecji.

|                              |                                                         |
|------------------------------|---------------------------------------------------------|
| Przyczyna amortyzacji       | Te formaty płatności nie są już używane.                 |
| Zamieniona przez inną funkcję? | Tak, przez format płatności poleceniem przelewu ISO20022 dla Szwecji |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami                                        |

### Identyfikacja radiowa (RFID)
<a id="radio-frequency-identifier" class="xliff"></a>

Identyfikacja radiowa (RFID) to technologia zbierania danych przy użyciu elektronicznych znaczników do przechowywania danych identyfikacyjnych bez konieczności bezpośredniego dostępu do czytnika w celu odczytania danych identyfikacyjnych.

|                              |                                               |
|------------------------------|-----------------------------------------------|
| Przyczyna amortyzacji       | Brak wykorzystywania przez odbiorców i ograniczony zestaw funkcji. |
| Zamieniona przez inną funkcję? | Nr                                            |
| Moduły, których dotyczą zmiany             | Zarządzanie zapasami                          |

### Raport o urzędowej numeracji faktur dla Łotwy
<a id="report-about-state-invoices-numbering-for-latvia" class="xliff"></a>

Łotewskie prawo zawiera określone reguły numerowania faktur sprzedaży. Funkcja pozwala przypisywać konkretne numery do faktur sprzedaży na podstawie użytkownika lub grupy użytkowników. Następnie można wygenerować raport lub plik XML. Można również wydrukować raport o użytych numerach faktur.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Urzędowa numeracja faktur nie musi już być stosowana. Raport o użytych numerach faktur nie jest już wymagany. |
| Zamieniona przez inną funkcję? | Nr                                                                                                                       |
| Moduły, których dotyczą zmiany             | Rozrachunki z odbiorcami                                                                                                      |

### Ustawianie imion i nazwisk menedżera i głównego księgowego firmy dla Litwy
<a id="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania" class="xliff"></a>

Imiona i nazwiska menedżera oraz głównego księgowego firmy można podać w danych firmy i następnie używać w różnych raportach drukowanych lokalnie.

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| Przyczyna amortyzacji       | Zamieniona przez inną funkcję                                     |
| Zamieniona przez inną funkcję? | Tak, w tym samym celu można używać konfiguracji urzędników.   |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami, Rozrachunki z odbiorcami, Zaawansowane uzgadnianie konta bankowego |

### Formaty płatności TelePay dla Norwegii
<a id="telepay-payment-formats-for-norway" class="xliff"></a>

Formaty płatności TelePay obejmują funkcje eksportu płatności dla dostawców (polecenie przelewu) i inkasa płatności od odbiorców (polecenie zapłaty).

|                              |                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Te formaty płatności nie są już używane.                                                        |
| Zamieniona przez inną funkcję? | Tak, przez format płatności poleceniem przelewu ISO20022 i format płatności od odbiorcy AvtaleGiro dla Norwegii |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami, Rozrachunki z odbiorcami                                                          |

### Formaty eksportu płatności dla dostawców dla Finlandii
<a id="vendor-payment-export-formats-for-finland" class="xliff"></a>

Dwa formaty eksportowania płatności są dostępne dla Finlandii. LM02 (FI) jest używany w przypadku krajowych płatności, a LUM2 (FI) jest używany w przypadku płatności zagranicznych.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Przyczyna amortyzacji       | Te formaty płatności nie są już używane.                  |
| Zamieniona przez inną funkcję? | Tak, przez format płatności poleceniem przelewu ISO20022 dla Finlandii |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami                                         |

### Przepływ pracy tworzenia celów
<a id="workflow-for-creating-goals" class="xliff"></a>

Przepływ pracy zarządzania tworzeniem celów dla pracowników jest jednym z kilku przepływów pracy, które były dostępne jako pomoc w koordynowaniu procesu zarządzania wydajnością.

|                              |                                                                                                                                                                                                                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Zarządzanie wydajnością zostało całkowicie przeprojektowane w programie Microsoft Dynamics 365 for Finance and Operations.                                                                                                                                                                                                                                        |
| Zamieniona przez inną funkcję? | Przeprojektowana funkcjonalność zarządzania wydajnością zapewnia większą kontrolę nad treścią celów, miarami służącymi do śledzenia postępów oraz dołączaniem towarzyszącej dokumentacji. Cele można zapisywać jako szablony i ponownie wykorzystywać. Ta funkcja może pomóc szybciej konfigurować dodatkowe cele dla pracowników. |
| Moduły, których dotyczą zmiany             | Zarządzanie kapitałem ludzkim                                                                                                                                                                                                                                                                                                               |

## Funkcje wycofane w wydaniach systemu Dynamics AX 7.0
<a id="features-deprecated-in-dynamics-ax-70-releases" class="xliff"></a>
### Możliwość anulowania zmian na fakturze od dostawcy
<a id="ability-to-cancel-changes-to-a-vendor-invoice" class="xliff"></a>

|                              |                         |
|------------------------------|-------------------------|
| Przyczyna amortyzacji       | Chęć poprawy wydajności. |
| Zamieniona przez inną funkcję? | Nie                      |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami        |

### Integracja z AIF, AxD i AxBC
<a id="aif-axd-and-axbc-integrations" class="xliff"></a>

W narzędziach integracji aplikacji (AIF) może dochodzić do wymiany danych z zewnętrznymi systemami poprzez logikę biznesową powiązaną z usługami. System Dynamics AX zawiera usługi, które są oparte na dokumentach i programie .NET Business Connector (AxBC). Dokument jest tworzony przy użyciu języka XML. Kod XML zawiera informacje nagłówka dodawane w celu tworzenia *komunikatów*, które mogą być przesyłane do systemu Dynamics AX lub z niego wysyłane. Przykłady dokumentów obejmują zamówienia sprzedaży i zamówienia zakupu. Jednak niemal wszystkie podmioty, np. odbiorca, mogą być reprezentowane przez dokument. Usługi oparte na dokumentach używają klas **Axd &lt;*dokument*&gt;**.

|                              |                                                                                                                                                                                                          |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Nie dało się przeskalować architektury narzędzi AIF i AxD na potrzeby usługi chmurowej. Wystąpiły problemy z wydajnością wokół importu zbiorczego.                                                                               |
| Zamieniona przez inną funkcję? | W bieżącej wersji systemu Dynamics AX ta funkcja jest zastąpiona strukturą importu/eksportu danych, która obsługuje cykliczny import/eksport zbiorczy. Dla klasy AxBC zaleca się użycie samych tabel. |
| Moduły, których dotyczą zmiany             | AxD, AxBC i AIF                                                                                                                                                                                     |

### BOM bez wersji BOM
<a id="boms-without-bom-versions" class="xliff"></a>

Po wyłączeniu klucza konfiguracji **Wersje BOM** wersje list składowych (BOM) były ukrywane we wszystkich formularzach, a system wymuszał relację 1:1 między zwolnionymi produktami i listami BOM. W bieżącej wersji systemu Dynamics AX klucza konfiguracji **Wersje BOM** nie da się wyłączyć.

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Obsługa klucza konfiguracji do kontrolowania wersji BOM nie jest dopasowana do skali środowiska chmurowego. |
| Zamieniona przez inną funkcję? | Nie                                                                                      |
| Moduły, których dotyczą zmiany             | Zarządzanie informacjami o produktach, Zarządzanie zapasami                                    |

### Brazylijski format Bordero
<a id="brazilian-bordero" class="xliff"></a>

Specjalna metoda płatności dla firm brazylijskich

|                              |                                                                                                       |
|------------------------------|-------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Obsługa brazylijskiej metody płatności Bordero została wycofana dla lokalizacji w Brazylii |
| Zamieniona przez inną funkcję? | Nr                                                                                                    |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami                                                                                      |

### Brazylijska deklaracja Sintegra
<a id="brazilian-sintegra-statement" class="xliff"></a>

Krajowa deklaracja podatku ICMS

|                              |                                                                                                                       |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Ta deklaracja nie ma już zastosowania w niektórych stanach Brazylii.                                                     |
| Zamieniona przez inną funkcję? | Nr Użytkownicy mogą użyć narzędzia Ogólne raportowanie elektroniczne do skonfigurowania deklaracji, jeśli jest to wymagane w określonych sytuacjach. |
| Moduły, których dotyczą zmiany             | Księgi podatkowe                                                                                                          |

### Brazylijski tryb sytuacji awaryjnych SCAN dla NF-e
<a id="brazilian-scan-contingency-mode-for-nf-e" class="xliff"></a>

Środowisko awaryjne (SCAN) jest używane do generowania, eksportowania i importowania stanu z portalu Nota Fiscal eletrônica (NF-e), gdy środowisko Secretaria da Fazenda (SEFAZ) jest niedostępne.

|                              |                                                                             |
|------------------------------|-----------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Ta metoda pracy awaryjnej nie jest już stosowana w niektórych stanach w Brazylii |
| Zamieniona przez inną funkcję? | Nr                                                                          |
| Moduły, których dotyczą zmiany             | Rozrachunki z odbiorcami                                                         |

### Aplikacja Business Analyzer
<a id="business-analyzer" class="xliff"></a>

Ta aplikacja mobilna pozwala użytkownikom przeglądać kluczowe pomiary biznesowe.

|                              |                                                                                                                                                               |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Ta funkcja została zastąpiona inną funkcją.                                                                                                      |
| Zamieniona przez inną funkcję? | Pakiet materiałów do monitorowania wyników finansowych dla usługi Microsoft Power BI będzie zawierał najważniejsze mierniki finansowe, które wcześniej były dostępne w aplikacji Business Analyzer. |
| Moduły, których dotyczą zmiany             | Księga główna                                                                                                                                                |

### Statystyki
<a id="business-statistics" class="xliff"></a>

Konfiguracja zapytań o statystyki biznesowe, które mogą ułatwić analizowanie funkcjonowania organizacji.

|                              |                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Istniejące podejście do analizy biznesowej (BI), niskie wykorzystanie przez odbiorców i ograniczony zestaw funkcji. |
| Zamieniona przez inną funkcję? | Nowe rozwiązanie BI dla aktualnej wersji systemu Dynamics AX.                                      |
| Moduły, których dotyczą zmiany             | Zaopatrzenie i sourcing, Rozrachunki z dostawcami, Sprzedaż i marketing, Rozrachunki z odbiorcami         |

### Funkcja zmiany daty dokumentu w Arkuszu zatwierdzania faktur
<a id="change-document-date-function-in-invoice-approval-journal" class="xliff"></a>

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Niskie wykorzystanie                                                               |
| Zamieniona przez inną funkcję? | Tak. Można zmienić datę dokumentu dla zaksięgowanej transakcji dostawcy. |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami                                                        |

### Format płatności ClieOp03 dla Holandii
<a id="clieop03-payment-format-for-the-netherlands" class="xliff"></a>

|                              |                                                                                                            |
|------------------------------|------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Ten format nie jest już używany w Holandii, ponieważ został zastąpiony przez funkcję SEPA. |
| Zamieniona przez inną funkcję? | Eksport płatności SEPA                                                                                       |
| Moduły, których dotyczą zmiany             | Wszyscy                                                                                                        |

### Centrum zgodności
<a id="compliance-center" class="xliff"></a>

Centrum zgodności było witryną Enterprise Portal do zarządzania wymaganiami dokumentacji dla inicjatyw zgodności związanych z ustawą Sarbanes-Oxley.

|                              |                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Brak wykorzystywania przez odbiorców. Program Microsoft SharePoint oferuje te same funkcje, które były dostępne w Centrum zgodności. |
| Zamieniona przez inną funkcję? | Nie                                                                                                                     |
| Moduły, których dotyczą zmiany             | Zgodność z przepisami i kontrole wewnętrzne                                                                                       |

### Connector for Microsoft Dynamics
<a id="connector-for-microsoft-dynamics" class="xliff"></a>

To narzędzie zostało użyte do integracji najważniejszych danych z programu Microsoft Dynamics CRM do aplikacji systemu Microsoft Dynamics ERP.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Przyczyna amortyzacji       | Ta funkcja została zastąpiona inną funkcją. |
| Zamieniona przez inną funkcję? | Integrator systemu Dynamics                                      |
| Moduły, których dotyczą zmiany             | Connector for Microsoft Dynamics                         |

### Jednostka kontenera i wielowymiarowe zapasy na stanie
<a id="container-unit-and-multi-dimension-on-hand" class="xliff"></a>

|                              |                                                                                                                                                                 |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Pokrywające się funkcje                                                                                                                                         |
| Zamieniona przez inną funkcję? | Tak. Od wersji AX 2012 ta funkcja jest zastąpiona zestawem funkcji skonsolidowanych szarż produkcyjnych. Zestaw zawiera skonsolidowany widok dostępnych zapasów. |
| Moduły, których dotyczą zmiany             | Zarządzanie informacjami o produktach, Kontrola produkcji, Zarządzanie zapasami, Sprzedaż i marketing                                                                   |

### Metadane grupy wskaźników
<a id="cue-group-metadata" class="xliff"></a>

|                              |                                                                                                                                                                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Grupy wskaźników były używane do wyświetlania jednego lub kilku wskaźników w obszarze pola informacji. Liczba pobrań była ograniczona i występowały też problemy z wydajnością, ponieważ zmiana rekordu w formularzu nadrzędnym powodowała tworzenie jednej kwerendy na wskaźnik w grupie wskaźników. |
| Zamieniona przez inną funkcję? | Nie                                                                                                                                                                                                                            |
| Moduły, których dotyczą zmiany             | Wszyscy                                                                                                                                                                                                                           |

### Metadane wskaźnika
<a id="cue-metadata" class="xliff"></a>

|                              |                                                                                                                                                                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Metadane wskaźnika były ograniczone do liczby lub sumy.                                                                                                                                                                                   |
| Zamieniona przez inną funkcję? | Wprowadzono metadane kafelka, by poprawić elastyczność modelowania. Można na przykład modelować aktualne liczby, nawigację i kluczowe wskaźniki wydajności (KPI). Metadane wskaźnika zostały bezpośrednio zastąpione przez metadane kafelka z liczbami. |
| Moduły, których dotyczą zmiany             | Wszyscy                                                                                                                                                                                                                                     |

### Duński format czeku
<a id="danish-check-format" class="xliff"></a>

|                              |                                                                                                                         |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Obsługa duńskiego układu formatu czeku została wycofana i raport został usunięty z lokalizacji DK. |
| Zamieniona przez inną funkcję? | Nie                                                                                                                      |
| Moduły, których dotyczą zmiany             | Wszyscy                                                                                                                     |

### Partycje danych
<a id="data-partitions" class="xliff"></a>

Partycje danych zapewniają logiczne oddzielenie danych w bazie danych systemu Microsoft Dynamics AX.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Partycje danych zostały wprowadzone w systemie Microsoft Dynamics AX 2012 R2, aby umożliwić izolowanie danych. W typowym scenariuszu firma ma oddziały. Dane z jednego oddziału firmy nie powinny być widoczne w innym oddziale, mimo że oba oddziały są zarządzane przez ten sam dział IT. Jednak były wymagane dodatkowe skrypty i towarzyszące zarządzanie programem w celu utworzenia nowych partycji i wypełnienia ich danymi oraz utworzenia kopii zapasowych danych partycji. W chmurze, gdzie mamy dostęp do usług bazy danych (baza danych SQL Microsoft Azure) w postaci platformy jako usługi (PaaS), znacznie bardziej efektywne jest używanie bazy danych jako kontenera izolacji niż konfigurowanie izolacji w programie. Niezależnie od tego, czy partycjonowanie danych jest wymagane dla oddziałów, wielu dzierżawców czy tylko ze względu na skalę, jesteśmy przekonani, że wszystkie scenariusze można lepiej obsługiwać za pomocą wielu baz danych lub wielu wystąpień systemu Dynamics AX. |
| Zamieniona przez inną funkcję? | W przyszłym wydaniu partycje danych zostaną zastąpione przez obsługę wielu baz danych lub wystąpień systemu Dynamics AX.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Moduły, których dotyczą zmiany             | Wszyscy                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

### Ogranicznik
<a id="delimitation" class="xliff"></a>

|                              |                                        |
|------------------------------|----------------------------------------|
| Przyczyna amortyzacji       | Nie stwierdzono używania funkcji. |
| Zamieniona przez inną funkcję? | Nie                                     |
| Moduły, których dotyczą zmiany             | Czas i frekwencja                    |

### Klient komputerowy
<a id="desktop-client" class="xliff"></a>

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Środowisko klienta systemu Dynamics AX zostało przeprojektowane, by poprawić funkcjonalność wielu platform i urządzeń.                      |
| Zamieniona przez inną funkcję? | Nowy klient sieci web jest oparty na metadanych formatu dla komputerów i modelu programowania, który został dostosowany do potrzeb rozszerzonej platformy internetowej. |
| Moduły, których dotyczą zmiany             | Wszystko                                                                                                                                    |

### Bezpośrednie połączenie z bazą danych
<a id="direct-database-connection" class="xliff"></a>

W programie Dynamics AX 2012 R3 aplikacja Retail Modern POS mogła się łączyć bezpośrednio z bazą danych kanału w podobny sposób, jak robi to aplikacja Enterprise POS. Było to uzupełnienie standardowej metody komunikacji używanej przez aplikację Retail Modern POS, czyli korzystania z pośrednictwa serwera sieci sprzedaży.  

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Bezpośrednia łączność z bazą danych wymagała protokołów o słabszych zabezpieczeniach i była używana głównie do osiągnięcia najwyższej wydajności. Ze względu na ulepszenia w dziedzinach wydajności i zabezpieczeń, które wprowadzono przy okazji programu Dynamics 365 for Finance and Operations, ta funkcjonalność wywołuje teraz więcej problemów, niż rozwiązuje. |
| Zamieniona przez inną funkcję? | Nr Teraz jest obsługiwana tylko standardowa komunikacja za pośrednictwem serwera sieci sprzedaży.    |
| Moduły, których dotyczą zmiany             | Baza danych kanału/Retail Modern POS                                    |

### Holenderski SWIFT MT940
<a id="dutch-swift-mt940" class="xliff"></a>

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | W miejsce funkcji zlokalizowanej używana jest teraz funkcja ogólna.                                                                                                                                                                 |
| Zamieniona przez inną funkcję? | Tak, ta funkcja została zastąpiona funkcją zaawansowanego uzgadniania kont bankowych. Oprócz tego w następnej aktualizacji systemu Dynamics AX jest planowana implementacja funkcji importu wyciągów z kont camt.053 ISO20022 dla arkusza finansowego. |
| Moduły, których dotyczą zmiany             | Wszyscy                                                                                                                                                                                                                                   |

### eBilanz (XBRL dla Niemiec)
<a id="ebilanz-xbrl-for-germany" class="xliff"></a>

Ta funkcja generowała dane wyjściowe w formacie eXtensible Business Reporting Language (XBRL) dostosowane specjalnie do niemieckiej taksonomii eBilanz.

|                              |                                                                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Brak wykorzystywania przez odbiorców.                                                                                                                                                 |
| Zamieniona przez inną funkcję? | Ta funkcja nie została zastąpiona przez inną funkcję, ale dla rynku niemieckiego jest dostępnych wiele wyspecjalizowanych pakietów XBRL oferujących rozbudowane funkcje XBRL. |
| Moduły, których dotyczą zmiany             | Program Management Reporter                                                                                                                                                    |

### Klient witryny Enterprise Portal
<a id="enterprise-portal-client" class="xliff"></a>

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Udostępnione jedną platformę kliencką.                                                                                            |
| Zamieniona przez inną funkcję? | Nowy klient sieci web jest oparty na metadanych formatu dla komputerów i modelu programowania, który został dostosowany do potrzeb rozszerzonej platformy internetowej. |
| Moduły, których dotyczą zmiany             | Wszyscy                                                                                                                                    |

### Równowaga środowiskowa
<a id="environmental-sustainability" class="xliff"></a>

|                              |                                                    |
|------------------------------|----------------------------------------------------|
| Przyczyna amortyzacji       | Brak wykorzystywania przez odbiorców i ograniczony zestaw funkcji.       |
| Zamieniona przez inną funkcję? | Nie                                                 |
| Moduły, których dotyczą zmiany             | Zgodność z przepisami i kontrole wewnętrzne, Rozrachunki z dostawcami |

### Formanty ActiveX i Zarządzany host
<a id="form-activex-and-managed-host-controls" class="xliff"></a>

|                              |                                                                                                                                                                                               |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Formanty ActiveX i Zarządzany host są oparte na kliencie dla komputerów, który został wycofany.                                                                                                             |
| Zamieniona przez inną funkcję? | Rozszerzana struktura formantów pozwala tworzyć nowe formanty oparte na HTML, CSS i JavaScript i jest formantem pierwszej klasy w środowisku narzędziowym Microsoft Visual Studio. |
| Moduły, których dotyczą zmiany             | Wszyscy                                                                                                                                                                                           |

### Generowanie przelewów testowych przy użyciu zadania wsadowego
<a id="generate-prenotes-by-using-a-batch" class="xliff"></a>

Przelewu testowego nie da się wygenerować za pomocą zadania wsadowego, ale może to zrobić użytkownik.

|                              |                                                                                                        |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Nie istnieje żaden formularz do utrwalania i wyświetlania powstałego pliku przelewu testowego po jego wygenerowaniu przy użyciu zadania wsadowego. |
| Zamieniona przez inną funkcję? | Przelewy testowe nadal można wygenerować, a użytkownik ma kontrolę nad miejscem zapisu pliku.   |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami, Rozrachunki z odbiorcami, Zaawansowane uzgadnianie konta bankowego                                        |

### Niemiecki eksport płatności i import wyciągu z konta DTAUS (sumy i transakcje)
<a id="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions" class="xliff"></a>

|                              |                                                                                                                                                                                                                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Ten format nie jest już używany w Niemczech, ponieważ został zastąpiony przez funkcję Jednolity Obszar Płatniczy w Euro (SEPA).                                                                                                                                                                 |
| Zamieniona przez inną funkcję? | Tak, ta funkcja została zastąpiona funkcjami eksportu płatności SEPA i zaawansowanego uzgadniania kont bankowych w imporcie wyciągów z kont. Oprócz tego w następnej aktualizacji systemu Dynamics AX jest planowana implementacja funkcji importu wyciągów z kont camt.053 ISO20022 dla arkusza finansowego. |
| Moduły, których dotyczą zmiany             | Wszyscy                                                                                                                                                                                                                                                                                            |

### Niemiecki format płatności DTAZV
<a id="german-dtazv-payment-format" class="xliff"></a>

|                              |                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Ten format nie jest już używany w Niemczech, ponieważ został zastąpiony przez funkcję SEPA. |
| Zamieniona przez inną funkcję? | Eksport płatności SEPA                                                                               |
| Moduły, których dotyczą zmiany             | Wszyscy                                                                                                |

### Niemiecki import MT940
<a id="german-mt940-import" class="xliff"></a>

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | W miejsce funkcji zlokalizowanej używana jest teraz funkcja ogólna.                                                                                                                                                                 |
| Zamieniona przez inną funkcję? | Tak, ta funkcja została zastąpiona funkcją zaawansowanego uzgadniania kont bankowych. Oprócz tego w następnej aktualizacji systemu Dynamics AX jest planowana implementacja funkcji importu wyciągów z kont camt.053 ISO20022 dla arkusza finansowego. |
| Moduły, których dotyczą zmiany             | Wszyscy                                                                                                                                                                                                                                   |

### Niemiecka lista sprzedaży do UE w formacie XML
<a id="german-xml-eu-sales-list" class="xliff"></a>

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Format XML na potrzeby raportowania niemieckiej listy sprzedaży do UE nie jest już obsługiwany. W celu przesyłania raportu list sprzedaży do UE do niemieckiego urzędu skarbowego można używać tylko plików tekstowych w formacie ELMA5. |
| Zamieniona przez inną funkcję? | Nie                                                                                                                                                                                 |
| Moduły, których dotyczą zmiany             | Podatek                                                                                                                                                                                |

### Raporty GL SSRS
<a id="gl-ssrs-reports" class="xliff"></a>

Usunięto raporty zawierające następujące elementy menu: **Sumaryczny bilans próbny**, **Szczegółowy bilans próbny**, **Plan kont**, **Dziennik inspekcji**, **Salda** i **Lista sald**.

|                              |                                                                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Raporty finansowe Microsoft SQL Server Reporting Services (SSRS) zostały zastąpione funkcjami programu Management Reporter i domyślnymi raportami. |
| Zamieniona przez inną funkcję? | Program Management Reporter (oznaczony jako **Raporty finansowe** w bieżącej wersji systemu Dynamics AX)                                                  |
| Moduły, których dotyczą zmiany             | Księga główna                                                                                                                               |

### Metadane InfoPart i FormPart
<a id="infopart-and-formpart-metadata" class="xliff"></a>

|                              |                                                                                                                                                                                                                                |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Włączona obsługa metadanych InfoPart i FormPart do tworzenia pól informacyjnych dla dwóch różnych klientów.                                                                                                                                    |
| Zamieniona przez inną funkcję? | Metadane InfoPart, które były uproszczoną definicję formularza, są konwertowane na formularz przez narzędzia uaktualniania. Metadane FormPart odwołujące się do formularza są zastępowane przez bardziej bezpośrednie odwołanie tworzone przez narzędzia uaktualniania. |
| Moduły, których dotyczą zmiany             | Wszyscy                                                                                                                                                                                                                            |

### Strona listy konta głównego
<a id="main-account-list-page" class="xliff"></a>

Lista kont dla podmiotu prawnego i powiązane informacje o saldzie

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Informacje o saldzie są dostępne na stronie listy **Bilans próbnego** według konta i wymiaru.                                                                                      |
| Zamieniona przez inną funkcję? | Strona **Konta główne** zawiera tę samą listę kont, która jest dostępna na stronie listy **Konto główne**. Widok siatki na stronie **Konta główne** również pokazuje nawet mniejszy widok przypominający siatkę. |
| Moduły, których dotyczą zmiany             | Księga główna                                                                                                                                                                     |

### Raport dotyczący bankowych przepływów pieniężnych w Malezji i Singapurze
<a id="malaysia-and-singapore-bank-cash-flow-report" class="xliff"></a>

Ta funkcja umożliwia drukowanie raportu przepływów pieniężnych, który przedstawia transakcje oraz szczegóły przychodów i rozchodów gotówkowych w określonym zakresie dat dla wybranych kont bankowych.

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Te same informacje można uzyskać z transakcji bankowej Informacje. |
| Zamieniona przez inną funkcję? | Transakcja bankowa Informacje.                                            |
| Moduły, których dotyczą zmiany             | Zarządzanie gotówką i bankami                                                |

### Meksykański faktura elektroniczna CFD
<a id="mexican-cfd-electronic-invoice" class="xliff"></a>

Ta funkcja służyła do generowania meksykańskich faktur elektronicznych za pomocą metody Comprobante Fiscal Digital (CFD), gdzie firma podpisuje fakturę, żądając powiązanej autoryzacji od rządu. Ta funkcja obejmuje też miesięczne raporty zawierające wszystkie faktury elektroniczne, które zostały wystawione w danym okresie.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                           |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Metoda nie jest już stosowana. Metoda generowania faktur elektronicznych za pomocą metody CFD została wycofana przez urzędy skarbowe i zastąpiona metodą Comprobante Fiscal Digital a través de Internet (CFDI) , w której podpis składa zewnętrzny dostawca (PAC). Miesięczny raport został usunięty, a opcja Informacje pozwala użytkownikom wysyłać zapytania o transakcje historyczne. |
| Zamieniona przez inną funkcję? | Nie                                                                                                                                                                                                                                                                                                                                                                                                        |
| Moduły, których dotyczą zmiany             | Rozrachunki z odbiorcami, Projekt                                                                                                                                                                                                                                                                                                                                                                              |

### Zrealizowany i niezrealizowany podatek VAT w Meksyku
<a id="mexico-realized-and-unrealized-vat" class="xliff"></a>

Zarządzanie podatkiem od towarów i usług (VAT) w systemie Microsoft Dynamics AX 2012 odbywało się przy użyciu właściwej dla Meksyku funkcji dla „podatku niezrealizowanego”.

|                              |                                                                                                                     |
|------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Pokrywające się funkcje                                                                                             |
| Zamieniona przez inną funkcję? | Tak, ta funkcja została zastąpiona standardową funkcją podatku warunkowego dostępną w module podstawowym. |
| Moduły, których dotyczą zmiany             | Podatek                                                                                                                 |

### Integracja z programem Microsoft Outlook
<a id="microsoft-outlook-integration" class="xliff"></a>

|                              |                                                                                |
|------------------------------|--------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Ta funkcja została zastąpiona integracją z serwerem programu Microsoft Exchange. |
| Zamieniona przez inną funkcję? | Tak                                                                            |
| Moduły, których dotyczą zmiany             | Sprzedaż i marketing                                                            |

### Informacje listy płac w module Zasoby ludzkie
<a id="payroll-information-in-human-resources" class="xliff"></a>

Informacje listy płac w module Zasoby ludzkie

|                              |                                                                                                                                                                                                                                                                                                                              |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Ta funkcja została zastąpiona stronami podstawowych modułów Lista płac i Zasoby ludzkie.                                                                                                                                                                                                                                              |
| Zamieniona przez inną funkcję? | **Świadczenia**, **Zarobki** i inne pokrewne strony, które były poprzednio używane w module US Payroll, otrzymały nową konfigurację i są teraz częścią konfiguracji podstawowych modułów Zasoby ludzkie, aby ułatwić zewnętrzne przetwarzanie listy płac. Ta funkcja jest dostępna za pomocą klucza konfiguracji **Zasoby ludzkie 1** &gt; **Lista płac**. |
| Moduły, których dotyczą zmiany             | Zasoby ludzkie, Lista płac                                                                                                                                                                                                                                                                                                     |

### Prywatne blokowanie arkuszy zarządzania zapasami i magazynem
<a id="private-blocking-of-inventory-and-warehouse-management-journals" class="xliff"></a>

Nie da się już oznaczyć arkusza zapasów i lub arkusza magazynu jako prywatnego. Możliwe jest jedynie blokowanie arkuszy jako prywatnych dla grup użytkowników oraz blokowanie podczas edycji.

|                              |                                        |
|------------------------------|----------------------------------------|
| Przyczyna amortyzacji       | Nie stwierdzono używania funkcji. |
| Zamieniona przez inną funkcję? | Nie                                     |
| Moduły, których dotyczą zmiany             | Zarządzanie zapasami                   |

### Konstruktor produktów
<a id="product-builder" class="xliff"></a>

Konstruktor produktów był używany do dynamicznego konfigurowania elementów z zamówienia sprzedaży, zamówienia zakupu, zlecenia produkcyjnego, wyceny, oferty w ramach projektu lub zapotrzebowania na towary. Na podstawie modelu produktu, który miał zmienne modelowania użytkownik mógł wybrać wartości w celu spełnienia wymagań odbiorcy i uzyskać unikatowy wariant produktu, który miał BOM i marszrutę.

|                              |                                                                                                                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Konstruktor produktów pokazywał kod X ++ użytkownikom końcowym, a w aktualnej wersji systemu Dynamics AX nie powinno do tego dochodzić. Funkcja została usunięta, by uniknąć duplikowania się działań na zachodzących na siebie, dużych podstawach kodu. |
| Zamieniona przez inną funkcję? | Konfiguracja produktu                                                                                                                                                                                   |
| Moduły, których dotyczą zmiany             | Zarządzanie informacjami o produktach, Sprzedaż i marketing                                                                                                                                                     |

### Zmiana nazwy wymiaru produktu
<a id="rename-product-dimension" class="xliff"></a>

Ta funkcja pozwala zmienić nazwę jednego z trzech standardowych wymiarów produktów (rozmiar, kolor lub styl) na taką, która lepiej pasuje do wymagań firmy. Można było zmieniać wszystkie etykiety, dla których użyto nazwy wymiaru produktu.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Bieżąca wersja systemu Dynamics AX nie obsługuje zmian etykiet w czasie wykonywania. |
| Zamieniona przez inną funkcję? | Nr                                                                            |
| Moduły, których dotyczą zmiany             | Zarządzanie informacjami o produktach                                                |

### Łączność serwera sieci sprzedaży przy użyciu protokołu HTTP
<a id="retail-server-connectivity-using-http" class="xliff"></a>

W programie Dynamics AX 2012 R3 serwer sieci sprzedaży mógł wykorzystywać komunikację za pośrednictwem protokołu HTTP (niezabezpieczonego). Było to uzupełnienie standardowej komunikacji wykorzystującej protokół HTTPS.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Ze względu na nowe wymagania w kwestii bezpieczeństwa obecnie jest obsługiwana tylko zabezpieczona komunikacja przy użyciu protokołu TLS 1.2 (lub nowszego, jeśli jest dostępny). Samoobsługowy instalator automatycznie skonfiguruje komputer do obsługi tej komunikacji. |
| Zamieniona przez inną funkcję? | Nr Teraz jest obsługiwana tylko standardowa komunikacja za pośrednictwem protokołu HTTPS.                                                                           |
| Moduły, których dotyczą zmiany             | Serwer sprzedaży detalicznej                                                |

### Strony widoków głównych użytkownika
<a id="role-center-pages" class="xliff"></a>

|                              |                                                                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Strony widoków głównych użytkownika zostały zbudowane na platformie przestarzałego modułu Enterprise Portal, który został zastąpiony przez platformę nowego klienta sieci web w bieżącej wersji systemu Dynamics AX. |
| Zamieniona przez inną funkcję? | Nowy wzór formularza obszaru roboczego oferuje użytkownikom architekturę ukierunkowaną na proces z łatwym dostępem do często używanych zadań w ramach procesu.                       |
| Moduły, których dotyczą zmiany             | Wszyscy                                                                                                                                                                      |

### Właściwe miejscowo urzędy skarbowe
<a id="sales-tax-jurisdictions" class="xliff"></a>

|                              |                                              |
|------------------------------|----------------------------------------------|
| Przyczyna amortyzacji       | Brak wykorzystywania przez odbiorców i ograniczony zestaw funkcji. |
| Zamieniona przez inną funkcję? | Nie                                           |
| Moduły, których dotyczą zmiany             | Podatki (od sprzedaży) na rynek amerykański                                 |

### Interfejs firmy przewozowej
<a id="shipping-carrier-interface" class="xliff"></a>

|                              |                                                                                                                                                 |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Pokrywające się funkcje                                                                                                                         |
| Zamieniona przez inną funkcję? | Tak, ta funkcja została częściowo zastąpiona funkcjami modułu Zarządzanie transportem, ale nie jest jeszcze zastąpiona w podstawowym module Zarządzanie magazynem (WMS I). |
| Moduły, których dotyczą zmiany             | Sprzedaż i marketing, Zarządzanie magazynem                                                                                                       |

### Sites Services
<a id="sites-services" class="xliff"></a>

Usługi Sites Services pozwalają tworzyć witryny internetowe, które poszerzają zasięg procesów biznesowych o Internet bez wsparcia działu informatycznego.

|                              |                                                                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Infrastruktura Microsoft Azure używana w systemie Dynamics AX zawiera nowe funkcje, które z powodzeniem zastępują wycofane (np. witryny Azure). |
| Zamieniona przez inną funkcję? | Nie                                                                                                                                       |
| Moduły, których dotyczą zmiany             | Rekrutacja kadr, zarządzanie sprawami, zapytania ofertowe, rejestracji dostawców                                                                  |

### Funkcjonalność strategii prognozowania popytu na platformie SSAS
<a id="ssas-demand-forecasting-strategy" class="xliff"></a>

|                              |                                                                              |
|------------------------------|------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Konstrukcja funkcji nie jest obsługiwana w nowej architekturze chmury. |
| Zamieniona przez inną funkcję? | Funkcja strategii prognozowania popytu wykorzystująca usługę Uczenie maszynowe Azure                           |
| Moduły, których dotyczą zmiany             | Planowanie                                                                     |

### Wnioski wyjazdowe
<a id="travel-requisitions" class="xliff"></a>

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| Przyczyna amortyzacji       | Niskie wykorzystanie i większość funkcji była dostępna w witrynie Enterprise Portal. |
| Zamieniona przez inną funkcję? | Nie                                                              |
| Moduły, których dotyczą zmiany             | Zarządzanie wydatkami                                              |

### Szczegóły puli faktur od dostawcy bez księgowania
<a id="vendor-invoice-pool-excluding-posting-details" class="xliff"></a>

|                              |                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Niskie wykorzystanie. Ta funkcja została zastąpiona arkuszem faktur, który ma funkcje przepływu pracy. |
| Zamieniona przez inną funkcję? | Funkcje przepływu pracy w arkuszu faktur.                                                           |
| Moduły, których dotyczą zmiany             | Rozrachunki z dostawcami                                                                                        |

### Firmy wirtualne
<a id="virtual-company-accounts" class="xliff"></a>

Funkcja firm wirtualnych nie jest już obsługiwana w systemie Dynamics AX. Funkcja firm wirtualnych pozwalała użytkownikom na konfigurowanie tabel wspólnych dla zbioru firm. Opis tej funkcji można znaleźć w temacie [Firmy oraz firmy wirtualne](https://msdn.microsoft.com/en-us/library/aa834382(v=ax.10).aspx). Funkcja działa poprzez grupowanie tabel w zbiory przypisane do wirtualnych firm będących grupami istniejących „rzeczywistych” firm. Tworzone są zapytania, tak aby wszystkie firmy w firmie wirtualnej miały dostęp do danych w tabelach skojarzonych zbiorów tabel.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Przyczyna amortyzacji</td>
<td><ul>
<li>Firmy wirtualne należy skonfigurować przed zapisaniem danych w tabelach. Dostosowywanie firm wirtualnych do istniejącego wdrożenia jest bardzo trudne.</li>
<li>Ponieważ w bieżącej wersji systemu Microsoft Dynamics AX dokonano rozległej normalizacji danych, bardzo trudne stało się ustalanie danych, które należało dodać do zbiorów tabel. Na przykład trudno stwierdzić, które tabele należy udostępnić. Wszystkie tabele z odwołaniami z tabel, które były w firmie wirtualnej, też muszą być dodane. Z powodu normalizacji tabel nawet proste dane główne rozłożone między wiele tabel muszą być częścią firmy wirtualnej. Wszelkie popełnione tutaj błędy wywołają problemy funkcjonalne.</li>
<li>Jeśli tabela jest częścią firmy wirtualnej, traci informacje o źródle danych i rejestrowane są tylko dane firmy wirtualnej.</li>
</ul></td>
</tr>
<tr class="even">
<td>Zamieniona przez inną funkcję?</td>
<td>Tabele globalne mogą służyć do udostępniania tabel ze wszystkich firm. Obecnie nie ma funkcji zastępczej.</td>
</tr>
<tr class="odd">
<td>Moduły, których dotyczą zmiany</td>
<td>Nie dotyczy</td>
</tr>
</tbody>
</table>

### Zarządzanie magazynem II
<a id="warehouse-management-ii" class="xliff"></a>

|                              |                                                                                                                                                                                                                                                                                                             |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Rozwiązanie WMS II (Zarządzania magazynem II), które było dostępne w module **Zarządzanie zapasami**, dubluje funkcje dostępne w module **Zarządzanie magazynem**, który został udostępniony w systemie Microsoft Dynamics AX 2012 R3.                                                                         |
| Zamieniona przez inną funkcję? | Moduł **Zarządzanie magazynem**, który został udostępniony w wersjach systemu AX 2012 R3, Microsoft Dynamics AX 2012 R3 CU8 i Microsoft Dynamics AX 2012 R3 CU9, zastępuje funkcje modułu WMS II. Nowy moduł ma bardziej zaawansowane funkcje i elastyczniejsze procesy zarządzania magazynem niż oferowane w module Zarządzanie magazynem II. |
| Moduły, których dotyczą zmiany             | Zarządzanie zapasami, sprzedaż i marketing, zaopatrzenie i sourcing                                                                                                                                                                                                                                         |

### Przypomnienia dla pracowników w module Zasoby ludzkie
<a id="worker-reminders-in-human-resources" class="xliff"></a>

Informacje listy płac w module Zasoby ludzkie

|                              |                 |
|------------------------------|-----------------|
| Przyczyna amortyzacji       | Niskie wykorzystanie       |
| Zamieniona przez inną funkcję? | Nie              |
| Moduły, których dotyczą zmiany             | Zasoby ludzkie |

### Planowanie pracy
<a id="workplanner" class="xliff"></a>

|                              |                                                                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Niskie wykorzystanie                                                                                                                                                            |
| Zamieniona przez inną funkcję? | Nie, ale strona **Relacja profilu**, którą można otworzyć ze strony **Grupy profilów**, obsługuje ten sam scenariusz biznesowy, co wycofana strona **Planowanie produkcji**. |
| Moduły, których dotyczą zmiany             | Czas i frekwencja                                                                                                                                                  |

### Sprawozdania finansowe X++
<a id="x-financial-statements" class="xliff"></a>

|                              |                                                                                             |
|------------------------------|---------------------------------------------------------------------------------------------|
| Przyczyna amortyzacji       | Ta funkcja została zastąpiona inną funkcją.                                    |
| Zamieniona przez inną funkcję? | Program Management Reporter (oznaczony jako **Raporty finansowe** w bieżącej wersji systemu Dynamics AX) |
| Moduły, których dotyczą zmiany             | Księga główna                                                                              |


