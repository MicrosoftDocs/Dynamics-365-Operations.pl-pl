---
title: Tworzenie pozwolenia na polecenie zapłaty dla odbiorcy
description: W tym przewodniku po zadaniach pokazano, jak utworzyć zgodę na polecenie zapłaty, a następnie używać go na fakturze.
author: ShivamPandey-msft
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e3bbf3703941255dfd82b8fb501ba8a9d1f3a2ec
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835083"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a>Tworzenie pozwolenia na polecenie zapłaty dla odbiorcy

[!include [banner](../../includes/banner.md)]

W tym przewodniku po zadaniach pokazano, jak utworzyć zgodę na polecenie zapłaty, a następnie używać go na fakturze.


## <a name="create-a-bank-account"></a>Tworzenie konta bankowego
1. W **okienku nawigacji** otwórz **Moduły > Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy**.
2. Na liście wybierz rekord. Na przykład zaznacz US-001.
3. W okienku akcji kliknij pozycję **Odbiorca**.
4. Kliknij przycisk **konta bankowe**.
5. Kliknij przycisk **Nowy**.
6. W polu **Konto bankowe** wpisz wartość.
7. W polu **Nazwa** wpisz wartość.
8. W polu **IBAN** wpisz wartość.
9. W polu **Waluta** wpisz wartość.
10. Kliknij przycisk **Zapisz**.
11. Zamknij stronę.
12. W **okienkun awigacji** przejdź do **Moduły > Zarządzanie gotówką i bankami > Konta bankowe > Konta bankowe**.
13. Na liście znajdź i zaznacz odpowiedni rekord.
14. Na liście kliknij łącze w wybranym wierszu.
15. Kliknij przycisk **Edytuj**.
16. Rozwiń kartę skróconą **Dodatkowa identyfikacja**.
17. W polu **Identyfikator polecenia zapłaty** wpisz wartość.
18. W polu **IBAN** wpisz wartość.
19. Zamknij stronę.
20. Zamknij stronę.

## <a name="define-the-electronic-payment-method"></a>Konfigurowanie elektronicznej metody płatności
1. W **okienku nawigacji** przejdź do **Moduły > Rozrachunki z odbiorcami > Ustawienia płatności > Metody płatności**.
2. Kliknij przycisk **Nowy**.
3. W polu **Metoda płatności** wpisz wartość.
4. W polu **Opis** wpisz wartość.
5. W polu **Typ płatności** wybierz opcję „Płatność elektroniczna”. Typem płatności dla zgody na płacenie poleceniem zapłaty musi być płatność elektroniczna.
6. W polu **Wymaga zgody** wybierz opcję Tak.
7. Zamknij stronę.

## <a name="add-a-direct-debit-mandate-to-a-customer"></a>Dodawanie zgody na polecenie zapłaty do odbiorcy
1. W **okienku nawigacji** otwórz **Moduły > Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy**.
2. Na liście wybierz rekord. Na przykład zaznacz US-001.
3. Kliknij przycisk **Edytuj**.
4. Rozwiń skróconą kartę **Ustawienia domyślne płatności**.
5. W polu **Metoda płatności** wprowadź lub wybierz wartość.
6. Rozwiń skróconą kartę **Ustawienia domyślne płatności**.
7. Rozwiń skróconą kartę **Pozwolenia na polecenie zapłaty**.
8. Kliknij przycisk **Dodaj**.
9. W polu **Konto bankowe** wprowadź lub wybierz wartość.
10. W polu **Konto bankowe wierzyciela** wprowadź lub wybierz wartość.
11. W polu **Częstość płatności** wprowadź liczbę płatności, jaką oczekujesz przetwarzać w ramach tej zgody.
12. Kliknij przycisk **OK**.
13. Kliknij przycisk **Drukuj**.
14. Kliknij opcję **Raport dotyczący zgody**.
15. Zamknij stronę.
16. Kliknij przycisk **Edytuj**.
17. W polu **Data podpisania** wprowadź datę.
18. Kliknij przycisk **Tak**.
19. Wpisz miejsce, w którym zgoda została podpisana.
20. Kliknij przycisk **OK**.
21. Zamknij stronę.

## <a name="create-a-free-text-invoice-with-mandate"></a>Tworzenie faktury niezależnej ze zgodą
1. W **okienku nawigacji** otwórz **Moduły > Rozrachunki z odbiorcami > Faktury > Wszystkie faktury niezależne**.
2. Kliknij przycisk **Nowy**.
3. Zaznacz odbiorcę, dla którego dodano zgodę.
4. W polu **Identyfikator zgody na polecenie zapłaty** wprowadź lub wybierz wartość.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]