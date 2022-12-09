---
title: Problemy z synchronizacją asynchroniczną zamówienia
description: W tym artykule opisano typowe przyczyny niepowodzenia asynchronicznego tworzenia zamówień w Microsoft Dynamics 365 Commerce oraz przedstawiono kroki rozwiązywania problemów, aby pomóc użytkownikom systemu i partnerom zrozumieć, co poszło nie tak.
author: Shajain
ms.date: 11/30/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: 27bccced3c07149fe1842524660447a49f86f3fc
ms.sourcegitcommit: 2804b05214c87f76457608b5db072582ff339852
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/01/2022
ms.locfileid: "9815764"
---
# <a name="asynchronous-order-synchronization-issues"></a>Problemy z synchronizacją asynchroniczną zamówienia

[!include [banner](../../includes/banner.md)]

W tym artykule opisano typowe przyczyny niepowodzenia asynchronicznego tworzenia zamówień w Microsoft Dynamics 365 Commerce oraz przedstawiono kroki rozwiązywania problemów, aby pomóc użytkownikom systemu i partnerom zrozumieć, co poszło nie tak.

## <a name="symptom"></a>Objaw

Zamówienia asynchroniczne tworzone w usługach Dynamics 365 Commerce e-commerce lub punkt sprzedaży (POS) nie są odzwierciedlane w programie Commerce Headquarters.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

Tworzenie zamówienia może się nie powieść w centrali z różnych powodów, w zależności od etapu, na którym proces tworzenia zamówienia kończy się niepowodzeniem. Poniżej przedstawiono przyczyny główne rozwiązywania problemów.

### <a name="validate-that-the-transaction-related-to-the-asynchronous-order-has-reached-headquarters"></a>Sprawdź, czy transakcja związana z zamówieniem asynchronicznym osiągnęła centralę

W przypadku zamówień e-commerce w centrali przejdź do **Sprzedaż detaliczna i handel \> Zapytania i raporty \> Transakcje w sklepie internetowym**. Jeśli dla zamówienia jest dostępny numer potwierdzenia, przefiltruj transakcje, wprowadzając numer potwierdzenia w polu **Identyfikator odwołania kanału** . Jeśli nie masz numeru potwierdzenia, odfiltruj transakcje, wprowadzając numer konta odbiorcy.

W przypadku zamówień w aplikacji POS otwórz stronę **Transakcje sklepu** i odfiltruj rekordy według numeru paragonu lub numeru konta odbiorcy. Jeśli transakcja nie zostanie znaleziona, uruchom zadanie transakcje kanału **P-0001**, które synchronizuje transakcje z kanałów do centrali. Jeśli zadanie **P-0001** nie powiedzie się, otwórz bilet pomocy technicznej dla błędu zadania. Jeśli zadanie **P-0001** się powiedzie, ale transakcje nadal nie będą widoczne w centrali, otwórz bilet pomocy technicznej z odpowiednimi informacjami.
 
### <a name="check-the-synchronization-status-if-the-transaction-is-present-in-headquarters-but-isnt-linked-with-a-sales-order"></a>Sprawdź stan synchronizacji, jeśli transakcja znajduje się w centrali, ale nie jest połączona z zamówieniem sprzedaży

Jeśli transakcja jest obecna w centrali, ale zamówienie sprzedaży nie zostało utworzone, otwórz stronę **Transakcje w sklepie internetowym** i wybierz **Stan synchronizacji** skróconą kartę. Jeśli zadanie **Synchronizuj zamówienia** próbowało zsynchronizować tę transakcję,    w polu **Stan zamówienia** oczekującego powinien być pokazywany stan **Sukces** lub **Niepowodzenie**. Jeśli stan to **Sukces**, pole zamówienia sprzedaży musi być obecne w tej transakcji. Jeśli stan to **Niepowodzenie**, można wyświetlić szczegóły błędu w polu **Szczegóły błędu zamówienia** na skróconej karcie **stan synchronizacji**. Jeśli żaden z tych stanów nie jest wyświetlany, nie są dokonywane żadne próby przetwarzania transakcji. W takim przypadku w górnej części strony można wybrać opcję **Synchronizuj zamówienie**, aby uruchomić zadanie synchronizacji.

