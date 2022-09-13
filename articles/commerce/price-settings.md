---
title: Ustawienia cen
description: W tym artykule opisano różne ustawienia zarządzania cenami i rabatami w centrali Microsoft Dynamics 365 Commerce headquarters.
author: boycez
ms.date: 09/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2022-08-11
ms.openlocfilehash: 4bc8cb16e7960d26adbb9590b4ad83cf46b02838
ms.sourcegitcommit: 6fd44fc6e9a7bad197cab58c36ec25a555724cf1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2022
ms.locfileid: "9410772"
---
# <a name="pricing-settings"></a>Ustawienia cen

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

W tym artykule opisano różne ustawienia zarządzania cenami i rabatami w centrali Microsoft Dynamics 365 Commerce headquarters. Te ustawienia umożliwiają organizacjom definiowanie zachowania cen w rozwiązaniu Commerce w celu spełnienia określonych potrzeb biznesowych.

## <a name="company-level-pricing-settings"></a>Ustawienia wyceny na poziomie firmy

Większość ustawień cen jest na poziomie firmy i można je znaleźć w **Parametry Commerce \> Ceny i rabaty** w centrali Commerce headquarters.

### <a name="best-price-and-compound-concurrency-control-model"></a>Model kontroli współbieżności najlepszej ceny i złożenia

Ustawienie **Modelu kontroli najlepszej ceny i złożonejwspółbieżności** określa sposób, w jaki aparat wyceny przetwarza wiele rabatów w trybie **najlepszej ceny** lub **złożonej** współbieżności. 

Jeśli dla parametru zostanie ustawiona wartość **Najlepsza cena i złożenie w priorytecie**, wszystkie rabaty **złożone** o tym samym priorytecie cen są złożone. Złożony wynik wówczas konkuruje z rabatami **najlepszych cen**, które mają ten sam priorytet cen, stosuje się najlepszą cenę, a wszystkie rabaty o niższym priorytecie cen są ignorowane.

Jeśli dla parametru zostanie ustawiona wartość **Najlepsza cena tylko z priorytetem, zawsze złożone między priorytetami**, wszystkie **złożone** rabaty są traktowane jako rabaty **najlepsza cena**. W ramach priorytetu cen tylko jeden rabat wygrywa. Jeśli ten rabat jest **najlepszą ceną** lub rabatem **złożonym**, jest on złożony ze wszystkimi dodatkowymi **najlepszymi cenami** lub rabatami **złożonymi** o niższym priorytecie cen.

### <a name="discount-compound-behavior"></a>Zachowanie złożenia rabatów

Ustawienie **Zachowanie złożonego rabatu** określa sposób, w jaki aparat cen oblicza wiele rabatów złożonych.

Jeśli parametr ma wartość **Złożony**, jeden rabat jest stosowany ponad innym w sposób skumulowany. Jeśli jest ustawiona wartość **Złożony w pierwotnej cenie**, wszystkie rabaty będą traktowane niezależnie od siebie i stosowane do tej samej ceny oryginalnej.

Na przykład należy pomnażać 10-procentowe rabaty i 20-procentowe rabaty dla produktu, dla którego oryginalna cena $100. Jeśli w parametrze **Zachowanie złożone rabatu** zostanie ustawiona wartość **Złożony**, cena końcowa zostanie $72 ($100 &times; 90% &times; 80%) Jeśli ustawisz na **Złożony w odniesieniu do oryginalnej ceny**, cena końcowa zostanie $70 ($100 – $10 – $20).

### <a name="enable-competition-between-exclusive-threshold-and-other-periodic-discounts"></a>Włącz konkurencję między wyłącznym rabatem progowym i innymi rabatami okresowymi

