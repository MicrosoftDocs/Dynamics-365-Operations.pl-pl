---
title: Faktury zaliczkowe dla Europy Wschodniej
description: "Faktura zaliczkowa jest dokumentem, który można utworzyć dla odbiorcy lub dostawcy. Podaje ona kwotę, która ma zostać opłacona z góry z tytułu zamówienia sprzedaży. Ten temat zawiera informacje dotyczące faktur zaliczkowych dla Europy Wschodniej."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 272643
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: epopov
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 97be3eee9ebb99af33e3153fe7726ed5b086b03c
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="advance-invoices-for-eastern-europe"></a>Faktury zaliczkowe dla Europy Wschodniej

[!include [banner](../includes/banner.md)]

Faktura zaliczkowa jest dokumentem, który można utworzyć dla odbiorcy lub dostawcy. Podaje ona kwotę, która ma zostać opłacona z góry z tytułu zamówienia sprzedaży. Ten temat zawiera informacje dotyczące faktur zaliczkowych dla Europy Wschodniej.

Funkcjonalność faktur zaliczkowych umożliwia wykonywanie następujących zadań:

-   Wystawianie faktur zaliczkowych odbiorcom i śledzenie stanu tych faktur (**Otwarte**, **Częściowo zapłacone** lub **Zamknięte**).
-   Księgowanie transakcji faktur zaliczkowych i transakcji podatku od wartości dodanej (VAT) (tylko dla Polski).
-   Automatyczne generowanie wierszy arkusza płatności na podstawie faktury zaliczkowej.
-   Łączenie przedpłat otrzymywanych od odbiorców z fakturami zaliczkowymi (przed lub po zaksięgowaniu przedpłaty).
-   Zmiana księgowania podatku VAT w zaksięgowanych przedpłatach (czyli konwertowanie przedpłaty na płatność lub płatności na przedpłatę albo zmiana daty księgowania, stawka podatku lub kwoty).
-   Tworzenie dokumentu podatkowego w celu dostarczenia należnego podatku VAT (tylko w przypadku Czechy).

## <a name="advance-invoices-for-poland"></a>Faktury zaliczkowe dla Polski
Polskie firmy otrzymujące przedpłatę muszą utworzyć fakturę na przedpłatę dla odbiorcy. Ta faktura zaliczkowa jest księgowana w księdze głównej i jest dokumentem obowiązkowym do rozliczania podatku VAT. Podatek obliczony w fakturze zaliczkowej należy zgłosić do urzędu skarbowego. Podczas ostatecznej sprzedaży towarów faktura zaliczkowa musi być podana w fakturze sprzedaży. Łączna kwota sprzedaży musi zawierać przedpłaty. Podczas księgowania faktury sprzedaży rozliczona faktura zaliczkowa zostanie wycofana. Oryginalna faktura zaliczkowa zostanie rozliczona za pomocą wycofania faktury zaliczkowej.

## <a name="set-up-accounts-receivable-for-advance-invoices"></a>Konfigurowanie modułu rozrachunków z odbiorcami dla faktur zaliczkowych
Na stronie **Parametry modułu rozrachunków z odbiorcami** na karcie **Aktualizacje** określ następujące parametry:


