---
title: Faktury zaliczkowe a zaliczki
description: Ten temat zawiera opis i porównanie dwóch metod, których organizacje używają do obsługi zaliczek (przedpłat).
author: abruer
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, PurchTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15871
ms.assetid: a0bb5220-73d4-48ae-84d0-46a171c224fa
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 64301ac540ce2e6e914b6b23668fddeb295ef84c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827993"
---
# <a name="prepayment-invoices-vs-prepayments"></a>Faktury zaliczkowe a zaliczki

[!include [banner](../includes/banner.md)]

Ten temat zawiera opis i porównanie dwóch metod, których organizacje używają do obsługi zaliczek (przedpłat). W jednej metodzie należy utworzyć fakturę zaliczkową skojarzoną z zamówieniem zakupu. W drugiej metodzie tworzy się załączniki arkusza zaliczki poprzez utworzenie zapisów w arkuszu i oznaczenie ich jako załączników arkusza zaliczki.

Organizacje mogą wystawiać zaliczki (płatności z góry) dla dostawców za towary lub usługi, które nie zostały jeszcze dostarczone lub zrealizowane. Dostępne są dwa sposoby wystawiania zaliczek dla dostawców. Aby zminimalizować ryzyko, można śledzić zaliczki, definiując zaliczkę na zamówieniu zakupu. Dla tej metody należy utworzyć fakturę zaliczkową skojarzoną z zamówieniem zakupu. Ta metoda jest nazywana fakturowaniem zaliczki. Organizacje, które nie chcą muszą śledzić zaliczek z taką dokładnością lub nie otrzymują faktury zaliczkowej od dostawcy, mogą zamiast metody fakturowania zaliczki używać załączników arkusza zaliczki. Załączniki arkusza zaliczki można tworzyć przez tworzenie wpisów w arkuszu i oznaczanie ich jako załączników arkusza zaliczki. Dla tej metody nie można śledzić, które zaliczki dla dostawcy odpowiadają którym zamówieniom zakupu. Można jednak można oznaczyć zaksięgowaną zaliczkę do rozliczenia według zamówienia zakupu.

## <a name="when-to-use-prepayment-invoicing-vs-prepayments"></a>Kiedy używać faktur zaliczkowych, a kiedy używać zaliczek

| Faktury zaliczkowe                                                                | Zaliczki                                                              |
|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Definiowanie wartości przedpłaty na zamówieniu zakupu.                                    | Na zamówieniu zakupu nie są definiowane żadne wartości przedpłaty.                    |
| Faktura zaliczkowa i końcowa muszą być zaksięgowane.                       | Zaliczki nie muszą być księgowane.                                    |
| Odpowiedzialność za zaliczkę ponosi konto przedpłaty, na konto rozrachunków z dostawcami. | Odpowiedzialność za zaliczkę ponosi konto rozrachunków z dostawcami.                  |
| Saldo dostawcy nie odzwierciedla wartości zaliczki w całym procesie.     | Saldo dostawcy odzwierciedla wartość zaliczki w całym procesie. |
| Faktury zaliczkowe są dostępne tylko w rozrachunkach z dostawcami.                         | Zaliczki są dostępne w rozrachunkach z odbiorcami i dostawcami.    |

## <a name="overview-of-the-prepayment-process"></a>Omówienie procesu zaliczki
Zasady księgowości stosowane w niektórych krajach/regionach wymagają, aby zaliczki od odbiorcy lub dla dostawcy nie były księgowane na zwykłych kontach rozrachunkowych używanych w rozliczeniach z danym odbiorcą lub dostawcą. Przedpłaty mają być zamiast tego księgowane na specjalnych kontach księgowych wyznaczonych do tego celu. W momencie złożenia zamówienia zakupu lub zamówienia sprzedaży jest wystawiana faktura dla odbiorcy lub dostawcy. Dokonanie płatności faktury powoduje wycofanie zaliczki i załącznika zaliczki na podatek z kont księgowych przeznaczonych na zaliczki oraz automatyczne zaksięgowanie kwot faktury na zwykłych kontach rozrachunkowych. Aby utworzyć zaliczkę, należy wykonać następujące kroki.