Jeśli ustawienie **Włącz konkurencjęmiędzy progiem wyłącznym a innymi rabatami okresowymi** ma wartość **Tak**, aparat cen stanowi konkurencję dla wyłącznie rabatów progowych. Nadal obowiązuje priorytet cen. Zachowanie **najlepszej ceny** i **złożonych** rabatów progowych pozostaje niezmienione. Innymi słowy, nie konkurują z rabatami innymi niż progowe.

### <a name="manual-line-discount-and-system-discount"></a>Ręcznie wprowadzony rabat wiersza i rabat systemu

Ustawienie **Ręczny rabat wiersza i rabat systemowy** określa sposób, w jaki aparat cenowy powoduje zastosowanie ręcznego rabatu wiersza i rabatu systemowego do tego samego wiersza. Ręczny rabat wiersza może być złożony na początku rabatu systemowego lub może zastąpić rabat systemowy. Po złożeniu ręcznego rabatu wiersza i rabatu systemowego logika obliczania jest zgodne z ustawieniem **Zachowanie złożonego rabatu**. Ręczne rabaty łączne stosowane do całego zamówienia nie dotyczą tego ustawienia.

### <a name="keep-items-on-the-same-sales-line-for-discount-price-rounding"></a>Zachowaj pozycje w tym samym wierszu sprzedaży w celu zaokrąglania ceny po rabacie

Czasami kwota kwoty rabatu ilościowego nie może być równomiernie podzielona przez ilość kwalifikującą (na przykład, jeśli kwota rabatu jest $10 dla trzech zakupionych jednostek). W takich przypadkach ustawienie **Zachowaj towary w tym samym wierszu sprzedaży w celu zaokrąglania ceny po rabacie** określa zasady działania aparatu cen i rozdziela kwotę rabatu. Jeśli parametr ma wartość **Tak**, kwota rabatu jest stosowana jako całość i nie jest dzielona. Jeśli jest ustawiona wartość **Nie**, kwota rabatu jest dzielona na ilość kwalifikującą i zaokrągloną. Na przykład kwota rabatu w wysokości $10 dla trzech jednostek jest dzielona na $3,33 dla jednej jednostki, $3,33 od drugiej jednostki i $3,34 wyłączona dla trzeciej jednostki.

### <a name="apply-discounts-to-key-in-price-products"></a>Stosuj rabaty do produktów z ceną wprowadzaną z klawiatury

Ustawienie **Zastosuj rabaty do klucza produktów ceny** określa, czy rabaty mogą być stosowane razem z cenami wprowadzanych w punkt sprzedaży. Ustawienia **Wprowadź cenę** w konfiguracji produktu określa, czy i w jaki sposób produkt obsługuje wprowadzoną cenę.

### <a name="apply-discounts-to-price-overrides"></a>Zastosuj rabaty do zastąpień cen

Ustawienie **Zastosuj rabaty do zastąpień cen** określa, czy rabaty mogą być stosowane razem z zastąpieniami cen.

### <a name="distribute-discounts-for-least-expensive-discounts"></a>Rozkłada rabaty dla najtańszych rabatów

W przypadku rabatów łączowych o typie obliczania „najtańsze” ustawienie **Rozdziel rabaty dla najtańszych rabatów** określa, czy aparat cen rozdzieli rabaty między wiersze.

Jeśli parametr ma wartość **Nie**, rabat będzie stosowany tylko do najtańszych wierszy. Na przykład w przypadku rabatu za rabat łączowy „kup 2, otrzymaj 1 za darmo” najtańszy towar będzie darmowy, a pozostałe dwa towary pozostaną z pełną ceną. W tym przypadku odbiorca, który zwraca obydwa towary, za które zapłaconą pełną cenę, nadal otrzyma trzeci towar za darmo. Ten scenariusz może spowodować stratę dla sprzedawcy detalicznego.

Jeśli parametr ma wartość **Tak**, aparat cen rozdziela rabat we wszystkich odpowiednich wierszach. To ustawienie pomaga zmniejszyć stratę ze zwrotów.

