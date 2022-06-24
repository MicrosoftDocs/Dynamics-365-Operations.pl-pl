---
title: Faktury zaliczkowe dla Europy Wschodniej
description: Ten artykuł zawiera informacje dotyczące faktur zaliczkowych dla Europy Wschodniej. Faktura zaliczkowa jest dokumentem, który można utworzyć dla odbiorcy lub dostawcy. Podaje ona kwotę, która ma zostać opłacona z góry z tytułu zamówienia sprzedaży.
author: EvgenyPopovMBS
ms.date: 05/25/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 272643
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: epopov
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: c722d8215c2b65e24008042c9a4d65bb419ad46a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886291"
---
# <a name="advance-invoices-for-eastern-europe"></a>Faktury zaliczkowe dla Europy Wschodniej

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje dotyczące faktur zaliczkowych dla Europy Wschodniej. Faktura zaliczkowa jest dokumentem, który można utworzyć dla odbiorcy lub dostawcy. Podaje ona kwotę, która ma zostać opłacona z góry z tytułu zamówienia sprzedaży. 

> [!NOTE]
> Inną opcją jest użycie funkcji faktury zaliczkowej. Od wersji Microsoft Dynamics 365 Finance 10.0.28 można używać tej funkcjonalności, przechodząc do pozycji **Rozrachunki z dostawcami** &gt; **Konfiguracja** &gt; **Parametery** &gt; **Księga i podatek** i ustawiając opcję **Używanie faktury przedpłaty** na skróconej karce **Faktura zaliczkowa** na **Tak**. Aby uzyskać więcej informacji, zobacz [Faktury zaliczkowe a przedpłaty](../accounts-payable/prepayments-invoices-vs-prepayments.md).

Funkcjonalność faktur zaliczkowych umożliwia wykonywanie następujących zadań:

- Wystawianie faktur zaliczkowych odbiorcom i śledzenie stanu tych faktur (**Otwarte**, **Częściowo zapłacone** lub **Zamknięte**).
- *Dotyczy tylko Polski:* księgowanie transakcji faktur zaliczkowych i transakcji podatku od wartości dodanej (VAT).
- Automatyczne generowanie wierszy arkusza płatności na podstawie faktury zaliczkowej.
- Łączenie przedpłat otrzymywanych od odbiorców z fakturami zaliczkowymi (przed lub po zaksięgowaniu przedpłaty).
- Zmiana księgowania podatku VAT w zaksięgowanych przedpłatach (czyli konwertowanie przedpłaty na płatność lub płatności na przedpłatę albo zmiana daty księgowania, stawka podatku lub kwoty).
- *Dotyczy tylko Republiki Czeskiej*: tworzenie dokumentu podatkowego w celu dostarczenia należnego podatku VAT.

## <a name="advance-invoices-for-poland"></a>Faktury zaliczkowe dla Polski

Polskie firmy otrzymujące przedpłatę muszą utworzyć fakturę na przedpłatę dla odbiorcy. Ta faktura zaliczkowa jest księgowana w księdze głównej i jest dokumentem obowiązkowym do rozliczania podatku VAT. Podatek obliczony w fakturze zaliczkowej należy zgłosić do urzędu skarbowego.

Podczas ostatecznej sprzedaży towarów faktura zaliczkowa musi być podana w fakturze sprzedaży. Łączna kwota sprzedaży musi zawierać przedpłaty.

Podczas księgowania faktury sprzedaży rozliczona faktura zaliczkowa jest wycofywana. Oryginalna faktura zaliczkowa zostanie jest rozliczana za pomocą wycofania faktury zaliczkowej.

## <a name="set-up-accounts-receivable-for-advance-invoices"></a>Konfigurowanie modułu rozrachunków z odbiorcami dla faktur zaliczkowych

1. Na stronie **Parametry modułu rozrachunków z odbiorcami**, na karcie **Aktualizacje**, na skróconej karcie **Faktura zaliczkowa** ustaw następujące pola.

    | Pole | Opis |
    |-------|-------------|
    | Profil księgowania | <p>*Dotyczy tylko Polski:* wybierz profil księgowania, który ma być używany do fakturowania zaliczek.</p><p>**Ważne:** W Czechach i na Węgrzech faktury zaliczkowe nie są traktowane jako dokumenty księgowe ani podatkowe i nie są księgowane w księdze głównej. W związku z tym dla tych krajów należy pozostawić to pole puste, aby uniemożliwić księgowanie faktur zaliczkowych w księdze głównej.</p> |
    | Konto przeciwstawne | Wybierz konto przeciwstawne. |
    | Grupa podatków | Umożliwia wybór grupy podatków używanej podczas obliczania podatku w fakturowaniu zaliczek. |
    | Wycofanie jako korekta | Zaznacz to pole wyboru, jeśli wycofanie faktury zaliczkowej powinno być uznawane za korektę. |
    | Wycofaj w dniu określonym datą faktury | Zaznacz to pole wyboru, aby cofnąć przedpłatę w dniu zaksięgowania faktury. |

