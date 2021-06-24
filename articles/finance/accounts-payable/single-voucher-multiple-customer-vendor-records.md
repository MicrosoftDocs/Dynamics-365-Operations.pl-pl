---
title: Jeden załącznik z wieloma rekordami odbiorców lub dostawców
description: Ten temat zawiera omówienie tego, co się dzieje podczas księgowania jednego załącznika z wieloma rekordami odbiorców lub dostawców. Ta funkcja nie będzie już dostępna w kolejnych wersjach Microsoft Dynamics 365 Finance, w związku z tym nie zalecamy używania tej metody księgowania ze względu na jej wpływ księgowy na przetwarzanie rozliczeń.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 222534
ms.assetid: d4df11ce-4d36-4c66-8230-f5fc58e021bc
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0e9c321315f91de6cf0f2029c26bd4f398a73830
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/07/2021
ms.locfileid: "6194008"
---
# <a name="single-voucher-with-multiple-customer-or-vendor-records"></a>Jeden załącznik z wieloma rekordami odbiorców lub dostawców

[!include [banner](../includes/banner.md)]

Ten temat zawiera omówienie tego, co się dzieje podczas księgowania jednego załącznika z wieloma rekordami odbiorców lub dostawców. Ta funkcja nie będzie już dostępna w kolejnych wersjach, w związku z tym nie zalecamy używania tej metody księgowania ze względu na jej wpływ księgowy na przetwarzanie rozliczeń. 

Do typowych przykładów używania jednego załącznika do wielu odbiorców lub dostawców należą m.in. przeniesienia sald między odbiorcami oraz kompensowanie sald między odbiorcami i dostawcami w tej samej organizacji. 

Załącznik zawierający więcej niż jednego odbiorcę lub dostawcę można wprowadzić przy użyciu jednej z następujących metod:

-   Za pomocą arkusza z zaznaczoną opcją **Tylko jeden numer załącznika**, tak aby każdy wiersz dodawany do arkusza znalazł się w tym samym załączniku.
-   Za pomocą załącznika wielowierszowego, gdy nie ma przeciwstawnego konta księgowego, z więcej niż jednym odbiorcą lub dostawcą.
-   Wprowadzanie załącznika z kombinacją konta i konta przeciwstawnego dostawca/dostawca, odbiorca/odbiorca, dostawca/odbiorca lub odbiorca/dostawca.

W tym temacie opisano sposób przetwarzania rozliczenia podczas księgowania jednego załącznika z wieloma rekordami odbiorców lub dostawców. Ponadto temat zawiera obejścia pomagające zrozumieć, jak unikać używania jednego załącznika z wieloma odbiorcami lub dostawcami. W szczególności podano przykłady ilustrujące dwa typowe scenariusze rozliczania, na które ma wpływ stosowanie jednego załącznika z wieloma odbiorcami lub dostawcami:

-   Księgowanie rabatów gotówkowych
-   Księgowanie przeszacowania

## <a name="how-does-settlement-impact-single-voucher-usage"></a>Jak na rozliczenie wpływa użycie jednego załącznika
Podczas księgowania załącznika, który zawiera wiele rekordów odbiorców lub dostawców, jest tworzony pojedynczy załącznik księgowy, który zawiera wiele sald rozrachunków z odbiorcami lub dostawcami. W procesie rozliczania oryginalne zapisy księgowe są używane do tworzenia zapisów księgowych dla rabatu gotówkowego, niezrealizowanych dodatnich i ujemnych różnic kursowych, zrealizowanych dodatnich i ujemnych różnic kursowych oraz zwolnienia konta rozrachunkowego oryginalnego dokumentu. Na przykład jeśli podczas rozliczania płatności dla dostawcy względem faktury zostanie uwzględniony rabat gotówkowy, musi on zostać zaksięgowany na koncie księgowym rozrachunków z dostawcami konta z oryginalnej faktury. Jeśli oryginalna faktura została zaksięgowana w załączniku zawierającym wiele rekordów dostawców, oryginalne zapisy księgowe są sumowane. W tym przypadku nie jest możliwe przejście do szczegółowego zapisu księgowego dla każdej transakcji z dostawcą w jednym załączniku, dlatego nie istnieje sposób określenia, jak użytkownik zamierzał rozliczyć rabat gotówkowy.

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-cash-discount-accounting"></a>Jeden załącznik z wieloma dostawcami i jego wpływ na księgowanie rabatu gotówkowego