### <a name="manually-calculate-multi-line-prices-and-discounts"></a>Ręcznie oblicz ceny i rabaty złożone z wielu wierszy

Ustawienie **Ręcznie oblicz ceny i rabaty wielowierszowe** określa, czy w aparacie cenowym są używane opóźnione obliczenia cen i rabatów dla punktu sprzedaży i kanale obsługi. Jeśli ten parametr ma wartość **Tak**, aparat cen nie oblicza od razu rabatów wielowierszowych (takich jak rabaty ilościowe, rabaty progowe czy rabaty łączone) za każdym razem, gdy zamówienie sprzedaży jest tworzone lub edytowane w punkcie sprzedaży lub w kanale centrum obsługi.

> [!NOTE]
> W wersji Commerce 10.0.30 i wcześniejszej ustawienie **Ręcznie oblicz ceny i rabaty wielowierszowe** steruje tylko kanałem w centrum obsługi. Osobne ustawienie **Ręczne obliczanie wielu rabatów dla towaru** w profilu funkcji steruje zachowaniem w obliczaniu ceny w punkcie sprzedaży. W wersji Commerce 10.0.31 te dwa ustawienia są konsolidowane w jedno ustawienie na poziomie firmy.

### <a name="retention-period-in-days"></a>Okres przechowywania w dniach

Ustawienie **Okres przechowywania w dniach** wskazuje, ile dni po dacie ważności (jeśli jest ustawiona data ważności) lub daty wyłączenia (jeśli nie jest ustawiona data ważności) rabat powinien zostać systemowo usunięty. Jeśli parametr ma wartość **0** (zero), automatyczne usuwanie nie jest stosowane.

> [!NOTE]
> W wersji Commerce 10.0.30 i wcześniejszej to ustawienie nosi nazwę **Liczba dni, po upływie których wygasłe rabaty powinny zostać usunięte**.

### <a name="coupon-bar-code"></a>Kod kreskowy kuponu

Ustawienie **Kod kreskowy kuponu** określa, który określony kod kreskowy jest używany do generowania kodów kreskowych kuponów. Użytkownicy mogą wybrać jeden ze wstępnie zdefiniowanych kodów kreskowych skonfigurowanych na stronie **ustawień kodów kreskowych**. Aby uzyskać więcej informacji o kodach kreskowych i maskach kodów kreskowych, zobacz temat [Konfigurowanie kodów kreskowych](set-up-bar-codes.md) i [konfigurowanie masek kodów kreskowych](set-up-bar-code-masks.md).

### <a name="coupon-code-must-be-manually-applied-to-return-transactions"></a>Kod kuponu trzeba ręcznie stosować do transakcji zwrotu

Ustawienie **Kod kuponu musi być ręcznie zastosowany do ustawienia transakcji zwrotu** ma zastosowanie tylko do transakcji zwrotów, dla których nie został dostarczony żaden dowód sprzedaży. Ustaw parametr **Nie**, jeśli kody kuponów mają być automatycznie stosowane do transakcji. Ustaw wartość **Tak,** jeśli kody kuponów trzeba ręcznie dodać do transakcji.

### <a name="use-sales-agreements-set-up-for-the-organization"></a>Użyj umów sprzedaży ustawionych dla organizacji

W przypadku zamówień typu B2B, jeśli ustawienie **Użyj umów sprzedaży ustawionych dla parametru organizacji** ma wartość **Tak**, aparat cen używa umów sprzedaży, które zostały zdefiniowane dla organizacji w hierarchii klienta użytkownika w celu określenia ceny opartej na umowie. Jeśli ten parametr ma wartość **Nie** lub jeśli hierarchia klientów nie jest zdefiniowana, aparat cen wyszukuje umowy sprzedaży zdefiniowanej dla użytkownika w celu ustalenia ceny na podstawie umowy. Aby uzyskać więcej informacji o hierarchiach klientów w handlu elektronicznym B2B, zobacz temat [Zarządzanie partnerami biznesowymi B2B przy użyciu hierarchii klientów](b2b/partners-customer-hierarchies.md).