1. Na skróconej karcie **Płatność** ustaw następujące pola.

    | Pole | Opis |
    |-------|-------------|
    | Wiele dat przedpłaty | Wybierz pozycję **Zaakceptuj**, **Ostrzeżenie** lub **Błąd**. |
    | Niezgodność dat | Wybierz pozycję **Zaakceptuj**, **Ostrzeżenie** lub **Błąd**. |
    | Niezgodność kwot | Wybierz pozycję **Zaakceptuj**, **Ostrzeżenie** lub **Błąd**. |
    | Łączenie z zaksięgowaną fakturą zaliczkową | Wybierz pozycję **Zaakceptuj**, **Ostrzeżenie** lub **Błąd**. |
    | (CZE), (POL) Obsługa przedpłat | Wybierz opcję **Zaawansowane**. |

1. Na karcie **Sekwencje identyfikatorów** skonfiguruj numeracje dla następujących odwołań:

    - Dokument podatkowy
    - Memorandum kredytowe dla podatku
    - Faktura zaliczkowa
    - Faktura korygująca do faktury zaliczkowej
    - Wycofanie faktury zaliczkowej
    - Załącznik faktury zaliczkowej
    - Załącznik faktury korygującej do faktury zaliczkowej
    - Załącznik do wycofania faktury zaliczkowej

## <a name="create-a-customer-advance-invoice"></a>Tworzenie faktury płatności zaliczkowej dla odbiorcy

1. Przejdź kolejno do opcji **Rozrachunki z odbiorcami** &gt; **Wspólne** &gt; **Faktury zaliczkowe** &gt; **Wszystkie faktury zaliczkowe**.
1. W okienku akcji na karcie **Faktura zaliczkowa** wybierz opcję **Faktura zaliczkowa**, aby utworzyć nową fakturę zaliczkową.
1. Wprowadź wymagane informacje, a następnie wybierz pozycję **Księguj** w celu zaksięgowania faktury zaliczkowej.

Faktura zaliczkowa może mieć jeden z następujących stanów: **Otwarta**, **Częściowo zapłacono** lub **Zamknięta**. Można ręcznie zmienić stan faktury zaliczkowej, która została zaksięgowana. Wybierz przycisk **Stan**, a następnie na stronie **Zmień stan faktury zaliczkowej** w polu **Nowy stan** wybierz nowy stan faktury zaliczkowej.

> [!NOTE]
> Można zmieniać stan faktury zaliczkowej w dowolnym momencie. Nie można przetwarzać zamkniętych faktur zaliczkowych w transakcjach.
> 
> *Dotyczy tylko Polski:* Transakcje faktur zaliczkowych są generowane, jeśli skonfigurowano profil księgowania dla faktur zaliczkowych na stronie Parametry modułu rozrachunków z odbiorcami. Aby wyświetlić transakcje, które zostały zaksięgowane, wybierz opcję **Załącznik** na stronie **Faktura zaliczkowa**.

## <a name="vat-on-advance-invoices"></a>VAT na fakturach zaliczkowych

Firmy muszą rejestrować podatek VAT w przedpłatach wnoszonych przez odbiorców, nawet jeśli sprzedaż nie została zakończona. Aby zaksięgować podatek VAT z przedpłaty, można do faktury zaliczkowej dodać wiersz zawierający specyfikacje podatku VAT. Faktura zaliczkowa może zawierać kilka wierszy, a wiersze te mogą zawierać specyfikacje podatku VAT pobierane z wierszy zamówienia sprzedaży. W związku z tym można zaksięgować podatek VAT od przedpłaty w ścisłej zgodności z wierszami zamówienia sprzedaży.

> [!NOTE]
> Specyfikacje podatku VAT są kopiowane do wierszy faktury zaliczkowej tylko wtedy, gdy w polu **Typ podatku** na stronie **Kody podatków** jest ustawiona wartość **Standardowy VAT** lub **Zredukowany VAT**. W przeciwnym razie następuje kopiowanie do wierszy faktury zaliczkowej, tak jakby kwota podatku VAT wynosiła 0 (zero).

