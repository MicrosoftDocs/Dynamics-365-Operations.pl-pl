---
title: EEU 00047 Zaliczka dla pracownika
description: Ta procedura pokazuje, jak skonfigurować i zarejestrować transakcje dla posiadacza zaliczki.
author: v-oloski
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RCashTable, LedgerJournalSetup, HcmWorkerGroup_RU, EmplPosting_RU, VendParameters, RCashPosting, BankParameters, PaymTerm, HcmWorker, HcmWorkerNewWorker, HcmWorkerAdvHolderTableListPage_RU, HcmWorkerAdvHolderTable_RU, PurchTable, PurchCreateOrder, HcmAdvHolderLookup_RU, InventItemIdLookupPurchase, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog, EmplTrans_RU, EmplBalance_RU
audience: Application User
ms.reviewer: kfend
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e4742071dbf8ea4e312ab7f9f068b68c0ece6c2bff4c8533f1fdbb904c26b0dd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744916"
---
# <a name="eeu-00047-advance-payment-to-employee"></a>EEU 00047 Zaliczka dla pracownika

[!include [banner](../../includes/banner.md)]

Ta procedura pokazuje, jak skonfigurować i zarejestrować transakcje dla posiadacza zaliczki. Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się na Litwie. To zadanie działa tylko dla firm, których adres podstawowy znajduje się w Polsce, na Litwie, na Łotwie, w Estonii, w Czechach lub na Węgrzech. Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.


## <a name="create-a-new-cash-account"></a>Tworzenie nowego konta kasowego
1. Kliknij kolejno opcje Zarządzanie gotówką i bankami > Konta bankowe > Konta kasowe.
2. Kliknij przycisk Nowy.
3. W polu Kasa wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. W polu Grupa sekwencji numerów wprowadź lub wybierz wartość.
6. Rozwiń sekcję Weryfikacja.
7. W polu Waluta wprowadź lub wybierz wartość.
8. W polu Ujemne saldo kasowe wybierz opcję Tak.
9. Kliknij przycisk Zapisz.

## <a name="create-a-new-journal"></a>Tworzenie nowego arkusza
1. Wybierz kolejno opcje Księga główna > Konfiguracja arkusza > Nazwy arkuszy.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
4. W polu Seria załączników wprowadź lub wybierz wartość.
5. Kliknij przycisk Zapisz.
6. Kliknij przycisk Nowy.
7. W polu Nazwa wpisz wartość.
8. W polu Typ arkusza wybierz opcję.
9. W polu Seria załączników wprowadź lub wybierz wartość.
10. Kliknij przycisk Zapisz.

## <a name="create-an-advance-holder-group"></a>Tworzenie grupy posiadaczy zaliczek
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia > Posiadacze zaliczek > Grupy posiadaczy zaliczek.
2. Kliknij przycisk Nowy.
3. W polu Grupa wpisz wartość.
4. Wypełnij pole Opis.
5. Kliknij przycisk Zapisz.

## <a name="create-an-employee-posting-profile"></a>Tworzenie profilu księgowania pracownika etatowego
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia > Posiadacze zaliczek > Profile księgowania pracowników.
2. Kliknij przycisk Nowy.
3. W polu Profil księgowania wpisz wartość.
4. Wypełnij pole Opis.
5. Na liście oznacz wybrany wiersz.
6. W polu Ważny dla wybierz opcję.
7. W polu Konto rozrachunkowe podaj żądane wartości.
8. Kliknij przycisk Zapisz.

## <a name="set-up-advance-holder-parameters"></a>Konfigurowanie parametrów posiadaczy zaliczek
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia > Parametry modułu rozrachunków z dostawcami.
2. Kliknij kartę Posiadacze zaliczek.
3. W polu Profil księgowania wprowadź lub wybierz wartość.
4. W polu Nazwa wprowadź lub wybierz wartość.
5. Wprowadź lub wybierz wartość w polu Kasa.
6. W polu Nazwa wprowadź lub wybierz wartość.
7. W polu Typ konta zaznacz opcję.
8. W polu Konto główne podaj żądane wartości.
9. Kliknij kartę Sekwencje numerów.
10. Kliknij przycisk Zapisz.

## <a name="set-up-a-cash-posting-profile"></a>Konfigurowanie profilu księgowania kasy
1. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Profile księgowania kasy.
2. Kliknij przycisk Nowy.
3. W polu Księgowanie kasy wpisz wartość.
4. Wypełnij pole Opis.
5. Na liście oznacz wybrany wiersz.
6. W polu Ważny dla wybierz opcję.
7. W polu Konto główne podaj żądane wartości.
8. Kliknij przycisk Zapisz.