W następującym przykładzie wiele faktur od dostawców jest rejestrowanych w księdze głównej na pojedynczym załączniku na stronie **Arkusz finansowy**. Te faktury są rozdzielone między wiele wymiarów kont.

| Załącznik | Typ konta | Konto  | opis | Uznanie | Strona kredytowa |
|-------------|------------------|--------------|-----------------|-----------|------------|
| GNJL001     | Dostawca           | 1001         | INV1            |           | 100,00     |
| GNJL001     | Dostawca           | 1001         | INV2            |           | 200,00     |
| GNJL001     | Dostawca           | 1001         | INV3            |           | 300,00     |
| GNJL001     | Księga           | 606300-001-- | INV1            |   50,00   |            |
| GNJL001     | Księga           | 606300-002-- | INV1            |   50,00   |            |
| GNJL001     | Księga           | 606300-003-- | INV2            | 200,00    |            |
| GNJL001     | Księga           | 606300-004-- | INV3            | 300,00    |            |

Po zaksięgowaniu jest tworzony jeden załącznik.

| Załącznik | Konto  | Typ księgowania | Kwota w walucie transakcji |
|-------------|--------------|------------------|------------------------------------|
| GNJL001     | 606300-001-- | Arkusz księgi   | 50,00                              |
| GNJL001     | 606300-002-- | Arkusz księgi   | 50,00                              |
| GNJL001     | 606300-003-- | Arkusz księgi   | 200,00                             |
| GNJL001     | 606300-004-- | Arkusz księgi   | 300,00                             |
| GNJL001     | 200110-001-  | Saldo dostawcy   | -100,00                            |
| GNJL001     | 200110-001-  | Saldo dostawcy   | -200,00                            |
| GNJL001     | 200110-001-  | Saldo dostawcy   | -300,00                            |

Należy zauważyć, że załącznik zawiera trzy wpisy dla typu księgowania Saldo dostawcy w jednym załączniku. Nie jest możliwe wskazanie, że debet 50,00 na koncie 606300 001 i debet 50,00 na koncie 606300-002 mają bilansować zapis salda dostawcy na koncie 200110-001. Jest to spowodowane tym, że użytkownik wprowadził wiele rekordów dostawców w jednym załączniku.

Za pomocą tego przykładu możemy analizować wpływ, jaki ma używanie jednego załącznika na późniejsze księgowanie rozliczenia. Załóżmy, że płacisz 197,00 za fakturę na 200,00, otrzymując rabat gotówkowy w wysokości 3,00. Należy zauważyć, że wartość na koncie rabatu gotówkowego jest rozdzielona między wszystkie wymiary kont wydatków wykazanych w załączniku faktury. Jest to spowodowane tym, że do zaksięgowania powyższej faktury został użyty jeden załącznik, bez wskazania, jak użytkownik chciał skorelować dystrybucje wydatków z saldem dostawcy w tym załączniku.

| Załącznik | Konto  | Typ księgowania     | Uznanie | Strona kredytowa |
|-------------|--------------|----------------------|-----------|------------|
| APPAYM001   | 200110-001-  | Saldo dostawcy       | 197.00    |            |
| APPAYM001   | 110110-001-  | Bank                 |           | 197.00     |
| 14000056    | 520200-001-- | Rabat gotówkowy dostawcy |           | 0.25       |
| 14000056    | 520200-002-- | Rabat gotówkowy dostawcy |           | 0.25       |
| 14000056    | 520200-003-- | Rabat gotówkowy dostawcy |           | 1,00       |
| 14000056    | 520200-004-- | Rabat gotówkowy dostawcy |           | 1.50       |
| 14000056    | 200110-001-  | Saldo dostawcy       | 3,00      |            |

