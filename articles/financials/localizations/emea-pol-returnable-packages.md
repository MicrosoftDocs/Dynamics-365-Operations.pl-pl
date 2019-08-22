---
title: Opakowania zwrotne dla Polski
description: Ten temat zawiera opis sposobu konfigurowania i używania opakowań zwrotnych dla Polski.
author: ShylaThompson
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PlCustPackageHolder, PlCustPackageReturn, PlInventPackageTable, PlInventPackageTrans
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 273043
ms.assetid: decdb3af-9fc3-4aff-add1-bbb9d2eadc27
ms.search.region: Poland
ms.author: ilyako
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 55150454d721fde0d13eb2dee503bbdc05eea52a
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852436"
---
# <a name="returnable-packaging-for-poland"></a>Opakowania zwrotne dla Polski
[!include [banner](../includes/banner.md)]

Funkcjonalność opakowań zwrotnych pozwala obsługiwać rejestrowanie opakowań, które mogą być zwracane przez odbiorców. Użytkownicy mogą definiować kody opakowań i określać kwotę kaucji, jaką odbiorca płaci za zwrotne materiały opakowaniowe. Ta funkcjonalność jest rozszerzeniem standardowej funkcjonalności materiałów opakowaniowych.

## <a name="prerequisites"></a>Wymagania wstępne
W poniższej tabeli przedstawiono wymagania wstępne, które muszą istnieć przed rozpoczęciem.

| Kategoria                | Wymaganie wstępne                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Konfiguracja:** Firma | Podstawowy adres firmy musi być w Polsce. Na stronie **Firmy** (**Administrowanie organizacją** &gt; **Organizacje** &gt; **Firmy**) wybierz swoją firmę. Następnie na skróconej karcie **Adresy** utwórz nowy adres lub zaktualizuj istniejący adres, wybierz **Polska** jako kraj/region, wprowadź pozostałe składniki adresu i zaznacz ten adres jako **Podstawowy**. |

## <a name="set-up-returnable-packages"></a>Konfigurowanie opakowań zwrotnych
W tej sekcji opisano różne ustawienia, które należy skonfigurować, aby korzystać z funkcjonalności opakowań zwrotnych.

### <a name="define-packaging-codes"></a>Definiowanie kodów opakowań

Na stronie **Opakowania zwrotne** (**Zarządzanie zapasami** &gt; **Ustawienia** &gt; **Materiał opakowania** &gt; **Opakowania zwrotne**) wprowadź wartości w następujących polach:

| Pole               | opis                                                                    |
|---------------------|--------------------------------------------------------------------------------|
| Kod opakowania      | Wprowadź unikatowy kod dla zwróconego opakowania.                                    |
| Opis opakowania | Umożliwia wprowadzenie opisu zwróconego opakowania.                                 |
| Przelew             | Wprowadź kwotę kaucji, jaką odbiorca płaci za zwrotne opakowanie. |

### <a name="attach-packaging-codes-to-packing-units"></a>Dołączanie kodów opakowań do jednostek opakowaniowych

Na stronie **Alokacja materiałów opakowań** (**Zarządzanie zapasami** &gt; **Ustawienia** &gt; **Materiał opakowania** &gt; **Alokacja materiałów opakowań**) można dołączyć kody opakowań do jednostek opakowaniowych dla wszystkich towarów, wybranych towarów lub określonych grup opakowań. Tylko poniższe pole jest specyficzne dla Polski. Rozszerza ono standardową funkcjonalność strony **Alokacja materiałów opakowań**.

| Pole          | opis                                                     |
|----------------|-----------------------------------------------------------------|
| Kod opakowania | Wybierz kod opakowania, które jest zwracane przez klienta. |

### <a name="set-up-a-number-sequence-for-package-vouchers"></a>Konfigurowanie numeracji załączników opakowań

Na stronie **Parametry modułu rozrachunków z odbiorcami** (**Rozrachunki z odbiorcami** &gt; **Ustawienia** &gt; **Parametry modułu rozrachunków z odbiorcami**) na skróconej karcie **Alokacja materiałów opakowań** skonfiguruj numerację dla pola odwołania **Załącznik do opakowania**.

### <a name="set-up-a-deposit-account"></a>Konfigurowanie konta kaucji