1.  Ustaw profile księgowania dla zaliczek.
2.  W parametrach rozrachunków z odbiorcami i rozrachunków z dostawcami w obszarze **Księga i podatek** wybierz nowy profil księgowania za pomocą parametru **Profil księgowania dla arkusza płatności z przedpłatą**.
3.  Utwórz arkusz płatności, a następnie utwórz nową płatność.
4.  Można oznaczać flagami płatność jako zaliczkę. Jeśli płatność jest oznaczona jako zaliczka, płatność jest księgowana na kontach księgowych zdefiniowanych w profilu księgowania ustawionym w krokach 1 i 2. Ponadto jeśli płatność jest oznaczona jako zaliczka, obliczane są podatki. W niektórych krajach podatki muszą być płacone w chwili rejestracji zaliczki, nawet jeśli nie ma jeszcze faktury.
5.  Zaksięguj przedpłatę.
6.  Opcjonalnie: Można rozliczyć zaliczkę dla zamówienia zakupu lub zamówienia sprzedaży przed utworzeniem faktury. Na stronie zamówienia sprzedaży lub zamówienia zakupu, w okienku akcji, użyj opcji **Rozlicz transakcje**.
7.  Po tym jak dostawca dostarczy towary lub zrealizuje usługi zarejestruj fakturę. Jeśli w kroku 6 zaliczka została rozliczona dla zamówienia zakupu lub zamówienia sprzedaży, zaliczka jest automatycznie rozliczana dla utworzonej faktury. Jeśli zaliczka nie została rozliczona dla zamówienia zakupu lub zamówienia sprzedaży, można ręcznie rozliczyć ją dla faktury za pomocą opcji **Rozlicz transakcje** na stronie odbiorcy lub dostawcy. Kwota zaliczki jest następnie wycofywana z tymczasowego konta księgowego rozrachunków z dostawcami/rozrachunków z odbiorcami. Ponadto, jeśli zostały obliczone podatki, są one wycofywane, bo faktura zawiera rzeczywiste podatki.

## <a name="overview-of-the-prepayment-invoicing-process"></a>Omówienie procesu fakturowania zaliczek
Faktury zaliczkowe są często stosowaną praktyką biznesową. Dostawca wystawia fakturę zaliczkową, by otrzymać wpłatę za zakup przed zrealizowaniem zamówienia zakupu. Na przykład niektórzy dostawcy wymagają zaliczki za niestandardowe towary lub usługi. Jeśli dostawca wystawia fakturę z prośbą o zaliczkę, można użyć funkcji fakturowania zaliczki. Wartość zaliczki można zdefiniować w zamówieniu zakupu, faktura zaliczkowa jest rejestrowana i płacona, a następnie faktura zaliczkowa jest stosowana na fakturze końcowej. Aby utworzyć zaliczkę, należy wykonać następujące kroki.

1.  Pracownik działu zakupów tworzy, potwierdza, a następnie przesyła dostawcy zamówienie zakupu, dla którego dostawca żądał zaliczki. Wartość przedpłaty jest zdefiniowana na zamówieniu zakupu w ramach umowy.
2.  Dostawca przesyła fakturę zaliczkową.
3.  Koordynator rozrachunków z dostawcami rejestruje fakturę zaliczkową dla zamówienia zakupu, a następnie faktura zaliczkowa jest płacona.
4.  Dostawca wysyła żądanie płatności, zwane standardową fakturą od dostawcy. Po tym jak dostawca dostarczy towary lub usługi i otrzymane standardowej faktury od dostawcy zostaną otrzymane, koordynator rozrachunków z dostawcami stosuje kwotę płatności, która została już zapłacona w odniesieniu do standardowej faktury.
5.  Koordynator rozrachunków z dostawcami płaci i rozlicza pozostałą kwotę standardowej faktury.