Jeśli użytkownik jest niezadowolony z rabatu gotówkowego przydzielanego do wszystkich dystrybucji wydatków z oryginalnej faktury, powinien do rejestrowania faktur używać wielu załączników, a nie jednego. Oto przykład sposobu wprowadzenia wielu załączników w księdze głównej zamiast jednego załącznika pokazanego na początku tego przykładu.

| Załącznik | Typ konta | Konto  | opis | Uznanie | Strona kredytowa | Typ przeciwstawny | Konto przeciwstawne |
|-------------|------------------|--------------|-----------------|-----------|------------|-----------------|--------------------|
| GNJL001     | Dostawca           | 1001         | INV1            |           | 100,00     | Księga          | &lt;pusty&gt;      |
| GNJL001     | Księga           | 606300-001-- | INV1            |   50,00   |            | Księga          | &lt;pusty&gt;      |
| GNJL001     | Księga           | 606300-002-- | INV1            |   50,00   |            | Księga          | &lt;pusty&gt;      |
| GNJL002     | Dostawca           | 1001         | INV2            |           | 200,00     | Księga          | 606300-003--       |
| GNJL003     | Dostawca           | 1001         | INV3            |           | 300,00     | Księga          | 606300-004--       |

Teraz podczas opłacania faktury INV2 zostanie dokonany następujący wpis. Zwróć uwagę, że wymiary finansowe rabatu gotówkowego są takie same, jak wymiary finansowe skojarzonego wydatku.

| Załącznik | Konto  | Typ księgowania     | Uznanie | Strona kredytowa |
|-------------|--------------|----------------------|-----------|------------|
| APPAYM001   | 200110-001-  | Saldo dostawcy       | 197.00    |            |
| APPAYM001   | 110110-001-  | Bank                 |           | 197.00     |
| 14000056    | 520200-003-- | Rabat gotówkowy dostawcy |           | 3,00       |
| 14000056    | 200110-001-  | Saldo dostawcy       | 3,00      |            |

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-realized-gainloss-accounting"></a>Jeden załącznik z wieloma dostawcami i jego wpływ na księgowanie zrealizowanych dodatnich/ujemnych różnic kursowych

| Załącznik | Typ konta | Konto | opis | Uznanie | Strona kredytowa | Typ konta | Konto  |
|-------------|------------------|-------------|-----------------|-----------|------------|------------------|--------------|
| GNJL001     | Dostawca           | 1001        | INV1            |           | 100,00     | Księga           | 606300-001-- |
| GNJL001     | Dostawca           | 1001        | INV2            |           | 200,00     | Księga           | 606300-002-- |

W następującym przykładzie wiele faktur od dostawców jest rejestrowanych w księdze głównej na pojedynczym załączniku na stronie **Arkusz finansowy**. Te faktury są rozdzielone między wiele wymiarów kont. Po zaksięgowaniu jest tworzony jeden załącznik.

| Załącznik | Konto  | Typ księgowania | Kwota w walucie transakcji (EUR) | Kwota w walucie rozliczeniowej (USD) |
|-------------|--------------|------------------|------------------------------------------|-----------------------------------------|
| GNJL001     | 606300-001-- | Arkusz księgi   | 100,00                                   | 114.00                                  |
| GNJL001     | 606300-002-- | Arkusz księgi   | 200,00                                   | 228.00                                  |
| GNJL001     | 200110-001-  | Saldo dostawcy   | -100,00                                  | -114.00                                 |
| GNJL001     | 200110-001-  | Saldo dostawcy   | -200,00                                  | -228.00                                 |

Należy zauważyć, że załącznik zawiera dwa wpisy dla typu księgowania Saldo dostawcy w jednym załączniku. Nie jest możliwe wskazanie, że debet na koncie 606300 001 ma bilansować zapis salda dostawcy 100,00 na koncie 200110-001. Jest to spowodowane tym, że użytkownik wprowadził wiele rekordów dostawców w jednym załączniku. 