## <a name="channel-level-pricing-settings"></a>Ustawienia wyceny na poziomie kanału

Poniższe ustawienia umożliwiają organizacjom kontrolowanie zachowania cen w określonych kanałach sprzedaży.

### <a name="enable-order-price-control"></a>Włącz kontrolę ceny zamówienia

Parametr **Włącz kontrolę ceny zamówienia** znajduje się na skróconej karcie **Ogólne** strony **Konfiguracja centrum obsługi**. Ustawienie określa, czy aparat cen wymusza ograniczenie dotyczące operacji zastępowania ceny w kanale centrum obsługi. Działa w połączeniu z ustawieniem **Zezwalaj na korygowanie ceny** na poziomie produktu.

Jeśli kontrola ceny zamówienia jest wyłączona, dowolny użytkownik działu obsługi może zmieniać ceny w wierszach sprzedaży w kanale centrum obsługi, niezależnie od tego, czy odpowiednie produkty umożliwiają korektę ceny.

Jeśli jest włączona kontrola ceny zamówienia, tylko produkty, w których parametr **Zezwalaj na korektę ceny** jest ustawiony na **Tak** umożliwia zastępowanie ceny w zamówieniach kanałów biur obsługi, a kod przyczyny musi być podany w odpowiednich wierszach sprzedaży. Użytkownik biuera obsługi może zmienić cenę sprzedaży tylko w górę do **Procentu narzutu kosztu**, który jest zdefiniowany w ustawieniach **Retail i Commerce \> Ustawienia kanału \> Ustawienia biura obsługi \> Uprawnienia zastąpienia**. Jeśli wartość zastąpienia ceny przekroczy tę wartość procentową, użytkownik musi przesłać żądanie, które będzie następnie przetwarzane w ramach wstępnie zdefiniowanego przepływu pracy Commerce w celu przejrzenia i zatwierdzenia. Więcej informacji na temat przepływów pracy Commerce zawiera temat [Omówienie systemu przepływów](/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system).

## <a name="product-level-pricing-settings"></a>Ustawienia wyceny na poziomie produktu

Poniższe ustawienia wymuszają reguły cen na poziomie produktu i znajdują się na stronie **Konfiguracja produktu** organizacji.

### <a name="allow-price-adjust"></a>Zezwalaj na korektę ceny

Jeśli w parametrze **Zezwalaj na korygowanie ceny** jest ustawiona wartość **Tak**, można zastosować zastąpienie ceny do produktu w zamówieniach sprzedaży kanału obsługi.

### <a name="key-in-price"></a>Wprowadzanie ceny

Ustawienie **Wprowadź cenę** określa, czy wprowadzona cena jest obowiązkowa po dodaniu produktu do transakcji sprzedaży w punkcie sprzedaży. Określa ono także odpowiednie ograniczenia wartości ceny.

### <a name="zero-price-valid"></a>Cena zerowa jest prawidłowa

Ustawienie **Cena zerowa prawidłowa** określa, czy wstępnie zdefiniowane, obliczone przez system lub ręcznie skorygowane ceny sprzedaży produktu mogą być równe 0 (zero). Ustaw parametr **Tak**, jeśli jest dozwolona cena zero. To ustawienie można także określić na poziomie kategorii w hierarchii produktu Commerce.

### <a name="prevent-all-discounts"></a>Nie zezwalaj na żadne rabaty

Ustawienie parametru **Zapobiegnij wszystkim rabatom** na wartość **Tak** uniemożliwia zastosowanie do produktu wszystkich typów rabatów (w tym rabatów ręcznych). To ustawienie można także określić na poziomie kategorii w hierarchii produktu Commerce.