|     Skrócona karta     |             Parametr             |                                                                                                                                                                                           opis                                                                                                                                                                                           |
|-----------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Faktura zaliczkowa |          Profil księgowania          | Wybierz profil księgowania, który ma być używany do fakturowania zaliczek (tylko Polska). <strong>Ważne:</strong> W Czechach i na Węgrzech faktury zaliczkowe nie są traktowane jako dokumenty księgowe ani podatkowe i nie są księgowane w księdze głównej. W związku z tym dla tych krajów należy pozostawić to pole puste, aby uniemożliwić księgowanie faktur zaliczkowych w księdze głównej. |
|                 |                                   |                                                                                                                                                                                                                                                                                                                                                                                                 |
| Faktura zaliczkowa |                Wył.                |                                                                                                                                                                                           Konto przeciwstawne                                                                                                                                                                                           |
| Faktura zaliczkowa |          Grupa podatków          |                                                                                                                                                      Umożliwia wybór grupy podatków używanej podczas obliczania podatku w fakturowaniu zaliczek.                                                                                                                                                      |
| Faktura zaliczkowa |      Wycofanie jako korekta       |                                                                                                                                                 To pole wyboru należy zaznaczyć, jeśli wycofanie faktury zaliczkowej powinno być uznawane za korektę.                                                                                                                                                  |
| Faktura zaliczkowa |      Wycofaj w dniu określonym datą faktury      |                                                                                                                                                     To pole wyboru należy zaznaczyć, aby cofnąć przedpłatę w dniu zaksięgowania faktury.                                                                                                                                                     |
|     Płatność     |     Wiele dat przedpłaty     |                                                                                                                                        Wybierz jedną z następujących opcji: <strong>Akceptacja</strong>, <strong>Ostrzeżenie</strong> lub <strong>Błąd</strong>.                                                                                                                                         |
|     Płatność     |           Niezgodność dat           |                                                                                                                                        Wybierz jedną z następujących opcji: <strong>Akceptacja</strong>, <strong>Ostrzeżenie</strong> lub <strong>Błąd</strong>.                                                                                                                                         |
|     Płatność     |          Niezgodność kwot          |                                                                                                                                        Wybierz jedną z następujących opcji: <strong>Akceptacja</strong>, <strong>Ostrzeżenie</strong> lub <strong>Błąd</strong>.                                                                                                                                         |
|     Płatność     | Łączenie z zaksięgowaną fakturą zaliczkową |                                                                                                                                        Wybierz jedną z następujących opcji: <strong>Akceptacja</strong>, <strong>Ostrzeżenie</strong> lub <strong>Błąd</strong>.                                                                                                                                         |
|     Płatność     | (CZE), (POL) Obsługa przedpłat  |                                                                                                                                                                                Wybierz opcję <strong>Zaawansowane</strong>.                                                                                                                                                                                |

Na karcie **Sekwencje identyfikatorów** skonfiguruj numeracje dla następujących odwołań:

-   Dokument podatkowy
-   Memorandum kredytowe dla podatku
-   Faktura zaliczkowa
-   Faktura korygująca do faktury zaliczkowej
-   Wycofanie faktury zaliczkowej
-   Załącznik faktury zaliczkowej
-   Załącznik faktury korygującej do faktury zaliczkowej
-   Załącznik do wycofania faktury zaliczkowej

## <a name="create-a-customer-advance-invoice"></a>Tworzenie faktury płatności zaliczkowej dla odbiorcy
Kliknij kolejno opcje **Rozrachunki z odbiorcami** &gt; **Wspólne** &gt; **Faktury zaliczkowe** &gt; **Wszystkie faktury zaliczkowe**. Aby utworzyć nową fakturę zaliczkową, w okienku akcji na karcie **Faktura zaliczkowa** kliknij opcję **Faktura zaliczkowa**. Wprowadź wymagane informacje, a następnie kliknij przycisk **Księguj** w celu zaksięgowania faktury zaliczkowej. Faktura zaliczkowa może mieć jeden z następujących stanów: **Otwarta**, **Częściowo zapłacono** lub **Zamknięta**. Można ręcznie zmienić stan faktury zaliczkowej, która została zaksięgowana. Kliknij przycisk **Stan**, a następnie na stronie **Zmień stan faktury zaliczkowej** w polu **Nowy stan** wybierz nowy stan faktury zaliczkowej. **Uwaga:** Można zmieniać stan faktury zaliczkowej w dowolnym momencie. Nie można przetwarzać zamkniętych faktur zaliczkowych w transakcjach. **Uwaga:** Dla Polski transakcje faktur zaliczkowych są generowane, jeśli skonfigurowano profil księgowania dla faktur zaliczkowych na stronie Parametry modułu rozrachunków z odbiorcami. Aby wyświetlić transakcje, które zostały zaksięgowane, na stronie **Faktura zaliczkowa** kliknij opcję **Załącznik**.

## <a name="vat-on-advance-invoices"></a>VAT na fakturach zaliczkowych
Firmy muszą rejestrować podatek VAT w przedpłatach wnoszonych przez odbiorców, nawet jeśli sprzedaż nie została zakończona. Aby zaksięgować podatek VAT z przedpłaty, można do faktury zaliczkowej dodać wiersz zawierający specyfikacje podatku VAT. Faktura zaliczkowa może zawierać kilka wierszy, a wiersze mogą zawierać specyfikacje podatku VAT pobierane z wierszy zamówienia sprzedaży. W związku z tym można zaksięgować podatek VAT od przedpłaty w ścisłej zgodności z wierszami zamówienia sprzedaży. **Uwaga:** Specyfikacje podatku VAT są kopiowane do wierszy faktury zaliczkowej tylko wtedy, gdy na stronie **Kody podatków** w polu **Typ podatku** jest ustawiona wartość **Standardowy VAT** lub **Zredukowany VAT**. W przeciwnym razie wiersz jest kopiowany do faktury zaliczkowej, tak jakby kwota podatku VAT wynosiła 0 (zero).