Za pomocą tego przykładu możemy analizować wpływ, jaki ma używanie jednego załącznika na późniejsze księgowanie rozliczenia. Załóżmy, że walutą rozliczeniową jest USD, a powyższa transakcja została zaksięgowana w walucie transakcji EUR. Załóżmy, że w pełni opłacono fakturę na 200,00 EUR, ale wystąpiła zrealizowana ujemna różnica kursowa z powodu różnic w kursie wymiany między dniem zaksięgowana faktury a dniem zapłaty. Należy zauważyć, że wartość na koncie zrealizowanej ujemnej różnicy kursowej jest rozdzielona między wszystkie wymiary kont wydatków wykazanych w załączniku faktury. W tym przypadku nastąpił przydział do obu wymiarów 001 i 002, mimo iż użytkownikowi może się wydawać, że tylko wymiar 002 należy do konta wydatków dla rozliczanej faktury. Jest to spowodowane tym, że do zaksięgowania powyższej faktury został użyty jeden załącznik, co uniemożliwia wskazanie, jak użytkownik chciał skorelować dystrybucje wydatków z saldem dostawcy w tym załączniku.

| Załącznik | Konto | Typ księgowania   | Kwota w walucie transakcji (EUR) | Kwota w walucie rozliczeniowej (USD) |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| APPAYM001   | 200110-001- | Saldo dostawcy     | 200,00                                   | 230.00                                  |
| APPAYM001   | 110110-001- | Bank               | -200,00                                  | -230,00                                 |
| 14000056    | 801300-001- | Ujemne różnice kursowe | 0,00                                     | 0.67                                    |
| 14000056    | 801300-002- | Ujemne różnice kursowe | 0,00                                     | 1.33                                    |
| 14000056    | 200110-001- | Saldo dostawcy     |                                          | -2,00                                   |

Jeśli użytkownik jest niezadowolony ze straty z tytułu ujemnych różnic kursowych przydzielanej do wszystkich dystrybucji wydatków z oryginalnej faktury, powinien do rejestrowania faktur używać wielu załączników, a nie jednego. Oto przykład sposobu wprowadzenia wielu załączników w księdze głównej zamiast jednego załącznika pokazanego na początku tego przykładu.

| Załącznik | Typ konta | Konto | opis | Uznanie | Strona kredytowa | Typ przeciwstawny | Konto przeciwstawne |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| GNJL002     | Dostawca           | 1001        | INV1            |           | 100,00     | Księga          | 606300-001--       |
| GNJL003     | Dostawca           | 1001        | INV2            |           | 200,00     | Księga          | 606300-002--       |

Teraz podczas opłacania faktury INV2 zostanie dokonany następujący wpis. Zwróć uwagę, że wymiary finansowe straty z tytułu ujemnych różnic kursowych są takie same, jak wymiary finansowe skojarzonego wydatku.

| Załącznik | Konto | Typ księgowania   | Kwota w walucie transakcji (EUR) | Kwota w walucie rozliczeniowej (USD) |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| APPAYM001   | 200110-001- | Saldo dostawcy     | 200,00                                   | 230.00                                  |
| APPAYM001   | 110110-001- | Bank               | -200,00                                  | -230,00                                 |
| 14000056    | 801300-002- | Ujemne różnice kursowe | 0,00                                     | 2.00                                    |
| 14000056    | 200110-001- | Saldo dostawcy     |                                          | -2,00                                   |

## <a name="one-voucher-for-balance-transfers-and-netting-scenarios"></a>Jeden załącznik do przenoszenia sald i dla scenariuszy kompensowania
Dwa najczęstsze scenariusze wykorzystywania jednego załącznika zawierającego wielu odbiorców lub dostawców to przeniesienia sald od jednego odbiorcy/dostawcy do innego odbiorcy/dostawcy oraz kompensowanie odbiorcy i dostawcy będącego tą samą organizacją. Dwa poniższe przykłady ilustrują preferowaną metodę wykonywania tych scenariuszy jako alternatywę do używania pojedynczych załączników. 

W *przeniesieniu salda* istnieje jeden załącznik z wieloma odbiorcami. Jego celem jest przeniesienie salda od jednego odbiorcy do innego odbiorcy (tak samo dla dostawców). Ten scenariusz może wystąpić, jeśli odpowiedzialność za zapłatę faktury zostanie przeniesiona na inną stronę, np. gdy firma podrzędna przenosi odpowiedzialność na firmę macierzystą. 