Gdy faktura sprzedaży jest księgowana, specjalny załącznik służy do księgowania opłaty odbiorcy za materiał opakowaniowy. Wszystkie transakcje kaucji są księgowane na odrębnym koncie, którego już powinno być zdefiniowane w powiązanym profilu księgowania odbiorcy. Na stronie **Profil księgowania odbiorcy** (**Rozrachunki z odbiorcami** &gt; **Ustawienia** &gt; **Profil księgowania odbiorcy**) wprowadź wartość w polu **Kaucje**.

## <a name="register-and-verify-returnable-packages"></a>Rejestrowanie i weryfikowanie opakowań zwrotnych
Użytkownicy mogą rejestrować opakowania dla zamówień sprzedaży, księgować i drukować dokumenty dostawy zawierające ilości wydanych opakowań oraz księgować i drukować faktury dla odbiorców. Użytkownicy mogą również uzyskiwać i weryfikować informacje o ilościach zapakowanych towarów dla zamówień sprzedaży.

### <a name="register-packages-in-a-sales-order"></a>Rejestrowanie opakowań w zamówieniu sprzedaży

Na stronie **Wszystkie zamówienia sprzedaży** (**Rozrachunki z odbiorcami** &gt; **Wspólne** &gt; **Zamówienia sprzedaży** &gt; **Wszystkie zamówienia sprzedaży**) utwórz nowe zamówienie sprzedaży lub otwórz istniejące zamówienie sprzedaży. Przełącz na widok **Wiersze** i utwórz nowy wiersz zamówienia sprzedaży lub wybierz istniejący wiersz zamówienia sprzedaży. Na skróconej karcie **Szczegóły wiersza** na karcie **Opakowanie** w polu **Jednostka opakowania** wybierz jednostkę opakowaniową, która jest dołączona do kodu opakowania zdefiniowanego wcześniej dla opakowań zwrotnych. Liczba opakowań, które odbiorca może zwrócić, jest obliczana automatycznie i wyświetlana w polu **Liczba jednostek opakowania**.

### <a name="verify-packages"></a>Weryfikowanie opakowań

Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz wiersz zamówienia sprzedaży, a następnie kliknij kolejno opcje **Finanse** &gt; **Opakowania** &gt; **Wydanie opakowań**, a zostanie otwarta strona **Wydanie opakowań**. Gdy ta strona zostanie otwarta z wiersza zamówienia sprzedaży, użytkownicy mogą modyfikować lub usuwać opakowania, które są automatycznie obliczane dla tego wiersza zamówienia sprzedaży. Alternatywnie w okienku akcji dla strony **Zamówienie sprzedaży** na karcie **Ogólne** kliknij opcję **Wydanie opakowań**. Gdy strona **Wydanie opakowań** jest otwierana przy użyciu tej metody, użytkownicy mogą wyświetlić pakiety, które są obliczane dla wszystkich wierszy zamówienia sprzedaży. W razie potrzeby mogą również dodawać kolejne opakowania.

### <a name="print-and-post-packing-slips"></a>Drukowanie i księgowanie dokumentów dostawy

Na stronie **Zamówienie sprzedaży** w okienku akcji na karcie **Pobierz i zapakuj** kliknij opcję **Księguj dokument dostawy**. Po zaksięgowaniu dokumentów dostawy użytkownicy mogą wysyłać zapytania o transakcje wydania opakowań dla każdego dokumentu dostawy. Kliknij kolejno opcje **Zarządzanie zapasami** &gt; **Ustawienia** &gt; **Materiały opakowań** &gt; **Opakowania zwrotne**, a następnie na karcie **Transakcje** kliknij opcję **Transakcje**, a zostanie otwarta strona **Transakcje opakowań zwrotnych**.

### <a name="print-and-post-invoices"></a>Drukowanie i księgowanie faktur