## <a name="link-an-advance-invoice-to-a-sales-order-or-a-free-text-invoice"></a>Łączenie faktury zaliczkowej z zamówieniem sprzedaży lub fakturą niezależną

Każda faktura zaliczkowa może być połączona tylko z jednym zamówieniem sprzedaży lub fakturą niezależną jednocześnie. Można przepisać istniejącą fakturę zaliczkową do innego zamówienia sprzedaży lub faktury niezależnej, pod warunkiem, że żadne przedpłaty nie są połączone z fakturą zaliczkową.

Aby połączyć fakturę zaliczkową z zamówieniem sprzedaży, wykonaj następujące czynności.

1. Na stronie **Wszystkie faktury zaliczkowe** wybierz fakturę zaliczkową.
1. W okienku akcji wybierz kolejno opcje **Faktura zaliczkowa** i **Zamówienie sprzedaży**.
1. Wybierz zamówienie sprzedaży, które ma zostać połączone z fakturą zaliczkową, a następnie wybierz przycisk **OK**.

Aby połączyć fakturę zaliczkową z fakturą niezależną, wykonaj następujące czynności.

1. Na stronie **Wszystkie faktury zaliczkowe** wybierz fakturę zaliczkową.
1. W okienku akcji wybierz kolejno opcje **Faktura zaliczkowa** i **Faktura niezależna**.
1. Wybierz fakturę niezależną, która ma zostać połączona z fakturą zaliczkową, a następnie wybierz przycisk **OK**.

## <a name="create-a-customer-advance-invoice-from-a-sales-order"></a>Utwórz faktury zaliczkowej dla odbiorcy na podstawie zamówienia sprzedaży

1. Utwórz zamówienie sprzedaży lub wybierz istniejące zamówienie sprzedaży.
1. Wybierz opcję **Faktura**, a następnie wybierz opcje **Generuj** &gt; **Faktura zaliczkowa**.
1. Na stronie **Utwórz fakturę zaliczkową** ustaw poniższe pola.

    | Pole | Opis |
    |-------|-------------|
    | Procent | Określ procent przedpłaty dla zamówienia sprzedaży. |
    | Konto przeciwstawne | Umożliwia wybór domyślnego konta przeciwstawnego, które ma być używane na potrzeby fakturowania zaliczek. |
    | Aktualizuj zamówienie | Wybierz opcję **Wszystko**, **Dostawa teraz**, **Pobrane**, **Dokument dostawy** lub **Ilość pobrana i produkty niemagazynowane**. Kwota faktury zaliczkowej będzie obliczana na podstawie kwot zamówień sprzedaży dla danych pozycji. |
    | Księguj podatek VAT | Określ, czy podczas księgowania faktur zaliczkowych ma być księgowany podatek VAT. |
    | Data księgowania podatku VAT | Wskaż datę księgowania podatku VAT. |
    | Profil księgowania z użyciem załącznika arkusza zaliczki | Określ profil księgowania przedpłaty. |
    | Utwórz dokument podatku | Określ, czy należy utworzyć dokument podatkowe. |

> [!NOTE]
> *Dotyczy tylko Polski:* Transakcje faktur zaliczkowych są generowane, jeśli skonfigurowano profil księgowania dla faktur zaliczkowych na stronie Parametry modułu rozrachunków z odbiorcami.

## <a name="create-a-customer-advance-invoice-from-a-free-text-invoice"></a>Tworzenie faktury płatności zaliczkowej odbiorcy na podstawie faktury niezależnej

1. Utwórz fakturę niezależną lub wybierz istniejącą fakturę niezależną.
1. Na karcie **Faktura** w sekcji **Nowy** wybierz opcję **Faktura zaliczkowa**.

    Teraz możesz utworzyć nową fakturę zaliczkową, która zostanie połączona z fakturą niezależną.

> [!NOTE]
> *Dotyczy tylko Polski:* Transakcje faktur zaliczkowych są generowane, jeśli skonfigurowano profil księgowania dla faktur zaliczkowych na stronie Parametry modułu rozrachunków z odbiorcami.

## <a name="print-an-advance-invoice"></a>Drukowanie faktury zaliczkowej

- Na stronie **Faktura zaliczkowa** wybierz pozycję **Drukuj**. 

