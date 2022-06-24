---
title: Omówienie polecenia zapłaty SEPA
description: Ten artykuł zawiera informacje dotyczące jednolitego obszaru płatności w euro (SEPA), który jest ustawiony przez Komisję Europejską.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, CustBankAccounts, CustParameters, CustTable
audience: Application User
ms.reviewer: kfend
ms.custom:
- "11144"
- intro-internal
ms.assetid: 3277c9b6-e46e-40c9-aa76-9b0449467842
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d63cac6c21ec5c5340204f409648516047bb94d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909164"
---
# <a name="sepa-direct-debit-overview"></a>Omówienie polecenia zapłaty SEPA

[!include [banner](../includes/banner.md)]

Jednolity Obszar Płatniczy w Euro (SEPA) został ustanowiony przez Komisję Europejską i decyduje o tym, że wszystkie płatności elektroniczne są uważane za krajowe, niezależnie od kraju/regionu, w którym znajdują się osoby, przedsiębiorstwa, organizacje oraz właściwy bank. Nie istnieje różnica między płatnościami krajowymi i międzynarodowymi. System SEPA obejmuje 28 państw członkowskich Unii Europejskiej (UE) oraz dodatkowo Islandię, Liechtenstein, Norwegię, Szwajcarię, Monako i San Marino. SEPA tworzy jeden rynek dla transakcji płatności w ramach europejskiego obszaru gospodarczego (EOG). Ostatecznie SEPA umożliwia zmniejszenie liczby formatów płatności, którymi operują banki, firmy i osoby prywatne.   

## <a name="what-is-the-goal-of-sepa-direct-debits"></a>Jaki jest cel poleceń zapłaty SEPA?

Polecenie zapłaty SEPA umożliwia wierzycielowi otrzymanie funduszy z konta bankowego odbiorcy, pod warunkiem, że udzielono odpowiedniej zgody podpisanej przez odbiorcę na rzecz wierzyciela. Odbiorca podpisuje zgodę, która autoryzuje wierzyciela do pobrania płatności i powoduje, że bank odbiorcy wypłaca zaległą kwotę. 

Polecenia zapłaty SEPA po raz pierwszy tworzą instrument płatniczy używanych dla krajowych i międzynarodowych poleceń zapłaty w euro, w 32 krajach/regionach SEPA. 

Dostępne są dwa schematy: główny schemat SEPA i schemat biznesowy SEPA. Oba programy wykorzystują ten sam format pliku.

## <a name="what-is-the-core-direct-debit-scheme"></a>Czym jest podstawowy schemat polecenia zapłaty?
Podstawowy schemat polecenia zapłaty to schemat główny. Ma następujące atrybuty:
-   Transfer funduszy jest w euro (nawet jeśli konta bankowe mogą posiadać środki w innych walutach).
-   Odbiorca i dostawca muszą posiadać konto u instytucji kredytowej, która znajduje się na terenie strefy SEPA.
-   Odbiorca musi przekazać podpisaną zgodę dla wierzyciela.
-   Zgoda wygasa po upływie 36 miesięcy od ostatnio zainicjowanego pobrania środków.
-   Wierzyciel musi przechowywać zgody tak długo, jak zgody obowiązują i przez co najmniej 14 miesięcy od ostatniego pobrania środków.
-   System może być używany dla pojedynczego (jednorazowego) lub powtarzający się poleceń zapłaty wierzytelności.
-   Odbiorcy mają prawo do otrzymania zwrotu pieniędzy na maksymalnie osiem tygodni po obciążeniu ich kąta "bez zadawania żadnych pytań".

## <a name="what-is-the-sepa-business-to-business-b2b-direct-debit-scheme"></a>Czym jest schemat firmowy SEPA?
Schemat firmowy SEPA dotyczy transakcji międzyfirmowych i wykorzystuje główny schemat SEPA. Główne różnice są następujące:
-   Jeśli odbiorca to osoba fizyczna (użytkownik), stosowanie schematu biznesowego SEPA B2B jest niedozwolone.
-   Odbiorca nie ma prawa do uzyskania zwrotu autoryzowanych transakcji.
-   Banki odbiorcy muszą upewnić się, że inkaso jest zatwierdzone, poprzez sprawdzając inkaso względem informacji w zgodzie. Banki odbiorcy i odbiorcy muszą wyrazić zgodę na weryfikację, która będzie wykonywana dla każdego polecenia zapłaty.
-   Schemat oferuje krótszą oś czasu przy prezentowaniu poleceń zapłaty i skraca okres zwrotu.