W tym przykładzie założono sprzedaż, gdzie odbiorca jest uprawniony do rabatu gotówkowego, jeśli płatność zostanie dokonana w ciągu 10 dni. Odbiorca w tym przykładzie wykorzystuje firmę ubezpieczeniową, która będzie odpowiedzialna za zapłatę faktury. Firma ubezpieczeniowa jest skonfigurowana jako drugi odbiorca w systemie. Saldo oryginalnego odbiorcy jest przenoszone do firmy ubezpieczeniowej, która opłaca fakturę, uzyskując rabat gotówkowy 2% za zapłatę w ciągu okresu rabatowego. 

Aby to zilustrować, załóżmy, że dokonano następującej sprzedaży do odbiorcy ACME. Poniższe zapisy księgowe reprezentują sprzedaż.

| Konto finansowe | Typ księgowania | Uznanie | Strona kredytowa |
|--------------------|------------------|-----------|------------|
| 401100-002-023-    | Przychód          |           | 100        |
| 130100-002-        | Saldo odbiorcy | 100       |            |

Następnie użytkownik przenosi należne saldo z firmy ACME na firmę ubezpieczeniową w jednym załączniku w arkuszu płatności rozrachunków z odbiorcami. Firma ubezpieczeniowa jest konfigurowana jako ubezpieczenia odbiorcy.

| Załącznik | Typ konta | Konto | opis | Uznanie | Strona kredytowa | Typ przeciwstawny | Konto przeciwstawne |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| ARPAYM001   | Odbiorca         | ACME        | Przenoszenie        |           | 100,00     | Odbiorca        | Ubezpieczenie          |

Należy zauważyć, że powyższy wpis znajduje się w jednym załączniku. Załącznik zawiera dwa rekordy odbiorców. Poniższy załącznik jest tworzony podczas księgowania powyższego zapisu w księdze głównej.

| Załącznik | Konto | Typ księgowania | Kwota w walucie transakcji |
|-------------|-------------|------------------|------------------------------------|
| ARPAYM001   | 130100-002- | Saldo odbiorcy | 100,00                             |
| ARPAYM001   | 130100-002- | Saldo odbiorcy | -100,00                            |

Następnie przyjmijmy, że otrzymujesz płatność od odbiorcy Ubezpieczenie w kwocie 98,00 i chcesz tę płatność rozliczyć względem faktury utworzonej przez przeniesienia salda. Spowoduje to zaksięgowane następującego załącznika. Być może oczekujesz, że w rozliczeniu zostaną użyte wymiary finansowe z oryginalnej faktury, ale nie jest to możliwe, ponieważ nie istnieje dokument faktury dla odbiorcy Ubezpieczenie. Należy zauważyć, że domyślnie wymiary dystrybucji rabatu gotówkowego pochodzą z transakcja odbiorcy utworzonej wskutek przeniesienia, a nie z konta przychodów dla oryginalnej faktury. Wartość domyślna jest wynikiem użycia jednego załącznika do przeniesienia sald.

| Załącznik | Konto | Typ księgowania | Uznanie | Strona kredytowa |
|-------------|-------------|------------------|-----------|------------|
| ARPAYM002   | 110110-002- | Bank             | 98.00     |            |
| ARPAYM002   | 130100-002- | Saldo odbiorcy |           | 98.00      |

W pokrewnym załączniku rabatu gotówkowego domyślna wartość wymiaru finansowego pochodzi z transakcji odbiorcy utworzonej wskutek przeniesienia, ponieważ przeniesienie ma więcej niż jednego odbiorcę.

| Załącznik | Konto | Typ księgowania       | Uznanie | Strona kredytowa |
|-------------|-------------|------------------------|-----------|------------|
| ARP-00001   | 403300-002- | Rabat gotówkowy odbiorcy | 2.00      |            |
| ARP-00001   | 130100-002- | Saldo odbiorcy       |           | 2.00       |