## <a name="set-up-cash-and-bank-parameters"></a>Konfigurowanie parametrów kasy i banku
1. Wybierz kolejno opcje Zarządzanie gotówką i bankami > Ustawienia > Parametry modułu Zarządzanie gotówką i bankami.
2. Kliknij kartę Kasa.
3. Wprowadź lub wybierz wartość w polu Kasa.
4. Wprowadź lub wybierz wartość w polu Księgowanie kasy.
5. Kliknij przycisk Zapisz.
6. Kliknij kartę Sekwencje numerów.
7. Na liście znajdź i zaznacz odpowiedni rekord.
8. W polu Kod sekwencji numerów wprowadź lub wybierz wartość.
9. Na liście znajdź i zaznacz odpowiedni rekord.
10. W polu Kod sekwencji numerów wprowadź lub wybierz wartość.
11. Kliknij przycisk Zapisz.

## <a name="set-up-terms-of-payment"></a>Ustaw warunki płatności
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia płatności > Warunki płatności.
2. Kliknij przycisk Edytuj.
3. W polu Od posiadacza zaliczki wybierz opcję Tak.
4. Kliknij przycisk Zapisz.

## <a name="create-a-new-worker"></a>Tworzenie nowego pracownika
1. Wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Pracownicy.
2. Kliknij przycisk Nowy.
3. W polu Imię wpisz wartość.
4. W polu Nazwisko wpisz wartość.
5. W polu Identyfikator pracownika wpisz wartość.
6. Kliknij przycisk Zatrudnij nowego pracownika.
7. Kliknij przycisk Zapisz.

## <a name="set-up-a-worker-as-an-advance-holder"></a>Konfigurowanie pracownika jako posiadacza zaliczki
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Posiadacze zaliczek > Posiadacze zaliczek.
2. Kliknij przycisk Edytuj.
3. W polu Grupa wprowadź lub wybierz wartość.
4. W polu Posiadacz zaliczki wybierz opcję Tak.
5. Kliknij przycisk Zapisz.

## <a name="create-and-post-a-purchase-order-invoice"></a>Tworzenie i księgowanie faktury zamówienia zakupu
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.
2. Kliknij przycisk Nowy.
3. W polu Konto dostawcy wprowadź lub wybierz wartość.
4. Kliknij przycisk OK.
5. W polu Wiersze lub nagłówek wybierz opcję.
6. Rozwiń sekcję Cena i rabat.
7. W polu Warunki płatności wprowadź lub wybierz wartość.
8. Wprowadź lub wybierz wartość w polu Posiadacz zaliczki.
9. W polu Wiersze lub nagłówek wybierz opcję.
10. Na liście oznacz wybrany wiersz.
11. W polu Numer towaru wprowadź lub wybierz wartość.
12. Wprowadź liczbę w polu Ilość.
13. Wprowadź liczbę w polu Cena jednostkowa.
14. Kliknij przycisk Zapisz.
15. W okienku akcji kliknij pozycję Zakup.
16. Kliknij przycisk Potwierdź.
17. W okienku akcji kliknij pozycję Faktura.
18. Kliknij opcję Faktura.
19. Na liście Domyślnie z zaznacz opcję Ilość z dokumentu przyjęcia produktów, aby otworzyć rozwijane okno dialogowe.
20. W polu Domyślna ilość dla wierszy zaznacz opcję.
21. Kliknij przycisk OK.
22. W polu Numer wpisz wartość.
23. Wypełnij pole Opis faktury.
24. W polu Data faktury wprowadź datę.
25. W polu Data rejestru VAT wpisz datę.
26. W polu Data otrzymania dokumentu wprowadź datę.
27. Kliknij przycisk Księguj.

## <a name="balance-and-close-advance-holders-transactions"></a>Bilansowanie i zamykanie transakcji posiadaczy zaliczek
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Posiadacze zaliczek > Posiadacze zaliczek.
2. Kliknij opcję Transakcje.
3. Zamknij stronę.
4. Kliknij opcję Saldo.
5. Kliknij opcję Zamknij — bank.
6. W polu Automatycznie wybierz opcję Tak.
7. W polu Kwota do przeniesienia wpisz liczbę.
8. Kliknij przycisk OK.
9. Kliknij opcję Zamknij — kasa.
10. W polu Automatycznie wybierz opcję Tak.
11. Kliknij przycisk OK.
12. Zamknij stronę.
13. Kliknij opcję Transakcje.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]