## <a name="can-i-use-the-cor1-scheme-for-direct-debit-mandates"></a>Czy można używać schematu COR1 dla zgód na polecenie zapłaty?
Tak. Można używać schematu COR1 do obsługi zgód na polecenie zapłaty SEPA w Austrii, Belgii, Niemczech, Francji, Włoszech, Hiszpanii i Holandii. Schemat zapewnia krótszy okres przed zgłoszeniem pobrania zapłaty dla dostawcy.

## <a name="what-are-international-bank-account-numbers-iban-and-bank-identifier-codes-bic"></a>Czym są Międzynarodowe numery konta bankowego (IBAN) i kody identyfikacyjne banku (SWIFT)?
Międzynarodowy numer konta bankowego (IBAN) i kod identyfikacyjny banku (SWIFT) są używane do identyfikowania dowolnego konta w 32 krajach/regionach SEPA. Wprowadź kod identyfikacyjny banku (BIC) w polu Kod SWIFT, a numer IBAN w polu IBAN. Oba pola znajdują się na skróconej karcie Dodatkowa identyfikacja na karcie Konto bankowe na stronie Konta bankowe. Dotyczy to zarówno konta bankowego wierzyciela, jak i konta bankowego odbiorcy.

## <a name="where-do-i-enter-creditor-identifiers-direct-debit-ids"></a>Gdzie wprowadzić identyfikatory wierzyciela (identyfikatory poleceń zapłaty)
W SEPA, każdy wierzyciel posiada unikatowy identyfikator. Identyfikator służy do filtrowania każdego polecenia zapłaty przez odbiorcę lub bank odbiorcy, a następnie przetwarzania lub odrzucenia polecenia zapłaty zgodnie z instrukcjami odbiorcy. Wierzyciele musi zażądać wydania tego identyfikatora za pośrednictwem swojego banku. Wpisz ten identyfikator w polu Identyfikator polecenia zapłaty dla konta bankowego firmy.

## <a name="what-are-mandates"></a>Czym są zgody?
Odbiorca podpisuje zgodę, która autoryzuje wierzyciela do pobrania płatności i powoduje, że bank odbiorcy wypłaca zaległą kwotę. Odbiorcy mogą wystawiać zgody, w formie papierowej lub elektronicznej. Domyślnie zgody wygasają po upływie 36 miesięcy od ostatnio zainicjowanego polecenia zapłaty.

## <a name="where-do-i-specify-the-sepa-direct-debit-file-format-iso-20022"></a>Gdzie należy określić format pliku polecenia zapłaty SEPA (ISO 20022)?
Formaty danych SEPA są oparte na normach ISO-20022 dla wiadomości. Aby skonfigurować metodę płatności dla rozrachunków z odbiorcami, trzeba zaznaczyć pole wyboru Ogólne raportowanie elektroniczne i wybrać format Polecenie zapłaty SEPA jako konfigurację formatu eksportu. Ta metoda płatności jest używana podczas generowania pliku płatności w arkuszu płatności odbiorcy.

## <a name="in-what-file-formats-can-i-generate-sepa-direct-debit-payment-files"></a>W jakich formatach plików można generować pliki płatności polecenia zapłaty SEPA?
Można generować pliki płatności elektronicznej dla poleceń zapłaty SEPA w następujących formatach:
-   Pliki płatności poleceniem zapłaty SEPA w formacie pliku PAIN.008.001.02 XML dla Belgii, Niemiec, Hiszpanii, Francji, Włoch i Holandii.
-   Pliki płatności polecenia zapłaty SEPA w formacie pliku PAIN.008.001.02 XML dla Austrii i w formacie pliku PAIN.008.003.02 XML dla Niemiec.

## <a name="how-do-refunds-and-returns-work-with-sepa-direct-debits"></a>Jak wyglądają zwroty dla polecenia zapłaty SEPA?
W ramach obu schematów poleceń zapłaty SEPA, odbiorcy mają określone prawa do refundacji. Odbiorca jest uprawniony do wycofania wszelkich autoryzowanych transakcji w okresie ośmiu tygodni po terminie, bez konieczności podawania przyczyny. W przypadku transakcji nieautoryzowanych, okres ten jest rozszerzony do 13 miesięcy po terminie płatności. Cofnięcia wszelkich płatności, które zostały wykonane, są realizowane ręcznie za pomocą przycisku Anuluj płatność na stronie Transakcje odbiorcy.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
