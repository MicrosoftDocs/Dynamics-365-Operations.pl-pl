---
title: Szczegóły określonych scenariuszy biznesowych w raporcie JPK-V7M
description: Ten temat wyjaśnia szczegóły konkretnych scenariuszy biznesowych w raporcie JPK-V7M w Polsce.
author: liza-golub
ms.date: 07/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Poland
ms.author: elgolu
ms.openlocfilehash: 7bd0cbe9ef85eda33eee7589f86b5d855429e8bda52e7edabc0f2bd31bc51261
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757954"
---
# <a name="details-of-specific-business-scenarios-in-the-jpk-v7m-report"></a>Szczegóły określonych scenariuszy biznesowych w raporcie JPK-V7M

[!include [banner](../includes/banner.md)]

Ten temat wyjaśnia szczegóły konkretnych scenariuszy biznesowych w raporcie JPK-V7M w Polsce.

## <a name="reporting-of-overdue-customer-invoices"></a>Raportowanie zaległych faktur dla odbiorcy

Raport JPK-V7M w Microsoft Dynamics 365 Finance obsługuje raportowanie zaległych faktur odbiorcy, gdy używana jest funkcja lokalnego [podatku VAT od zaległych należności](emea-pol-sales-tax-reports.md#allowance-for-bad-debts) polskich.

### <a name="business-requirement"></a>Wymagania biznesowe

- Jeśli procedura jest stosowana przez firmę, element **\<P_68\>** części deklaracji musi wykazywać kwotę podstawy opodatkowania dla zaległych faktur w okresie sprawozdawczym (czyli transakcji, które są zaksięgowane do odliczenia podatku od towarów i usług (VAT) za wystawione faktury, które nie zostały opłacone w ciągu 150 dni od terminu płatności).
- Jeśli procedura jest stosowana przez firmę, element **\<P_69\>** części deklaracji musi raportować wysokość VAT dla zaległych faktur w okresie raportu (czyli transakcje, które zostały zaksięgowane w celu odliczenia podatku VAT z tytułu wystawionych faktur, które nie zostały zapłacone w ciągu 150 dni od terminu płatności).
- Jeśli procedura jest stosowana przez firmę, ta transakcja musi być raportowana dla zaległych faktur w okresie, w którym minęło 150 dni od terminu płatności. Należy wpisać informacje o odbiorcy z oryginalnej faktury oraz kwotę, która ma znak minus (–).
- Jeśli procedura jest stosowana przez firmę, ta transakcja musi być raportowana dla zapłaconych zaległych faktur w okresie, gdy zaległa faktura została zapłacona. Należy wpisać wszystkie informacje o odbiorcy z oryginalnej faktury oraz kwotę, która ma znak plus (+).
- Jeżeli procedura jest stosowana przez firmę, a transakcje przeterminowane i przeterminowane opłacone znajdują się w tym samym okresie sprawozdawczym, można opcjonalnie zaraportować obie transakcje razem w ewidencji sprzedaży. W tym przypadku nie są raportowane elementy **\<P_68\>** i **\<P_69\>** części deklaracji.

### <a name="supported-business-user-scenario-in-finance"></a>Obsługiwany scenariusz użytkownika biznesowego w module Finance

Jeśli istnieje zaległa faktura dla odbiorcy, faktura, która jest wystawiana odbiorcy, może przejść trzy etapy:

1. Faktura jest wystawiana odbiorcy, księgowane są transakcje podatkowe, a faktura jest uwzględniana w **JPK** > **Ewidencja** > **SprzedazWiersz** jak zwykle, zgodnie z konfiguracją podatku i konfiguracją markerów.
2. Jeśli faktura nie zostanie zapłacona w ciągu 150 dni od terminu płatności, firma może zastosować zadanie okresowe [Zaległa kwota podatku VAT](emea-pol-sales-tax-reports.md#allowance-for-bad-debts) stanowiąca zadłużenie, przechodząc do **Rozrachunki z odbiorcami** > **Zadania okresowe** > **Zaległa kwota podatku VAT**. Transakcje podatkowe generowane przez to zadanie są odzwierciedlane w raporcie JPK-V7M. Zawarte są następujące informacje:

    - Uwzględnione są wszystkie informacje o odbiorcy z oryginalnej faktury zaksięgowanej w etapie 1.
    - Kwoty są raportowane w tych samych elementach **K_\***, co w oryginalnej fakturze, ale ze znakiem ujemnym.
    - Stosowane są te same markery, które zastosowano w oryginalnej fakturze.
    - Jest stosowany marker **\<KorektaPodstawyOpodt\>**.

    Ponadto kwota podstawy i kwota podatku z tej faktury (dokument wewnętrzny) są uwzględniane i zgłaszane w elementach **P_68** i **P_69** części deklaracji raportu.

3. Jeśli faktura zostanie zaksięgowana po wystąpieniu obu etapów 1 i 2, firma musi ponownie zastosować zadanie okresowe **Zaległa kwota podatku VAT stanowiąca zadłużenie** w okresie, w którym faktura została zapłacona. Wynikowe transakcje podatkowe są odzwierciedlane w raporcie JPK-V7M. Zawarte są następujące informacje:

    - Uwzględnione są wszystkie informacje o odbiorcy z oryginalnej faktury zaksięgowanej w etapie 1.
    - Kwoty są raportowane w tych samych elementach **K_\***, co w oryginalnej fakturze, ale ze znakiem dodatnim.
    - Stosowane są te same markery, które zastosowano w oryginalnej fakturze.
    - Jest stosowany marker **\<KorektaPodstawyOpodt\>**.

    Kwota podstawy i kwota podatku z tej faktury (dokument wewnętrzny) **nie** są uwzględniane i zgłaszane w elementach **P_68** i **P_69** części deklaracji raportu.

> [!IMPORTANT]
> Jeśli etapy 2 i 3 występują w tym samym okresie raportu, elementy **P_68** i **P_69** części deklaracji raportu nie podlegają zmianie.

## <a name="report-ro-and-fp-document-types-for-retail-operations"></a>Raportowanie typów dokumentów RO i FP dla operacji handlu detalicznego

Raport JPK-V7M w finansach obsługuje raportowanie typu **ZWROT** (wewnętrzny dokument podsumowania) (tag **\<TypDokumentu\>** pod tagiem **\<SprzedazWiersz\>**) dla operacji detalicznych, gdy jest używana funkcja [Dodatkowe faktury do sprzedaży detalicznej dla Polski](emea-pol-vdek.md).

### <a name="business-requirements"></a>Wymagania biznesowe

Poniższe zasady raportowania faktur sprzedaży dla operacji handlu detalicznego są oparte na wyjaśnieniach opublikowanych w sekcji Pytania i odpowiedzi oficjalnego portalu podatkowego polskiego Ministerstwa Finansów:

- Wszystkie paragony fiskalne, które są drukowane i wydawane odbiorcom, muszą być zagregowane i zgłoszone jako dokumenty typu **RO** (faktura zbiorcza). Sprzedaż niekrajowym odbiorcom musi być wykluczona z agregacji i zgłaszana jako zwykłe faktury (bez markera typu dokumentu). Należy wykonać agregację dla okresu raportu. Dokumenty sprzedaży raportowane jako dokumenty typu **RO** (faktura zbiorcza) nie podlegają markerom **GTU**. Sprzedaż krajowa, która jest agregowana na potrzeby raportowania jako dokumenty podlegające opodatkowaniu typu **RO** musi być także raportowana jako osobne dokumenty podlegające opodatkowaniu typu **FP**, jeśli odbiorca zażąda faktury za tę sprzedaż. Faktury oznaczone jako dokumenty typu **FP** muszą być wykluczane z sum w **SprzedazCtrl** i wszystkich powiązanych wartościach **P_\**_ części deklaracji. Dokumenty sprzedaży, które są raportowane jako dokumenty typu _* FP** podlegają markerom **GTU**.

### <a name="initial-assumptions-for-the-reporting-of-fiscal-documents-in-a-jpk-v7m"></a>Wstępne założenia dotyczące zgłaszania dokumentów fiskalnych w JPK-V7M

- Wszystkie dokumenty pochodzące z kasy fiskalnej (POS) są opodatkowane.
- Informacje o paragonach fiskalnych przetwarzanych w kasie fiskalnej są poprawnie odzwierciedlone w następujących tabelach bazy danych systemu:

    - RetailTransactionTable
    - RetailTransactionSalesTrans
    - RetailTransactionTaxTrans

- Jeśli odbiorca podał numer VAT do paragonu fiskalnego w kasie fiskalnej, jest on przechowywany w tabeli RetailTransactionFiscalCustomer.SerializedData.
- Wszystkie paragony fiskalne i wstępnie zagregowane dokumenty fiskalne zaksięgowane za pośrednictwem zestawienia sprzedaży detalicznej, które muszą zostać zagregowane na potrzeby raportowania, są księgowane ze stanem **Dokument fiskalny** lub **Dokument fiskalny przekonwertowany na fakturę** w arkuszu faktur dla odbiorcy.
- Jeśli faktura została utworzona w kasie fiskalnej, jest ona poprawnie odzwierciedlona w tabeli RetailTransactionSupplementaryInvoice.
- Jeśli paragon fiskalny został przekonwertowany z dokumentu fiskalnego na fakturę, ma stan faktury **Dokument fiskalny przekonwertowany na fakturę** w arkuszu faktur dla odbiorcy. (Założenie to dotyczy tylko dokumentów fiskalnych, które nie są wstępnie zagregowane).
- Tylko zaksięgowane transakcje detaliczne typu **Sprzedaż** są traktowane jako faktury sprzedaży detalicznej do celów raportowania jako dokumenty typu **FP**.
- Specyficzne scenariusze, takie jak scenariusz „karty upominkowej”, są obecnie poza zakresem.

### <a name="supported-business-user-scenario-in-finance"></a>Obsługiwany scenariusz użytkownika biznesowego w module Finance

Aby raportować typy dokumentów typu **RO** i **FP** za operacje handlu detalicznego, należy skorzystać z następujących parametrów w grupie parametrów **Oznaczenie sprzedaży właściwe dla sprzedaży detalicznej** klasy wykonywalnej **Wygenerowanie JPK_V7M** (**EMGenerateJPKVDEKReportController_PL**) (**Podatek** \> **Ustawienia** \> **Obsługa wiadomości elektronicznych** \> **Ustawienia klasy wykonywalnej**):

- Pole wyboru **Zagregowane dokumenty fiskalne** uaktywnia rekordy **Kryteria zbierania faktur dla odbiorcy na potrzeby agregacji (RO — faktury zbiorcze)**, które są uwzględniane w zbieraniu i agregowaniu paragonów fiskalnych, które muszą być raportowane jako dokumenty typu **RO**.
- Pole wyboru **Zgłoś faktury z kasy fiskalnej** gromadzi faktury sprzedaży detalicznej, które mają datę faktury w okresie raportu i zgłasza je jako dokumenty typu **FP**.
- Pole wyboru **Zgłoś dokument fiskalny przekonwertowany na fakturę** zbiera faktury z tabeli CustInvoiceJour, które mają stan **Dokument fiskalny przekonwerterowany na fakturę** i **FiscalDocDate_PL** w okresie raportu oraz zgłasza je jako dokumenty typu **FP**.

#### <a name="aggregate-fiscal-documents-parameter"></a>Parametr zagregowanych dokumentów fiskalnych

Domyślnie pole wyboru **Zagregowane dokumenty fiskalne** nie jest zaznaczone. W takim przypadku system nie agreguje żadnych dokumentów. Dokumenty są raportowane jako standardowe dokumenty, w których nie jest stosowany żaden typ dokumentu. W związku z tym raport działa tak, jak działał przed tą zmianą.

Jeśli zaznaczono pole wyboru **Zagregowane dokumenty fiskalne**, faktury krajowe mające stan **Dokument fiskalny** lub **Dokument fiskalny przekonwertowany na fakturę** oraz wartość **Data ewidencji VAT**, która przypada w okresie raportu, są raportowane jako jeden zagregowany dokument typu **RO** za okres raportu. Użytkownik definiuje specyficzne dla firmy kryteria krajowych dokumentów fiskalnych, które muszą być zagregowane przy użyciu rekordów **Kryteria zbierania faktur dla odbiorcy na potrzeby agregacji (RO — faktury zbiorcze)**.

Jeśli raport zawiera zagregowany dokument typu **RO**, ma on następujące pola nagłówka.

| Tag raportowania      | Wartość                                 |
|--------------------|---------------------------------------|
| KodKrajuNadaniaTIN | PL                                    |
| NrKontrahenta      | BRAK                                  |
| NazwaKontrahenta   | Sprzedaz paragonowa                   |
| DowodSprzedazy     | ROyyyyMMdd                            |
| DataWystawienia    | Ostatnia data okresu raportu. |
| DataSprzedazy      | Ostatnia data okresu raportu. |
| TypDokumentu       | RO                                    |

#### <a name="report-retail-pos-invoices-parameter"></a>Parametry raportowania faktur z kasy fiskalnej

Domyślnie pole wyboru **Raportuj faktury z kasy fiskalnej** jest wyczyszczone. Po wybraniu tej opcji system gromadzi faktury sprzedaży detalicznej spełniające następujące kryteria:

- W tabeli RetailTransactionSupplementaryInvoice musi znajdować się faktura sprzedaży detalicznej dla transakcji handlu detalicznego w tabeli RetailTransactionTable.
- Wartość **RetailTransactionTable.Type** musi być równa wartości **RetailTransactionType::Sales**.
- Wartość **RetailTransactionTable.entryStatus** musi być równa **RetailEntryStatus::Posted**, a pole **RetailTransactionTable.StatementId** nie może być puste.
- Data faktury (**RetailTransactionSupplementaryInvoice.InvoiceDate**) przypada w okresie raportu.

Pola faktur z kasy fiskalnej z poniższej tabeli muszą być wypełnione.

| Tag raportowania      | Wartość                                                                                                               |
|--------------------|---------------------------------------------------------------------------------------------------------------------|
| KodKrajuNadaniaTIN | PL                                                                                                                  |
| NrKontrahenta      | „BRAK” lub RetailTransactionFiscalCustomer.SerializedData                                                            |
| NazwaKontrahenta   | Nazwa odbiorcy z danych głównych odbiorcy (RetailTransactionSupplementaryInvoice.AccountNum) lub „BRAK” |
| DowodSprzedazy     | RetailTransactionSupplementaryInvoice.InvoiceId                                                                     |
| DataWystawienia    | RetailTransactionSupplementaryInvoice.InvoiceDate                                                                   |
| DataSprzedazy      | RetailTransactionSalesTrans.TransDate                                                                               |
| TypDokumentu       | FP                                                                                                                  |

Pola tabeli SAFTTaxTransByReportingCode_PL są wypełniane na podstawie następujących źródeł danych.

| Nazwa tabeli                            | Nazwy pól                                                                                        |
|---------------------------------------|----------------------------------------------------------------------------------------------------|
| RetailTransactionTable                | Typ, EntryStatus, StatementId, kanał, sklep, Terminal, TransactionId                            |
| RetailTransactionTaxTrans             | TaxCode, TaxPercentage, TaxBaseAmount, kwota, IsExempt, kanał, StoreId, Terminal, TransactionId |
| RetailTransactionSupplementaryInvoice | InvoiceId, InvoiceDate, AccountNum, CustInvoiceJour, kanał, sklep, Terminal, TransactionId       |
| RetailTransactionSalesTrans           | TaxGroup, TaxItemGroup, TransDate, waluta, kanał, sklep, TerminalId, TransactionId             |
| RetailTransactionFiscalCustomer       | SerializedData, kanał, sklep, Terminal, TransactionId                                            |

#### <a name="report-fiscal-document-converted-to-invoice-parameter"></a>Parametry raportowania dokumentu fiskalnego przekonwertowanego na fakturę

Domyślnie pole wyboru **Zgłoś dokument fiskalny przekonwertowany na fakturę** nie jest zaznaczone. W takim przypadku, jeśli zbiór transakcji podatkowych i powiązanych z nimi faktur dla odbiorcy został zagregowany i zgłoszony jako dokumenty typu **RO**, są one wykluczone ze zbioru transakcji raportowanych domyślnie.

Gdy pole wyboru **Zgłoś dokument fiskalny przekonwertowany na fakturę** jest zaznaczone, system zbiera faktury z tabeli CustInvoiceJour przy użyciu tych samych rekordów **Kryteria zbierania faktur dla odbiorcy na potrzeby agregacji**, które są zdefiniowane dla faktur krajowych do agregacji. Stosowane są także następujące kryteria dodatkowe:

- Wartość **CustInvoiceJour_PL.FiscalDocState_PL** musi być równa wartości pola **Dokument fiskalny przekonwertowany na fakturę**.
- **CustInvoiceJour_PL.FiscalDocDate_PL** musi być w okresie raportu.

Podczas wstępnego przetwarzania te faktury są traktowane jako faktury standardowe. Jedyną różnicą jest to, że ich typ dokumentu jest ustawiany na **FP**.

## <a name="report-invoices-from-counterparties-in-different-countries-or-regions-that-have-identical-nip-numbers"></a>Raportuje faktury od kontrahentów z różnych krajów lub regionów, którzy mają identyczne numery NIP 

Struktura danych w raporcie JPK_V7M zawiera dane z pierwszego kodu kraju/regionu ISO, który został znaleziony w tabeli Numery identyfikacji podatkowej i zaksięgowany w tabeli Transakcje podatkowe. Stosuj różne numery identyfikacji podatkowej dla kontrahentów z różnych krajów lub regionów. Aby podczas konfigurowania rozróżnić identyczne numery identyfikacji podatkowej z różnych krajów lub regionów, należy użyć prefiksu z kodem ISO kraju/regionu. Dwie pierwsze litery kodu ISO kraju/regionu zostaną pominięte podczas raportowania w znaczniku **NrDostawcy**.

## <a name="split-payment-mpp-marker"></a>Marker podzielonej płatności (MPP)

Raport JPK-V7M obsługuje raportowanie znacznika **MPP** dla rejestrów sprzedaży i rejestrów zakupów dla okresów raportowania przed 1 lipca 2021 roku. Znacznik **MPP** nie jest wymagany w okresach po 1 lipca 2021.

Jeśli firma wykonuje operacje, dla których należy zastosować procedurę podzielonej płatności, należy użyć funkcji **Podzielona płatność**.

Gdy jest używana funkcja **podzielonej płatności**, nie trzeba wykonywać żadnej specjalnej konfiguracji, aby zgłosić marker **MPP** w JPK-V7M. Do identyfikacji markera **MPP** jest używany następujący algorytm:

- System zapewnia kontrolę parametrów **Podzielona płatność** i **Dobrowolna podzielona płatność** dla transakcji odbiorcy, która jest związana z fakturą sprzedaży. Jeśli wybrano parametr **Podzielona płatność**, a parametr **Dobrowolna podzielona płatność** jest wyczyszczony, powiązana faktura zostanie zaraportowana przy użyciu znacznika **MPP**.
- System zapewnia kontrolę parametrów **Podzielona płatność** i **Dobrowolna podzielona płatność** dla transakcji dostawcy, która jest związana z fakturą od dostawcy. Jeśli wybrano parametr **Podzielona płatność**, a parametr **Dobrowolna podzielona płatność** jest wyczyszczony, powiązana faktura zostanie zaraportowana przy użyciu znacznika **MPP**.
