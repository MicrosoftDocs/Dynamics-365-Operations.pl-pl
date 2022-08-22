---
title: Importowanie plików ISO20022
description: W tym artykule wyjaśniono, jak importować pliki płatności w formatach ISO 20022 camt.054 i pain.002 do aplikacji Microsoft Dynamics 365 Finance.
author: AdamTrukawka
ms.date: 07/27/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Italy, Latvia, Lithuania, Norway, Poland, Spain, Sweden, Switzerland, United Kingdom
ms.author: atrukawk
ms.search.validFrom: 2017-06-01
ms.dyn365.ops.version: July 2017 update
ms.search.form: CustPaymMode, CustBankAccounts, VendPaymMode, VendBankAccounts
ms.openlocfilehash: 3c3dc260d7f2b4d4aee966007941f5c626f0a4c6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273836"
---
# <a name="import-iso20022-files"></a>Importowanie plików ISO20022

[!include [banner](../includes/banner.md)]

Można importować pliki płatności mające następujące formaty:

 - **Zawiadomienie kredytowe ISO20022 camt.054** — importowanie płatności przychodzących z pliku w tym formacie do arkusza płatności odbiorców.
 - **Informacja zwrotna o stanie ISO20022 pain.002** i **zawiadomienie debetowe ISO20022 camt.054** — importowanie plików zwrotnych w tych formatach do arkusza przelewów w module Rozrachunki z dostawcami.

## <a name="prerequisites-for-importing-the-camt054-credit-advice-file"></a>Wymagania wstępne dotyczące importowania pliku zawiadomienia kredytowego camt.054
Należy wykonać poniższe wymagania wstępne, aby importować komunikaty powiadomień bankowych w formacie camt.054.001.002 do arkusza płatności odbiorców.

1. Zaimportuj konfigurację **ISO20022 camt.054** modułu Raportowanie elektroniczne (ER) z usługi Microsoft Dynamics Lifecycle Services (LCS). Następnie na stronie **Metoda płatności odbiorcy** w polu **Konfiguracja formatu importu** zaznacz tę konfigurację. Aby uzyskać więcej informacji, zobacz [Formaty plików metod płatności](emea-select-file-formats-for-the-method-of-payments.md).
2. Na stronie **Wszyscy odbiorcy** wprowadź nazwę i numer organizacji dla każdego odbiorcy.
3. Na stronie **Konto bankowe odbiorcy** skonfiguruj rekord konta bankowego odbiorcy przez wprowadzenie następujących informacji: numer IBAN lub numer konta bankowego oraz kod SWIFT lub kod banku.
4. Na stronie **Konta bankowe** skonfiguruj konta bankowe firmy przez wprowadzenie następujących informacji: numer IBAN lub numer konta bankowego, kod SWIFT lub kod banku, waluta i adres.

   > [!NOTE]
   > Jeśli zamierzasz używać funkcji Zaawansowane uzgadnianie konta bankowego, na skróconej karcie **Uzgodnienie** w opcji **Zaawansowane uzgadnianie konta bankowego** ustaw wartość **Tak**. Jeśli zamierzasz uzgadniać niezaksięgowane importowane płatności, w opcji **Uznaj wyciągi bankowe jako potwierdzenia płatności elektronicznych** ustaw wartość **Tak**.

5. Opcjonalnie: Na stronie **Mapowanie kodu transakcji** skonfiguruj mapowanie między kodami transakcji bankowych w pliku a typami transakcji bankowych.
6. Jeżeli plik zawiera opłaty za transakcje, które chcesz zaksięgować razem z przychodzącą płatnością, otwórz opłatę od płatności na stronie **Opłata od płatności odbiorcy**. Następnie na stronie **Metody płatności** skojarz opłatę od płatności z kontem bankowym w ustawieniach opłat od płatności.
7. Jeśli będą importowane płatności ESR zawierające odniesienia do dokumentów płatności ISR (dotyczy firm w Szwajcarii), należy wykonać następującą konfigurację:

    - W polu **Płatności odbiorcy, długość konta** wprowadź długość kodu odbiorcy, który będzie używany w odniesieniach do dokumentu płatności ISR lub do automatycznej identyfikacji odbiorcy.
    - Upewnij się, że numer odbiorcy i numer faktury (numeracje) zawierają tylko cyfry. Nie może w nich być żadnych innych znaków. Numer faktury nie może zawierać zer na początku.
    - Wprowadź numery ESR i BESR oraz kod banku dla rachunku bankowego firmy. Aby uzyskać więcej informacji, zobacz [Importowanie płatności odbiorcy w formacie ESR](emea-che-esr-customer-payments-import.md), ponieważ są wymagane podobne ustawienia.
    