## <a name="link-an-advance-invoice-to-a-sales-order-or-a-free-text-invoice"></a>Łączenie faktury zaliczkowej z zamówieniem sprzedaży lub fakturą niezależną
Każda faktura zaliczkowa może być połączona tylko z jednym zamówieniem sprzedaży lub fakturą niezależną na raz. Można przepisać istniejącą fakturę zaliczkową do innego zamówienia sprzedaży lub faktury niezależnej, pod warunkiem, że żadne przedpłaty nie są połączone z fakturą zaliczkową. Aby połączyć fakturę zaliczkową z zamówieniem sprzedaży, na stronie **Wszystkie faktury zaliczkowe** zaznacz fakturę zaliczkową. W okienku akcji kliknij kolejno opcje **Faktura zaliczkowa** i **Zamówienie sprzedaży**. Następnie zaznacz zamówienie sprzedaży, które ma zostać połączone z fakturą zaliczkową, i kliknij przycisk **OK**. Aby połączyć fakturę zaliczkową z fakturą niezależną, na stronie **Wszystkie faktury zaliczkowe** zaznacz fakturę zaliczkową. W okienku akcji kliknij kolejno opcje **Faktura zaliczkowa** i **Faktura niezależna**. Następnie zaznacz fakturę niezależną, która ma zostać połączona z fakturą zaliczkową, i kliknij przycisk **OK**.

## <a name="create-a-customer-advance-invoice-from-a-sales-order"></a>Utwórz faktury zaliczkowej dla odbiorcy na podstawie zamówienia sprzedaży
Utwórz zamówienie sprzedaży lub wybierz istniejące zamówienie sprzedaży. Kliknij opcję **Faktura**, a następnie kolejno opcje **Generuj** &gt; **Faktura zaliczkowa**. Na stronie **Utwórz fakturę zaliczkową** ustaw następujące pola.

| Pole                                           | opis                                                                                                                                                                                                                               |
|-------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Procent                                         | Określ procent przedpłaty dla zamówienia sprzedaży.                                                                                                                                                                             |
| Konto przeciwstawne                                  | Umożliwia wybór domyślnego konta przeciwstawnego, które ma być używane do fakturowania zaliczek.                                                                                                                                                                         |
| Aktualizuj zamówienie                                    | Wybierz jedną z następujących opcji: **Wszystko**, **Dostawa teraz**, **Pobrane**, **Dokument dostawy** lub **Ilość pobrana i produkty niemagazynowane**. Kwota faktury zaliczkowej będzie obliczana na podstawie kwot zamówień sprzedaży dla towarów. |
| Księguj podatek VAT                                        | Określ, czy podczas księgowania faktur zaliczkowych ma być księgowany podatek VAT.                                                                                                                                                                      |
| Data księgowania podatku VAT                                   | Umożliwia określenie daty zaksięgowania podatku VAT.                                                                                                                                                                                                         |
| Profil księgowania z użyciem załącznika arkusza zaliczki | Określ profil księgowania przedpłaty.                                                                                                                                                                                           |
| Utwórz dokument podatku                             | Określ, czy należy utworzyć dokument podatkowe.                                                                                                                                                                                         |

> [!UWAGA} Dla Polski transakcje faktur zaliczkowych są generowane, jeśli skonfigurowano profil księgowania dla faktur zaliczkowych na stronie Parametry modułu rozrachunków z odbiorcami.

## <a name="create-a-customer-advance-invoice-from-a-free-text-invoice"></a>Tworzenie faktury płatności zaliczkowej odbiorcy na podstawie faktury niezależnej
Utwórz fakturę niezależną lub wybierz istniejącą fakturę niezależną. Na karcie **Faktura** w sekcji **Nowy** kliknij opcję **Faktura zaliczkowa**. Następnie można utworzyć nową fakturę zaliczkową, która zostanie połączona z fakturą niezależną. **Uwaga:** Dla Polski transakcje faktur zaliczkowych są generowane, jeśli skonfigurowano profil księgowania dla faktur zaliczkowych na stronie Parametry modułu rozrachunków z odbiorcami.