> [!NOTE]
> To ustawienie nie ogranicza operacji ręcznej zmiany ceny, ponieważ operacja ustawia podstawę ceny i nie jest traktowana jako rabat.

### <a name="prevent-manual-discounts"></a>Nie zezwalaj na rabaty ręczne

Ustawienie parametru **Zapobiegnij ręcznym rabatom** na wartość **Tak** uniemożliwia ręczne zastosowanie do produktu rabatów transakcji lub wiersza (w tym rabatów ręcznych). Nadal można stosować wszystkie inne rabaty. To ustawienie można także określić na poziomie kategorii w hierarchii produktu Commerce.

> [!NOTE]
> To ustawienie nie ogranicza operacji ręcznej zmiany ceny, ponieważ operacja ustawia podstawę ceny i nie jest traktowana jako rabat.

### <a name="prevent-retail-discounts"></a>Nie zezwalaj na rabaty detaliczne

Jeśli w parametrze **Zapobiegaj rabatom sieci sprzedaży** jest ustawiona wartość **Tak**, rabatu **prostego**, **ilościowego**, **progowego**, **łączonego** i **wysyłkowego** nie można zastosować do produktu. Nadal można stosować wszystkie inne rabaty (włącznie z ręcznymi).

### <a name="prevent-tender-based-discounts"></a>Nie zezwalaj na rabaty oparte na metodach płatności

Jeśli w parametrze **Zapobiegaj rabatom opartym na płatności** jest ustawiona wartość **Tak**, do produktu nie można zastosować rabatu **opartego na płatności**. Nadal można stosować wszystkie inne rabaty (włącznie z ręcznymi).

Detaliści często wykluczają niektóre produkty, takie jak nowe towary lub pozycje pożądane, z rabatów opartych na towarze (takie jak rabaty proste lub ilościowe). Jeśli jednak klient płaci za pomocą preferowanej metody płatności, rabat oparty na płatności ciągle może być zastosowany. Aby to osiągnąć, sprzedawcy detaliczni mogą ustawić parametry **Zapobiegaj wszystkim rabatom** i **Zapobiegaj rabatom opartym na płatności** na **Nie**, a parametry **Zapobiegaj rabatom detalicznym** i **Zapobiegaj ręcznym rabatom** na **Tak**.

## <a name="deprecated-or-removed-settings"></a>Usunięte lub wycofane ustawienia

Następujące ustawienia cen zostały usunięte lub są planowane do usunięcia z Dynamics 365 Commerce.