*Dotyczy tylko Polski:* można wydrukować dokument fiskalny faktury zaliczkowej. Wybierz opcję podczas księgowania faktury zaliczkowej.

*Dotyczy tylko Polski:* układy dokumentów faktury sprzedaży i faktury niezależnej powinny zawierać następujące informacje dotyczące rozliczanej faktury zaliczkowej:

- Numer faktury zaliczkowej
- Data faktury zaliczkowej
- Kwota bez podatku VAT, kwota podatku VAT, kwota z podatkiem VAT i waluta
- Procent podatku

Podsumowanie kwot podatku VAT powinno zawierać pole **Podatek z faktury zaliczkowej**. Kwota należna powinna być pomniejszona o kwotę faktury zaliczkowej.

## <a name="create-a-payment-proposal-from-an-advance-invoice"></a>Tworzenie propozycji płatności na podstawie faktury zaliczkowej

Podczas tworzenia nowego arkusza płatności można automatycznie generować wiersze arkusza płatności na podstawie faktury zaliczkowej.

1. Na stronie **Arkusz płatności** wybierz kolejno pozycje **Załącznik arkusza zaliczki**, a następnie wybierz pozycję **Wiersze**.
1. Na stronie **Załącznik arkusza** wybierz kolejno opcje **Propozycja płatności** &gt; **Propozycja płatności z faktury zaliczkowej**, aby utworzyć propozycję płatności na podstawie faktur zaliczkowych. Informacje takie jak profil księgowania i grupy podatków zostaną pobrane z faktury zaliczkowej.

> [!NOTE]
> Nowe przedpłaty będą automatycznie łączone z fakturami zaliczkowymi, jeśli na stronie **Tworzenie propozycji płatności na podstawie faktur zaliczkowych** zaznaczono opcje **Połącz przedpłaty** i **Zmień stan**.

## <a name="link-a-prepayment-to-an-advance-invoice"></a>Połącz przedpłaty z fakturą zaliczkową

Aby połączyć przedpłatę z fakturą zaliczkową z arkusza płatności, wykonaj następujące kroki.

- Otwórz arkusz płatności, zaznacz wiersz zawierający przedpłatę, a następnie wybierz kolejno opcje **Funkcje** &gt; **Połącz z fakturami zaliczkowymi**.

Aby połączyć przedpłatę z fakturą zaliczkową ze strony **Transakcje klienta**, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Wszyscy klienci** &gt; **Klienci** &gt; **Transakcje**.
1. Zaznacz arkusz płatności, zaznacz wiersz zawierający przedpłatę, a następnie wybierz kolejno opcje **Funkcje** &gt; **Połącz z fakturami zaliczkowymi**.

## <a name="link-an-advance-invoice-to-a-prepayment"></a>Łączenie faktury zaliczkowej z przedpłatą

Aby połączyć fakturę zaliczkową z wierszem przedpłaty, wykonaj następujące czynności.

1. Na stronie **Wszystkie faktury zaliczkowe** wybierz fakturę zaliczkową.
1. W okienku akcji wybierz kolejno opcje **Faktura zaliczkowa** i **Przedpłata**.
1. Wybierz wiersz przedpłaty, który ma zostać połączony z fakturą zaliczkową, i wybierz przycisk **OK**.

## <a name="advance-invoice-credit-notes"></a>Faktury korygujące do faktury zaliczkowej

- *Dotyczy tylko Polski:* aby anulować fakturę zaliczkową, można utworzyć fakturę korygującą faktury zaliczkowej i zaksięgować ją w księdze głównej.
- Aby utworzyć fakturę korygującą, można utworzyć nową fakturę zaliczkową, a następnie wybrać opcję **Faktura korygująca**. Następnie można zaznaczyć fakturę zaliczkową do anulowania.
- Można także utworzyć fakturę korygującą dla faktury sprzedaży rozliczającej fakturę zaliczkową.
- Układ faktur korygujących faktury zaliczkowe zawiera informacje o wierszach przed i po korekcie.
- *Dotyczy tylko Polski:* po zaksięgowaniu faktury korygującej faktury zaliczkowej są tworzone transakcje księgi głównej.

## <a name="tax-documents-for-the-czech-republic"></a>Dokumenty podatkowe — Republika Czeska