Jeśli użytkownik jest niezadowolony z domyślnych wartości wymiarów finansowych rabatu gotówkowego, zamiast jednego załącznika powinien użyć wielu załączników do zarejestrowania przeniesienia salda. Ten scenariusz należy zrealizować poprzez utworzenie faktury korygującej dla odbiorcy, OD którego jest przenoszone saldo, oraz noty debetowej (obciążeniowej) lub faktury dla odbiorcy, DO którego jest przenoszone saldo. W przykładzie poniżej pokazano, jak w celu przeniesienia salda można wprowadzić wiele załączników w arkuszu płatności rozrachunków z dostawcami zamiast używać jednego załącznika, jak to przedstawiono wcześniej w tym w przykładzie.

| Załącznik | Typ konta | Konto | opis | Uznanie | Strona kredytowa | Typ przeciwstawny | Konto przeciwstawne |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| ARPAYM001   | Odbiorca         | ACME        |                 |           | 100,00     | Księga          | 401100-002-023-    |
| ARPAYM002   | Odbiorca         | Ubezpieczenie   |                 | 100,00    |            | Księga          | 401100-002-023-    |

Oznacza to, że gdy odbiorca Ubezpieczenie zapłaci 98,00 załącznikiem ARPAYM02, będą używane poprawne wymiary finansowe z zapisu na koncie księgi załącznika ARPAYM002.

| Załącznik | Konto | Typ księgowania | Uznanie | Strona kredytowa |
|-------------|-------------|------------------|-----------|------------|
| ARPAYM003   | 110110-002- | Bank             | 98.00     |            |
| ARPAYM003   | 130100-002  | Saldo odbiorcy |           | 98.00      |

W pokrewnym załączniku rabatu gotówkowego będą używane wymiary finansowe z przeciwstawnego konta przychodów widocznego w załączniku ARPAYM002.

| Załącznik | Konto     | Typ księgowania       | Uznanie | Strona kredytowa |
|-------------|-----------------|------------------------|-----------|------------|
| ARP-00001   | 403300-002-023- | Rabat gotówkowy odbiorcy | 2.00      |            |
| ARP-00001   | 130100-002-     | Saldo odbiorcy       |           | 2.00       |

## <a name="one-voucher-with-a-netting-for-multiple-customers-and-vendors"></a>Jeden załącznik z kompensacją dla wielu odbiorców i dostawców
Kompensacja może być przydatna, gdy organizacja kupuje i sprzedaje do tej samej firmy. Zamiast opłacać faktury od dostawców i czekać na otrzymanie płatności za faktury dla odbiorców, organizacja może kompensować oba rodzaje faktur. Transakcje kompensacyjne są rozliczane względem zaległych sald. 

Aby to zilustrować, załóżmy, że dostawca 1001 i odbiorca 008 są tą samą jednostką, więc organizacja chce zbilansować salda należności i zobowiązań, a następnie zapłacić/otrzymać pozostałe saldo. Załóżmy, że rekord odbiorcy wykazuje zobowiązanie 75,00 EUR, a rekord dostawcy należność 100,00 EUR. Oznacza to, że chcesz zbilansować salso i zapłacić dostawcy tylko 25,00 EUR. Dodatkowo załóżmy, że walutą rozliczeniową jest USD. W tym przypadku transakcja kompensacyjna jest wprowadzana w jednym załączniku w arkuszu płatności rozrachunków z dostawcami.

| Załącznik | Typ konta | Konto | opis | Uznanie | Strona kredytowa | Typ przeciwstawny | Konto przeciwstawne |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| APPAYM001   | Dostawca           | 1001        | Kompensacja         |  75,00    |            | Odbiorca        | US-008             |

Aby uniknąć problemów z przyszłymi rozliczeniami tej transakcji, zamiast używać jednego załącznika, należy w arkuszu wprowadzić wiele załączników do zarejestrowania transakcji kompensacyjnej. Należy zauważyć, że salda odbiorcy i dostawcy są kompensowane przy użyciu jednego konta rozliczeniowego, co ma zapobiec stosowaniu jednego załącznika zawierającego wiele sald odbiorców i dostawców.

| Załącznik | Typ konta | Konto | opis | Uznanie | Strona kredytowa | Typ przeciwstawny | Konto przeciwstawne |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| 001         | Odbiorca         | US-008      |                 |           |  75,00     | Księga          | 999999---          |
| 002         | Dostawca           | 1001        |                 |  75,00    |            | Księga          | 999999---          |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]