Na stronie **Zamówienie sprzedaży** w okienku akcji na karcie **Faktura** kliknij kolejno opcje **Generuj** &gt; **Faktura**. Po zaksięgowaniu faktur użytkownicy mogą wysyłać zapytania o transakcje na opakowaniach, które mają zaksięgowane kwoty kaucji dla każdej faktury. Kliknij kolejno opcje **Zarządzanie zapasami** &gt; **Ustawienia** &gt; **Materiały opakowań** &gt; **Opakowania zwrotne**, a następnie na karcie **Transakcje** kliknij opcję **Transakcje**, a zostanie otwarta strona **Transakcje opakowań zwrotnych**. Kliknij opcję **Załącznik**, a zostanie otwarta strona **Transakcje na załączniku**. Sprawdź kwoty kaucji odbiorcy, które są zaksięgowane na koncie głównym. Numer konta głównego jest określony na stronie **Profile księgowania odbiorców**. Aby wydrukować raport **Transakcje kaucji dla opakowań**, kliknij przycisk **Drukowanie**. Użytkownicy mogą również wykonywać zapytania o sumy opakowań zwrotnych dla wybranego odbiorcy. Kliknij kolejno opcje **Rozrachunki z odbiorcami** &gt; **Wszyscy odbiorcy**, a następnie na karcie **Windykacja** kliknij przycisk **Opakowania u odbiorców**, co spowoduje otwarcie strony **Transakcje opakowań zwrotnych**.

## <a name="post-and-print-packages-returns"></a>Księgowanie i drukowanie informacji o zwrotach opakowań
Aby wprowadzić informacje o opakowaniach zwracanych przez odbiorców, kliknij kolejno opcje **Rozrachunki z odbiorcami** &gt; **Wszyscy odbiorcy**, a następnie na karcie **Windykacja** kliknij opcję **Zwrot opakowań**, co spowoduje otwarcie strony **Potwierdzenie zwrotu opakowań**. Wprowadź wartości w następujących polach: **Sekcja Opakowania zwrotne**

| Pole       | opis                                                                                        |
|-------------|----------------------------------------------------------------------------------------------------|
| Data        | Umożliwia wprowadzenie daty zwrotu opakowania.                                                                |
| opis | Umożliwia wprowadzenie opisu zwrotu opakowania.                                                         |
| Zaksięgowany      | Wartość wskazująca, czy zwrot opakowania został zaksięgowany. Ta wartość jest aktualizowana automatycznie. |

**Sekcja Transakcje opakowań zwrotnych**

| Pole                         | opis                                                                                                                                                          |
|-------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kod opakowania                | Umożliwia wybranie kodu opakowania, które ma zostać zwrócone.                                                                                                                                   |
| Ilość zwrotu               | Określ liczbę opakowań do zwrotu. Wartość nie może przekraczać wartości w polu **Ilość możliwa do zwrotu**.                                             |
| Ilość możliwa do zwrotu | Maksymalna liczba opakowań, jaką można zwrócić. Ta wartość jest obliczana automatycznie.                                                                         |
| Ilość                        | Kwota, którą należy zapłacić odbiorcy. Ta wartość jest obliczana automatycznie na podstawie kwoty kaucji za opakowanie i zwróconej ilości. |
| Waluta                      | Waluta kwoty, którą należy zapłacić odbiorcy.                                                                                                       |

Po zakończeniu wprowadzania informacji o zwrotach opakowań kliknij przycisk **Księguj**, aby zaksięgować transakcję zwrotu. Na stronie księgowania należy ustawić opcję **Drukuj** na **Tak**, aby wydrukować raport **Potwierdzenie zwrotu opakowań**. Aby ponowne wydrukować raport potwierdzenia później, można kliknąć przycisk **Drukuj** na stronie **Potwierdzenie zwrotu opakowań**. Użytkownicy mogą wysyłać zapytania o transakcje opakowaniami zwrotnymi. Kliknij kolejno opcje **Zarządzanie zapasami** &gt; **Ustawienia** &gt; **Materiały opakowań** &gt; **Opakowania zwrotne**, a następnie na karcie **Transakcje** kliknij opcję **Transakcje**, a zostanie otwarta strona **Transakcje opakowań zwrotnych**. Transakcje na opakowaniach zwrotnych będą miały wartości ujemne w polu **Liczba opakowań**. Kliknij opcję **Załącznik**, aby wyświetlić szczegóły wybranej transakcji. Kliknij przycisk **Drukowanie**, aby wydrukować raport **Potwierdzenie zwrotu opakowań**.