## <a name="set-up-parameters-to-enable-the-prepayment-invoicing-process"></a>Konfigurowanie parametrów w celu włączenia procesu fakturowania przedpłat
Konto przedpłaty musi być zdefiniowane na karcie **Zamówienie zakupu** na stronie **Księgowania zapasów** (**Księgowanie konfiguracji \> Ustawienia  \> Księgowanie \> Księgowanie**). Po zaksięgowaniu faktury zaliczkowej konto przedpłaty (zwykle obciążane) zostanie zaktualizowane. Saldo na koncie przedpłaty zostanie wycofane, gdy zostanie zaksięgowana standardowa faktura zastosowana do faktury zaliczkowej. Jeśli faktura zaliczkowa nie zostanie rozliowana przed zastosowaniem faktury zaliczkowej do standardowej faktury, wpisy księgowe z zaksięgowanej faktury zaliczkowej zostaną wycofane po zaksięgowaniu faktury standardowej.

Przeciwstawne konto rozrachunkowe rozrachunków z dostawcami jest zdefiniowane w profilu **księgowania dostawcy**. Aby zdefiniować domyślny profil księgowania, kliknij opcję **Rozrachunki z odbiorcami \> ustawienia \> parametry rozrachunków z odbiorcami \> karta Księga i podatek \> Księgowanie profili z wcześniej opłaconą fakurą dostawcy**.

**Zasady stosowania przedpłat** wskazuje, czy system automatycznie zastosuje rozliczone faktury zaliczkowe do ostatecznej faktury utworzonej ręcznie. Faktury tworzone przy użyciu jednostki danych nie będą się odwoływać do zasad **stosowania przedpłat**. Należy ręcznie zastosować rozliczone faktury zaliczkowe do faktur utworzonych przy użyciu jednostki danych. Aby zdefiniować zasady, przejdź do **Rozrachunki z dostawcami \>Ustawienia \> Parametry rozrachunków z dostawcami \> Karta księgi i podatku \> ZAsady stosowania przedpłaty**. Jeśli w polu **Zasady rozliczania przedpłaty** została ustawiona wartość **Automatycznie**, faktura zaliczkowa zostanie automatycznie zaznaczona do rozliczenia z fakturą końcową. Jeśli to pole jest ustawione na **Powiadomienie**, podczas tworzenia faktury końcowej jest wyświetlana graficzna informacja o tym, że faktura zaliczkowa jest dostępna w aplikacji.

## <a name="create-a-purchase-order-that-contains-prepayment-invoice-information"></a>Tworzenie zamówienia zakupu zawierającego informacje o fakturze zaliczkowej
Jeśli dostawca informuje Użytkownika, że wymaga przedpłaty za towary i usługi zawarte w zamówieniu zakupu, należy zdefiniować wartość przedpłaty dla skojarzonego zamówienia zakupu. Przejdź do **Rozrachunki z dostawcami \> Wspólne \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**, a następnie znajdź zamówienie zakupu dostawcy. W okienku akcji wybierz kartę **Zakup** i wybierz opcję **Zapłata**. Służy do wprowadzania informacji o zaliczce, w tym opisu, wartości przedpłaty, czy przedpłata to kwota stała czy procent oraz identyfikator kategorii przedpłaty. 

Należy zauważyć, że definicje wielu przedpłat na zamówieniu zakupu są niedozwolone. Jeśli jest konieczne zezwalanie na wiele przedpłat na zamówieniu zakupu, księguj płatności za pomocą arkusza płatności zamiast faktury zaliczkowej.

Przedpłatę można usunąć z zamówienia zakupu, chyba że wcześniej rozliczona została płatność z zaksięgowaną fakturą zaliczkową lub zaksięgowano standardową fakturę. Aby usunąć z zamówienia zakupu informacje o przedpłatze, wybierz opcję **Rozrachunki z dostawcami \> Wspólne \> Zamówienia zakupu \> wszystkie zamówienia zakupu** i znajdź zamówienie zakupu dostawcy. W okienku akcji wybierz kartę **Zakup** i wybierz opcję **Usuń przedpłatę**.