## <a name="import-the-camt054-credit-advice-file-into-the-customer-payment-journal"></a>Importowanie pliku zawiadomienia kredytowego camt.054 do arkusza płatności odbiorców
1. Na stronie **Wiersze arkusza płatności odbiorców** kliknij kolejno opcje **Funkcje** > **Import płatności**.
2. Wybierz metodę płatności, która ma wymagane ustawienia formatu camt.054 ISO20022.
3. Określ wymagane parametry i ścieżkę pliku, a następnie kliknij przycisk **OK**. Plik zostanie zaimportowany.

## <a name="prerequisites-for-importing-files-in-the-pain002-status-return-and-camt054-debit-advice-formats-into-the-ap-payment-transfer-journal"></a>Warunki wstępne importowania plików informacji zwrotnej o stanie w formacie ISO20022 pain.002 i zawiadomienia debetowego w formacie ISO20022 camt.054 do arkusza przelewów w module Rozrachunki z dostawcami
Należy spełnić poniższe warunki wstępne, aby importować komunikaty bankowe w następujących formatach ISO20022 do strony **Przelew do dostawcy**: komunikaty zwrotne o stanie pain.002.001.003 i zawiadomienia debetowe camt.054.001.002.

1. Zaimportuj konfiguracje ER **ISO20022 camt.054** i **ISO20022 pain.002** z usługi LCS.
2. Na stronie **Metoda płatności dostawcy** w polach **Konfiguracja formatu zwrotnego** i **Pomocnicza konfiguracja formatu zwrotnego** zaznacz zaimportowane konfiguracje modułu ER. Trzeba będzie aktywować standardowy format elektroniczny informacji zwrotnych dla wybranej metody płatności.
3. Na stronie **Mapowanie stanu formatu zwrotnego** skonfiguruj mapowanie kodów stanu między stanami formatu pain.002 a stanami arkusza płatności dostawców.

    Oto przykład konfiguracji stanów.

    Stan zwrotu | Stan płatności
    --------------|---------------
    RJCT          | Odrzucona
    ACCP          | Zaakceptowany
    ACSP          | Odebrane

4. Na stronie **Kody błędów formatu zwrotnego** skonfiguruj kody błędów i opisy formatu pain.002 kody zgodnie z zewnętrznymi kodami przyczyn stanu w standardzie ISO20022.

    Poniżej przedstawiono przykład częściowej konfiguracji kodów błędów.

    Kod | Nazwisko
    -----|-----
    AC01 | IncorrectAccountNumber
    AC02 | InvalidDebtorAccountNumber
    AC03 | InvalidCreditorAccountNumber
    AC04 | ClosedAccountNumber
    AC05 | ClosedDebtorAccountNumber
    AC06 | BlockedAccount

5. Jeżeli plik camt.054 zawiera opłaty za transakcje, które chcesz zaksięgować razem z przychodzącą płatnością, otwórz opłatę od płatności na stronie **Opłata od płatności dostawcy**. Następnie na stronie **Metody płatności** skojarz opłatę od płatności z kontem bankowym w ustawieniach opłat od płatności.

## <a name="import-the-pain002-status-return-or-camt054-debit-advice-files-into-the-vendor-payment-journal"></a>Importowanie plików informacji zwrotnej o stanie pain.002 lub zawiadomienia debetowego camt.054 do arkusza płatności dostawców
1. Otwórz stronę **Przelewy** stronę w menu modułu Rozrachunki z dostawcami.
2. Na stronie **Przelewy** kliknij opcję **Plik zwrotny — Dostawca**.
3. Wybierz metodę płatności, która ma wymagane ustawienia plików formatu ISO20022, i kliknij przycisk **OK**.
4. Zaznacz format pliku, który chcesz zaimportować, a następnie kliknij przycisk **OK**.
5. Określ wymagane parametry i ścieżkę pliku, a następnie kliknij przycisk **OK**.

Jeśli importujesz plik pain.002, stan wierszy płatności do dostawców zostanie zaktualizowany zgodnie z informacjami w importowanym pliku.

W przypadku importowania pliku camt.054 należy określić następujące dodatkowe parametry:

- **Identyfikator opłaty** — wprowadź identyfikator opłaty, który będzie definiował nowe wiersze opłat od płatności tworzone w wierszu arkusza płatności dostawców w przypadku, gdy plik camt.054 zawiera kwotę opłaty.
- **Nazwa nowego arkusza** i **Opis nowego arkusza** — wprowadź nazwę i opis arkusza, do którego będą przenoszone przetworzone transakcje. Po przeniesieniu w nowym arkuszu powinny zostać przypisane nowe numery załączników.
- **Importuj transakcje poleceń zapłaty** — ustaw w tej opcji wartość **Tak**, jeśli wychodzące polecenia zapłaty muszą być importowane do arkusza płatności dostawców.
- **Nazwa arkusza** — podaj nazwę nowego arkusza na importowane transakcje polecenia zapłaty.
- **Rozlicz transakcje** — ustaw w tej opcji wartość **Tak**, jeśli importowane płatności do dostawców muszą być rozliczane względem faktur znajdujących się w systemie.