W Czechach można utworzyć dokument podatkowy oparty na danych przedpłaty w celu dostarczenia należnego podatku VAT. Dokument podatkowy można utworzyć, utworzyć i wyświetlić albo utworzyć i wydrukować ze strony przedpłaty, wybierając pozycje **Funkcje** &gt; **Dokument podatkowy**, a następnie wybierając jedną z opcji. Dokument podatkowy zawiera szczegółowe informacje dotyczące podatku VAT, takie jak typ podatku VAT, wartość oraz jego podstawę w walutach rozliczeniowej i transakcji.

## <a name="set-up-accounts-payable-for-advance-invoices"></a>Konfigurowanie modułu rozrachunków z dostawcami dla faktur zaliczkowych

- Na stronie **Parametry modułu rozrachunków z dostawcami** na karcie **Sekwencje identyfikatorów** określ numerację faktur zaliczkowych.

## <a name="create-a-vendor-advance-invoice"></a>Tworzenie faktury zaliczkowej dla dostawcy

Fakturę zaliczkową można utworzyć ręcznie. Alternatywnie nowa faktura zaliczkowa może być oparta na istniejącym zamówieniu zakupu.

### <a name="manually-create-a-vendor-advance-invoice"></a>Ręczne tworzenie faktury zaliczkowej dla dostawcy

1. Przejdź kolejno do opcji **Rozrachunki z dostawcami** &gt; **Wspólne** &gt; **Faktury zaliczkowe** &gt; **Wszystkie faktury zaliczkowe**.
1. W okienku akcji na karcie **Faktura zaliczkowa** wybierz opcję **Faktura zaliczkowa**, aby utworzyć nową fakturę zaliczkową.
1. Wprowadź wymagane informacje, a następnie wybierz pozycję **Księguj** w celu zaksięgowania faktury zaliczkowej.

Faktura zaliczkowa może mieć jeden z następujących stanów: **Otwarta**, **Częściowo zapłacono** lub **Zamknięta**. Można ręcznie zmienić stan faktury zaliczkowej, która została zaksięgowana. Wybierz przycisk **Stan**, a następnie na stronie **Zmień stan faktury zaliczkowej** w polu **Nowy stan** wybierz nowy stan faktury zaliczkowej.

> [!NOTE]
> Można zmieniać stan faktury zaliczkowej w dowolnym momencie. Nie można przetwarzać zamkniętych faktur zaliczkowych w transakcjach.
>
> Specyfikacje podatku VAT są kopiowane do wierszy faktury zaliczkowej tylko wtedy, gdy w polu **Typ podatku** na stronie **Kody podatków** jest ustawiona wartość **Standardowy VAT** lub **Zredukowany VAT**. W przeciwnym razie następuje kopiowanie do wierszy faktury zaliczkowej, tak jakby kwota podatku VAT wynosiła 0 (zero).

### <a name="link-an-advance-invoice-to-a-purchase-order"></a>Łączenie faktury zaliczkowej z zamówieniem zakupu

Każdą fakturę zaliczkową można połączyć tylko z jednym zamówieniem zakupu na raz. Można przepisać istniejącą fakturę zaliczkową do innego zamówienia zakupu, pod warunkiem, że żadne przedpłaty nie są połączone z fakturą zaliczkową.

Aby połączyć fakturę zaliczkową z zamówieniem zakupu, wykonaj następujące czynności.

1. Na stronie **Wszystkie faktury zaliczkowe** wybierz fakturę zaliczkową.
1. W okienku akcji wybierz kolejno opcje **Faktura zaliczkowa** i **Zamówienie zakupu**.
1. Wybierz zamówienie zakupu, które ma zostać połączone z fakturą zaliczkową, a następnie wybierz przycisk **OK**.

### <a name="create-a-vendor-advance-invoice-from-a-purchase-order"></a>Tworzenie faktury zaliczkowej dla dostawcy z zamówienia zakupu

1. Utwórz zamówienie zakupu lub wybierz istniejące zamówienie zakupu.
1. Wybierz opcję **Faktura**, a następnie wybierz opcje **Generuj** &gt; **Faktura zaliczkowa**.
1. Na stronie **Utwórz fakturę zaliczkową** ustaw poniższe pola.

    | Pole | Opis |
    |-------|-------------|
    | Procent | Określ procent przedpłaty dla zamówienia zakupu. |
    | Aktualizacja zakupu | Wybierz opcję. Kwota faktury zaliczkowej będzie obliczana na podstawie kwoty zamówienia zakupu dla danych pozycji. |
    | Profil księgowania z użyciem załącznika arkusza zaliczki | Określ profil księgowania przedpłaty. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