## <a name="create-and-post-a-prepayment-invoice"></a>Tworzenie i księgowanie faktury przedpłaty
Aby zarejestrować fakturę zaliczkową dostawcy, przejdź na stronę **Faktura od dostawcy**, zaznaczając opcję **Faktura zaliczkowa** na stronie **Zamówienia zakupu** (**Rozrachunki z dostawcami \> Wspólne \> Zamówienia zakupu \> Wszystkie zamówienia zakupu \> karta Faktury \> Faktura przedpłaty**). Wprowadź informacje dotyczące faktury przedpłaty, w tym numer faktury. Nie można zmienić ilości dla faktury zaliczkowej. Jeśli dostawca zafakturował częściową kwotę wartości przedpłaty zdefiniowanej w zamówieniu zakupu, można zaktualizować cenę jednostkową, tak aby odzwierciedlała wartość częściową.

Po zaksięgowaniu faktury przedpłaty saldo dostawcy i konto przedpłaty zostaną zaktualizowane. Zostanie także zaktualizowana wartość **Zastosowania przedpłaty** w definicji przedpłaty zawartej w zamówieniu zakupu. Domyślne wpisy wymiaru finansowego dla zaksięgowanego załącznika przedpłaty będą pochodziły z informacji nagłówka zamówienia zakupu.

## <a name="post-and-settle-payments-for-the-prepayment-invoice"></a>Księgowanie i rozliczanie płatności dla faktury zaliczkowej
Następnie faktura zaliczkowa zostanie zapłacona ze strony **Arkusza płatności**. Aby uzyskać dostęp do arkuszy płatności, kliknij **Rozrachunki z dostawcami \> Arkusze \> Płatności \> Arkusz płatności**. Po zaksięgowaniu rozliczenia płatności na fakturze zaliczkowej zostanie zaktualizowana **Pozostała wartość zastosowania przedpłaty** zamówienia zakupu.

Przed zaksięgowaniem standardowej faktury dla faktury zaliczkowej można wycofać rozliczenie płatności z faktury zaliczkowej. Jednak po zastosowaniu faktury standardowej do faktury przedpłaty nie można cofnąć rozliczenia płatności z faktury przedpłaty.

## <a name="post-the-standard-vendor-invoice-for-the-purchase-order-and-apply-the-prepayment-invoice-to-the-standard-invoice"></a>Księguj standardową fakturę od dostawcy dla zamówienia zakupu i zastosuj fakturę zaliczkową do standardowej faktury
Zarejestrować standardową fakturę otrzymaną od dostawcy. W ramach tego procesu można zastosować rozliczoną fakturę zaliczkową do faktury dostawcy, dzięki czemu wartość faktury zostanie zmniejszona o już zapłaconą kwotę. Zastosowanie faktury zaliczkowej do faktury od dostawcy zapewnia wycofanie zapisów księgowych z faktury zaliczkowej.

## <a name="application-of-the-prepayment-invoice-after-posting-the-standard-invoice"></a>Zastosowanie faktury zaliczkowej po zaksięgowaniu faktury standardowej
W razie zapomnienia zastosowania przedpłaty do standardowej faktury od dostawcy w momencie księgowania faktury dostawcy, rozliczona przedpłata będzie dostępna do zastosowania do innych faktur od tego dostawcy ze strony **Dostawcy** (**Rozrachunki z dostawcami \> Wspólne \> Dostawcy \> Wszyscy dostawcy \> Karta Faktury \> Zastosuj**).

## <a name="reversal-of-the-prepayment-application-process"></a>Wycofanie procesu zgłoszenia przedpłaty
Jeśli musisz cofnąć rozliczenia lub wycofać zastosowanie faktury zaliczkowej z faktury standardowej, wybierz akcję **Wycofaj** ze strony **Dostawcy** (**Rozrachunki z dostawcami \> Wspólne \> Dostawcy \> Wszyscy dostawcy \> Karta Faktury \> Wycofaj**). Po wycofaniu zgłoszenia przedpłaty można zastosować przedpłatę do innej standardowej faktury. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]