## <a name="print-an-advance-invoice"></a>Drukowanie faktury zaliczkowej
Aby wydrukować fakturę zaliczkową, na stronie **Faktura zaliczkowa** kliknij przycisk **Drukuj**. W przypadku Polski można wydrukować dokument fiskalny faktury zaliczkowej. Wybierz opcję podczas księgowania faktury zaliczkowej. W przypadku Polski układy dokumentów faktury sprzedaży i faktury niezależnej powinny zawierać następujące informacje dotyczące rozliczanej faktury zaliczkowej:

-   Numer faktury zaliczkowej
-   Data faktury zaliczkowej
-   Kwota bez podatku VAT, kwota podatku VAT, kwota z podatkiem VAT i waluta
-   Procent podatku

Podsumowanie kwot podatku VAT powinno zawierać pozycję **Podatek z faktury zaliczkowej**. Kwota należna powinna być pomniejszona o kwotę faktury zaliczkowej.

## <a name="create-a-payment-proposal-from-an-advance-invoice"></a>Tworzenie propozycji płatności na podstawie faktury zaliczkowej
Wiersze arkusza płatności mogą być generowanie automatyczne na podstawie faktury zaliczkowej. Podczas tworzenia nowego arkusza płatności na stronie **Arkusz płatności** zaznacz opcję **Załącznik arkusza zaliczki**, a następnie kliknij opcję **Wiersze**. Na stronie **Załącznik arkusza** można kliknąć kolejno opcje **Propozycja płatności** &gt; **Propozycja płatności z faktury zaliczkowej**, aby utworzyć propozycję płatności na podstawie faktur zaliczkowych. Informacje takie jak profil księgowania i grupy podatków zostaną pobrane z faktury zaliczkowej. **Uwaga:** Nowe przedpłaty będą automatycznie łączone z fakturami zaliczkowymi, jeśli na stronie **Tworzenie propozycji płatności na podstawie faktur zaliczkowych** zaznaczono opcje **Połącz przedpłaty** i **Zmień stan**.

## <a name="link-a-prepayment-to-an-advance-invoice"></a>Połącz przedpłaty z fakturą zaliczkową
Aby połączyć przedpłatę z fakturą zaliczkową z arkusza płatności, otwórz arkusz płatności, zaznacz wiersz zawierający przedpłatę, a następnie kliknij kolejno opcje **Funkcje** &gt; **Połącz z fakturami zaliczkowymi**. Aby połączyć przedpłatę z fakturą zaliczkową ze strony **Transakcje odbiorcy**, kliknij kolejno opcje **Wszyscy odbiorcy** &gt; **Odbiorca** &gt; **Transakcje**. Zaznacz arkusz płatności, zaznacz wiersz zawierający przedpłatę, a następnie kliknij kolejno opcje **Funkcje** &gt; **Połącz z fakturami zaliczkowymi**.

## <a name="link-an-advance-invoice-to-a-prepayment"></a>Łączenie faktury zaliczkowej z przedpłatą
Aby połączyć fakturę zaliczkową z wierszem przedpłaty, na stronie **Wszystkie faktury zaliczkowe** zaznacz fakturę zaliczkową. W okienku akcji kliknij kolejno opcje **Faktura zaliczkowa** i **Przedpłata**. Następnie zaznacz wierszy przedpłaty, który ma zostać połączony z fakturą zaliczkową, i kliknij przycisk **OK**.

## <a name="advance-invoice-credit-note"></a>Faktura korygująca do faktury zaliczkowej
-   (POL) Aby anulować fakturę zaliczkową, można utworzyć fakturę korygującą faktury zaliczkowej i zaksięgować ją w księdze głównej.
-   Aby utworzyć fakturę korygującą, można utworzyć nową fakturę zaliczkową, a następnie kliknąć przycisk **Faktura korygująca**. Następnie można zaznaczyć fakturę zaliczkową do anulowania.
-   Można także utworzyć fakturę korygującą dla faktury sprzedaży rozliczającej fakturę zaliczkową.
-   Układ faktur korygujących faktury zaliczkowe zawiera informacje o wierszach przed i po korekcie.
-   (POL) Po zaksięgowaniu faktury korygującej faktury zaliczkowej są tworzone transakcje księgi głównej.