| Ustawienie | Przyczyna wycofania lub usunięcia | Stan usunięcia lub wycofania |
|---------|-----------------------------------|-------------------------------|
| Obsługa nakładających się rabatów | Określiliśmy to ustawienie w parametrach Commerce w celu określenia sposobu wyszukiwania przez aparat cen i określenia najlepszej kombinacji rabatów do zastosowania. Opcja **Najlepszy rabat** wymusza kombinacje wszystkich możliwych rabatów podczas obliczania cen. **Najlepsza wydajność** — opcja jest zoptymalizowana, by używać algorytmu heurystycznego oraz metody klasyfikacji wartości marginalnej w celu ustalania priorytetów, oceniania i ustalania najlepszych kombinacji rabatów na czas. **Obliczanie bilansowe** — opcja w podstawie kodu ta opcja działa tak samo jak opcja **Najlepsza wydajność**. W związku z tym jest to zasadniczo zduplikowana opcja. Aby poprawić wydajność, aparat cen został zaktualizowany, dzięki czemu jako opcja standardowa używana jest tylko **Najlepsza wydajność**. W związku z tym to ustawienie nie ma już zastosowania. | Wycofane w wersji z 10.0.21 i zostanie usunięte w październiku 2022 r. |
| Zezwalanie na korekty cen zwiększające cenę produktu | Stworzyliśmy ustawienie, aby kontrolować, czy funkcja korekty ceny może zwiększyć ceny produktu. Jeśli parametr jest wyłączony, organizacje mogą używać funkcji korekty ceny tylko do ustawiania ceny jednostkowej produktu, by była niższa niż cena podstawowa i cena sprzedaży w umowie handlowej. To ustawienie jest przestarzałe, ponieważ funkcja korekty ceny została zaktualizowana, by obsługiwać korekty dwukierunkowe (zwiększenia lub zmniejszenia) poza polem. | Wycofane w wersji z 10.0.30 i zostanie usunięte w październiku 2023 r. |
| Włącz raport o cenach w sklepie sieci sprzedaży | To ustawienie było możliwe do kontrolowania, czy funkcja **raportu cen** jest dostępna do użycia na stronie formularzu konfiguracji sklepu. To ustawienie jest przestarzałe, ponieważ strona konfiguracji sklepu została zaktualizowana, tak aby zawsze dostarczała **raport cen** jako funkcję standardową. | Wycofane w wersji z 10.0.31 i zostanie usunięte w październiku 2023 r. |
| Używanie bieżącej daty do obliczania cen | Standardowy aparat cenowy Dynamics 365 Supply Chain Management obsługuje obliczanie cen na podstawie żądanej daty wysyłki i żądanej daty przyjęcia wraz z bieżącą datą. Aparat wyceny Commerce obsługuje wyłącznie kalkulację cen na podstawie daty dzisiejszej. W przypadku klientów korzystających z funkcji Supply Chain Management i Commerce zalecamy korzystanie z tego ustawienia i zalecaliśmy klientom ustawienie **Tak**, aby te dwa aparaty cen działały razem. To ustawienie jest przestarzałe, ponieważ fundamentalnie nie zmienia zachowania obliczeń i jest w związku z tym nadmiarowe. | Wycofane w wersji z 10.0.31 i zostanie usunięte w październiku 2023 r. |
| Cena maksymalna | To ustawienie było dostępne w profilu funkcji, aby kontrolować, czy tylko produkty, których cena sprzedaży jest poniższej określonej maksimum ceny, mogą być sprzedawane za pośrednictwem punktu sprzedaży w konkretnych sklepach. Wycofaliśmy to ustawienie z powodu niskiej wartości użycia funkcji. | Wycofane w wersji z 10.0.31 i zostanie usunięte w październiku 2023 r. |
| Zastosuj rabaty do ceny jednostkowej | To ustawienie było przeznaczone do kontrolowania, czy podczas obliczania cen i rabaty są zaokrąglane na poziomie ceny jednostkowej czy na poziomie wiersza sprzedaży. Wycofaliśmy ją, ponieważ nie jest ona używana w żadnym miejscu w bieżącej podstawie kodu. | Wycofane w wersji z 10.0.31 i zostanie usunięte w październiku 2023 r. |
| Ręczne obliczanie wielu rabatów dla pozycji | To ustawienie było dostępne, aby kontrolować, czy aparat cen korzysta z opóźnionego obliczania cen w kanale sklepu sieci sprzedaży. Jeśli ten parametr ma wartość **Tak**, aparat cen nie oblicza od razu rabatów wielowierszowych (takich jak rabaty ilościowe, rabaty progowe czy rabaty łączone) za każdym razem, gdy zamówienie sprzedaży jest tworzone lub edytowane w punkcie sprzedaży. Zdecydowaliśmy się skonsolidować to ustawienie z podobnymi ustawieniami w parametrach Commerce, aby przeprowadzić kontrolę wielokanałową. | Wycofane w wersji z 10.0.31 i zostanie usunięte w październiku 2023 r. |

Aby uzyskać pełną listę usuniętych lub przestarzałych funkcji systemu Dynamics 365 Commerce, zobacz temat [Usunięte lub wycofane funkcje w programie Dynamics 365 Commerce](get-started/removed-deprecated-features-commerce.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