Upewnij się, że zadanie **Synchronizowania zamówień** jest zaplanowane do okresowego uruchomienia, dzięki czemu transakcje asynchroniczne mogą być tworzone jako zamówienia w centrali.

Poniższe sekcje zawierają informacje o pewnych typowych błędach i proponowanych poprawkach.

#### <a name="the-order-error-details-field-shows-the-following-error-message-number-sequence-has-been-exceeded"></a>W polu Szczegóły błędu zamówienia wyświetlany jest następujący komunikat o błędzie: „Sekwencja numerów została przekroczona”

Sekwencje numerów są używane do tworzenia zamówień sprzedaży w centrali. Jeśli wszystkie numery dozwolone dla sekwencji numerów są wyczerpane, system wygeneruje ten komunikat o błędzie. Sekwencję numerów używaną do tworzenia zamówień sprzedaży można znaleźć w **Parametry należności \> Sekwencje numerów \> Zamówienie sprzedaży**. Aby rozwiązać ten problem, napraw istniejącą sekwencję numerów lub zastąp ją nową sekwencją numerów.

#### <a name="the-order-error-details-field-shows-the-following-error-message-there-must-be-a-default-payment-service-to-process-credit-card-transactions"></a>W polu Szczegóły błędu zamówienia jest wyświetlany następujący komunikat o błędzie: „Aby przetwarzać transakcje kartą kredytową, musi istnieć domyślna usługa płatnicza”

Aby rozwiązać ten problem, upewnij się, że domyślna płatność jest zdefiniowana w centrali. Jeśli nie zdefiniowano domyślnej płatności, należy jej zdefiniować. Przejdź do **Rozrachunki z odbiorcami \> Konfiguracja płatności \> Usługi płatnicze** i upewnij się, że opcja **Domyślny procesor dla nowych kart kredytowych** jest ustawiona na **Tak** dla jednej usługi płatniczej.
    
#### <a name="the-order-error-details-field-shows-an-account-structure-error-message"></a>W polu Szczegóły błędu zamówienia wyświetlany jest komunikat o błędzie struktury konta

Tekst komunikatu o błędzie struktury konta może być różny, tak jak po poniższych przykładach. Błędy mają jednak wspólne główne przyczyny, które są powiązane z konfiguracją struktury konta.

- „Wyniki księgowania dla arkusza numer partii 0009656328 Kupon ARP-000959899 1,00 dla kuponu ARP-000959899 w firmie usrt zostaną zaksięgowane jako nadpłata lub niedopłata”
- „Wyniki księgowania dla numeru partii dziennika 0009656328 Załącznik ARP-000959899 Załącznik ARP-000959901 Struktura konta dla kombinacji 618160 nie jest ważna dla wspólnego konta głównego firmy księgi”
- „Wyniki księgowania dla dziennika numer partii 0009656328 Voucher ARP-000959899 Voucher ARP-000959901 Zgłoszono z kont firmowych usrt”
- „Wyniki księgowania dla numeru partii czasopisma 0009656328 Voucher ARP-000959899 Księgowanie zostało anulowane”
    
Aby poprawić te błędy, sprawdź poprawność struktur kont. Aby uzyskać więcej informacji, zobacz [Konfigurowanie struktury konta](/dynamics365/finance/general-ledger/configure-account-structures).
    
Po awarii zaznacz transakcję, która się nie powiodła, a następnie w górnej części strony wybierz opcję **Synchronizuj zamówienie**, aby uruchomić zadanie synchronizacji.
    
#### <a name="other-types-of-errors-that-might-require-the-transaction-data-to-be-fixed"></a>Inne typy błędów, które mogą wymagać stałych danych transakcji

Aby poprawić inne typy błędów, które mogą wymagać poprawki danych transakcji, można użyć funkcji „transakcji edycji i inspekcji”. Aby uzyskać więcej informacji, zobacz [Edycja i przeprowadzanie inspekcji transakcji](../edit-order-trans.md).