## <a name="cze-tax-documents"></a>(CZE) Dokumenty podatkowe
W Czechach można utworzyć dokument podatkowy oparty na danych przedpłaty w celu dostarczenia należnego podatku VAT. Ze strony przedpłaty można utworzyć, utworzyć i wyświetlić lub utworzyć i wydrukować dokument podatkowy. Kliknij kolejno opcje **Funkcje** &gt; **Dokument podatkowy** i wybierz jedną z opcji. Dokument podatkowy zawiera szczegółowe informacje dotyczące podatku VAT, takie jak typ podatku VAT, wartość oraz jego podstawę w walutach rozliczeniowej i transakcji.

## <a name="set-up-accounts-payable-for-advance-invoices"></a>Konfigurowanie modułu rozrachunków z dostawcami dla faktur zaliczkowych
Na stronie **Parametry modułu rozrachunków z dostawcami** na karcie **Sekwencje identyfikatorów** określ numerację faktur zaliczkowych.

## <a name="create-a-vendor-advance-invoice"></a>Tworzenie faktury zaliczkowej dla dostawcy
Fakturę zaliczkową można utworzyć ręcznie. Alternatywnie nowa faktura zaliczkowa może być oparta na istniejącym zamówieniu zakupu.

## <a name="manually-create-a-vendor-advance-invoice"></a>Ręczne tworzenie faktury zaliczkowej dla dostawcy
Kliknij kolejno opcje **Rozrachunki z dostawcami** &gt; **Wspólne** &gt; **Faktury zaliczkowe** &gt; **Wszystkie faktury zaliczkowe**. Aby utworzyć nową fakturę zaliczkową, w okienku akcji na karcie **Faktura zaliczkowa** kliknij opcję **Faktura zaliczkowa**. Następnie wprowadź wymagane informacje i kliknij przycisk **Księguj** w celu zaksięgowania faktury zaliczkowej. Faktura zaliczkowa może mieć jeden z następujących stanów: **Otwarta**, **Częściowo zapłacono** lub **Zamknięta**. Można ręcznie zmienić stan faktury zaliczkowej, która została zaksięgowana. Kliknij przycisk **Stan**, a następnie na stronie **Zmień stan faktury zaliczkowej** w polu **Nowy stan** wybierz nowy stan faktury zaliczkowej. **Uwaga:** Można zmieniać stan faktury zaliczkowej w dowolnym momencie. Nie można przetwarzać zamkniętych faktur zaliczkowych w transakcjach. **Uwaga:** Specyfikacje podatku VAT są kopiowane do wierszy faktury zaliczkowej tylko wtedy, gdy na stronie **Kody podatków** w polu **Typ podatku** jest ustawiona wartość **Standardowy VAT** lub **Zredukowany VAT**. W przeciwnym razie wiersz jest kopiowany do faktury zaliczkowej, tak jakby kwota podatku VAT wynosiła 0 (zero).

## <a name="link-an-advance-invoice-to-a-purchase-order"></a>Łączenie faktury zaliczkowej z zamówieniem zakupu
Każda faktura zaliczkowa może być połączona tylko z jednym zamówieniem zakupu na raz. Można przepisać istniejącą fakturę zaliczkową do innego zamówienia zakupu, pod warunkiem, że żadne przedpłaty nie są połączone z fakturą zaliczkową. Aby połączyć fakturę zaliczkową z zamówieniem zakupu, na stronie **Wszystkie faktury zaliczkowe** zaznacz fakturę zaliczkową. W okienku akcji kliknij kolejno opcje **Faktura zaliczkowa** i **Zamówienie zakupu**. Następnie zaznacz zamówienie zakupu, które ma zostać połączone z fakturą zaliczkową, i kliknij przycisk **OK**.

## <a name="create-a-vendor-advance-invoice-from-a-purchase-order"></a>Tworzenie faktury zaliczkowej dla dostawcy z zamówienia zakupu
Utwórz zamówienie zakupu lub wybierz istniejące zamówienie zakupu. Kliknij opcję **Faktura**, a następnie kolejno opcje **Generuj** &gt; **Faktura zaliczkowa**. Na stronie **Utwórz fakturę zaliczkową** ustaw następujące pola.

| Pole                                           | opis                                                                                                              |
|-------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Procent                                         | Określ procent przedpłaty dla zamówienia zakupu.                                                         |
| Aktualizacja zakupu                                 | Wybierz spośród dostępnych opcji. Kwota faktury zaliczkowej będzie obliczana na podstawie kwoty zamówienia zakupu dla towarów. |
| Profil księgowania z użyciem załącznika arkusza zaliczki | Określ profil księgowania przedpłaty.                                                                          |







