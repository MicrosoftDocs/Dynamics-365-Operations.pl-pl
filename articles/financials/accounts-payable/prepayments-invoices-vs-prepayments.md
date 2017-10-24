---
title: Faktury zaliczkowe i zaliczki
description: "Ten artykuł zawiera opis i porównanie dwóch metod, których organizacje używają do obsługi zaliczek (przedpłat). W jednej metodzie należy utworzyć fakturę zaliczkową skojarzoną z zamówieniem zakupu. W drugiej metodzie tworzy się załączniki arkusza zaliczki poprzez utworzenie zapisów w arkuszu i oznaczenie ich jako załączników arkusza zaliczki."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, PurchTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15871
ms.assetid: a0bb5220-73d4-48ae-84d0-46a171c224fa
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e6bf67fb17363f7b61e782ed6d8e7b6310433ffd
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="prepayment-invoices-vs-prepayments"></a>Faktury zaliczkowe i zaliczki

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera opis i porównanie dwóch metod, których organizacje używają do obsługi zaliczek (przedpłat). W jednej metodzie należy utworzyć fakturę zaliczkową skojarzoną z zamówieniem zakupu. W drugiej metodzie tworzy się załączniki arkusza zaliczki poprzez utworzenie zapisów w arkuszu i oznaczenie ich jako załączników arkusza zaliczki.

Organizacje mogą wystawiać zaliczki (płatności z góry) dla dostawców za towary lub usługi, które nie zostały jeszcze dostarczone lub zrealizowane. Dostępne są dwa sposoby wystawiania zaliczek dla dostawców. Aby zminimalizować ryzyko, można śledzić zaliczki, definiując zaliczkę na zamówieniu zakupu. Dla tej metody należy utworzyć fakturę zaliczkową skojarzoną z zamówieniem zakupu. Ta metoda jest nazywana fakturowaniem zaliczki. Organizacje, które nie chcą muszą śledzić zaliczek z taką dokładnością lub nie otrzymują faktury zaliczkowej od dostawcy, mogą zamiast metody fakturowania zaliczki używać załączników arkusza zaliczki. Załączniki arkusza zaliczki można tworzyć przez tworzenie wpisów w arkuszu i oznaczanie ich jako załączników arkusza zaliczki. Dla tej metody nie można śledzić, które zaliczki dla dostawcy odpowiadają którym zamówieniom zakupu. Można jednak można oznaczyć zaksięgowaną zaliczkę do rozliczenia według zamówienia zakupu.

## <a name="when-to-use-prepayment-invoicing-vs-prepayments"></a>Kiedy używać faktur zaliczkowych, a kiedy używać zaliczek
| Faktury zaliczkowe                                                                | Zaliczki                                                              |
|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Definiowanie wartości przedpłaty na zamówieniu zakupu.                                    | Na zamówieniu zakupu nie są definiowane żadne wartości przedpłaty.                    |
| Klucz: faktura zaliczkowa i końcowa muszą być zaksięgowane.                       | Zaliczki nie muszą być księgowane.                                    |
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
4.  Po tym jak dostawca dostarczy towary lub usługi i otrzymane faktury od dostawcy zostaną otrzymane, koordynator rozrachunków z dostawcami stosuje kwotę płatności, która została już zapłacona w odniesieniu do faktury.
5.  Koordynator rozrachunków z dostawcami płaci i rozlicza pozostałą kwotę faktury.