Zaimportowane informacje można przejrzeć na stronie **Przelewy**. 

## <a name="additional-details"></a>Dodatkowe szczegóły

Podczas importowania konfiguracji formatu z usługi LCS importujesz całe drzewo konfiguracja, a więc również konfiguracje modelu i mapowania modelu. W modelu płatności począwszy od wersji 8 mapowania znajdują się w oddzielnych konfiguracjach raportowania elektronicznego w drzewie rozwiązania (Mapowanie modelu płatności 1611, Mapowanie modelu płatności do lokalizacji docelowej ISO20022 itp.). W jednym modelu (modelu płatności) istnieje wiele różnych formatów płatności, dlatego oddzielna obsługa mapowań jest kluczowa dla łatwego zarządzania rozwiązaniem. Rozważmy na przykład następujący scenariusz: używasz płatności ISO20022 do generowania plików poleceń przelewu, a następnie importujesz komunikaty zwrotne z banku. W tym scenariuszu należy korzystać z następujących konfiguracji:

 - **Model płatności**
 - **Mapowanie modelu płatności 1611** — to mapowanie będzie używane do generowania pliku eksportu
 - **Mapowanie modelu płatności do lokalizacji docelowej ISO20022** — ta konfiguracja zawiera wszystkie mapowania, które będą używane do importowania danych (kierunek mapowania „do lokalizacji docelowej”)
 - **Polecenie przelewu ISO20022** — ta konfiguracja zawiera składnik formatu odpowiedzialny za generowanie pliku eksportu (pain.001) na podstawie konfiguracji Mapowanie modelu płatności 1611, a także format do modelowania składnika mapowania, który będzie używany razem z konfiguracją Mapowanie modelu płatności do lokalizacji docelowej ISO20022 w celu rejestrowania wyeksportowanych płatności w systemie na potrzeby dalszego importu (import w tabeli technicznej CustVendProcessedPayments)
 - **Polecenie przelewu ISO20022 (CE)**, gdzie CE odpowiada rozszerzeniu kraju — format pochodny od formatu Polecenie przelewu ISO20022 z taką samą strukturą i pewnymi różnicami specyficznymi dla krajów
 - **Pain.002** — ten format zostanie użyty wraz z konfiguracją Mapowanie modelu płatności do lokalizacji docelowej ISO20022 w celu zaimportowania pliku pain.002 do arkusza przeniesień płatności dostawców
 - **Camt.054** — ten format zostanie użyty wraz z konfiguracją Mapowanie modelu płatności do lokalizacji docelowej ISO20022 w celu zaimportowania pliku camt.054 do arkusza przeniesień płatności dostawców Ta sama konfiguracja formatu będzie używana w funkcji importowania płatności odbiorców, ale inne mapowanie będzie używane w konfiguracji Mapowanie modelu płatności do lokalizacji docelowej ISO20022.

Aby uzyskać więcej informacji na temat raportowania elektronicznego, zobacz [Omówienie raportowania elektronicznego](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

## <a name="additional-resources"></a>Dodatkowe zasoby
- [Tworzenie i eksport płatności dla dostawcy przy użyciu formatu płatności ISO20022](./tasks/create-export-vendor-payments-iso20022-payment-format.md)
- [Importowanie konfiguracji polecenia przelewu ISO20022](./tasks/import-iso20022-credit-transfer-configuration.md)
- [Importowanie konfiguracji polecenia zapłaty ISO20022](./tasks/import-iso20022-direct-debit-configuration.md)
- [Konfigurowanie kont bankowych firmy dla poleceń przelewu ISO20022](./tasks/set-up-company-bank-accounts-iso20022-credit-transfers.md)
- [Konfigurowanie kont bankowych firmy dla poleceń zapłaty ISO20022](./tasks/set-up-company-bank-accounts-iso20022-direct-debits.md)
- [Konfigurowanie odbiorców i kont bankowych odbiorców dla poleceń zapłaty ISO20022](./tasks/set-up-bank-accounts-iso20022-direct-debits.md)
- [Konfigurowanie metody płatności przelewu ISO20022](./tasks/set-up-method-payment-iso20022-credit-transfer.md)
- [Konfigurowanie metody płatności poleceniem zapłaty ISO20022](./tasks/setup-method-payment-iso20022-direct-debit.md)
- [Konfigurowanie dostawców i kont bankowych dostawców dla poleceń przelewu ISO20022](./tasks/set-up-vendor-iso20022-credit-transfers.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
