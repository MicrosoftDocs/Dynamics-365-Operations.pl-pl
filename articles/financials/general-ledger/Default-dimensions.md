---
title: "Wymiary finansowe i księgowanie"
description: "Podczas planowania i konfigurowania planu kont należy wziąć pod uwagę, jak różne składniki będą współpracowały podczas księgowania dokumentu lub arkusza. Te składniki obejmują struktury kont, zaawansowane reguły oraz wymiary bilansowania i stałe. W tym temacie przestawiono poszczególne składniki i opisano sposób ich współdziałania."
author: aprilolson
manager: AnnBe
ms.date: 08/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: fa494ab9c3b3f0540ec042f952344c15796845e6
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="financial-dimensions-and-posting"></a>Wymiary finansowe i księgowanie 

[!include[banner](../includes/banner.md)]

Podczas planowania i konfigurowania planu kont należy wziąć pod uwagę, jak różne składniki będą współpracowały podczas księgowania dokumentu lub arkusza. Te składniki obejmują struktury kont, zaawansowane reguły oraz wymiary bilansowania i stałe. W tym temacie przestawiono poszczególne składniki i opisano sposób ich współdziałania.

## <a name="chart-of-accounts-and-financial-dimension-components"></a>Składniki planów kont i wymiarów finansowych

Program Microsoft Dynamics 365 for Finance and Operations Enterprise Edition zawiera rozbudowany, oparty na regułach system definiowania prawidłowych kombinacji kont głównych i wartości wymiarów finansowych. Ta sekcja zawiera krótkie omówienie funkcji poszczególnych składników oraz opis, gdzie można znaleźć każdy składnik.

### <a name="account-structures"></a>Struktury kont

Struktura konta jest wymagana podczas konfigurowania księgi. Należy zdefiniować i aktywować co najmniej jedną strukturę konta oraz przypisać ją do księgi. Struktura konta musi zawierać konto główne. Możliwe jest określenie kolejności segmentów, która najlepiej odpowiada potrzebom firmy. Po zdefiniowaniu konta głównego system może ustalić używaną strukturę konta. Umieszczenie konta głównego z przodu struktury konta lub w jego pobliżu pomaga ograniczyć dopuszczalne wartości, a system może stosować ostatnią znaną prawidłową wartość jako wartość domyślną. W strukturze konta można umieścić maksymalnie 10 dodatkowych wymiarów finansowych. Struktura konta określa, które wartości wymiarów są prawidłowe w połączeniu z innymi wartościami. Wskazuje także, czy wartości wymiarów muszą zostać wprowadzone.

### <a name="advanced-rules"></a>Reguły zaawansowane

Reguły zaawansowane są opcjonalnym składnikiem konfigurowanym podczas tworzenia planu kont. Do struktury konta można dodać dowolną liczbę reguł zaawansowanych. Reguły zaawansowane są często używane do obsługi scenariuszy, w których muszą być śledzone dodatkowe wymiary finansowe po spełnieniu określonych kryteriów. Na przykład jeśli korzystasz z konta Wydatki na podróże służbowe, warto śledzić dodatkowe informacje, takie jak wydarzenia, na które pracownik podróżuje. Jeśli istnieje wiele reguł zaawansowanych, są stosowane w kolejności alfabetycznej według nazw reguł. Segmenty dodawane przez regułę można stosować dopiero po segmentach w strukturze konta.

### <a name="balancing-dimension"></a>Wymiar bilansowania

Opcjonalnie można zdefiniować wymiar finansowy bilansowania. Na stronie **Księga** można zdefiniować wymiar finansowy, który powinien być bilansowany. Następnie każdorazowo podczas księgowania transakcji do tego wymiaru finansowego system automatycznie tworzy i księguje zapisy powodujące zbilansowanie tego wymiaru finansowego.

### <a name="defaultfixed-financial-dimensions-on-the-main-account"></a>Domyślne/stałe wymiary finansowe konta głównego

Domyślne wymiary pochodzą z różnych miejsc, takich jak rekordy główne (na przykład rekordy odbiorców lub dostawców), nagłówków dokumentów i konta głównego. Ten temat koncentruje się na wymiarach domyślnych konta głównego z podziałem na firmy. Można określić, czy konto główne ma wartość **Niestałe** czy **Stałe** dla każdego wymiaru finansowego używanego we wszystkich strukturach kont w księdze. Jeśli wymiar finansowy ma wartość **Niestałe**, używa wartości domyślnej, ale można ją zastąpić. To zachowanie dotyczy wszystkich wartości domyślnych w systemie, nawet tych, które pochodzą z rekordów głównych. Jeśli wymiar finansowy ma ustawioną wartość **Stałe**, jest ona stosowana zawsze, niezależnie od tego, czy pochodzi z innego miejsca jako wartość domyślna, czy też wprowadził ją użytkownik.

## <a name="order-in-which-default-dimensions-are-applied-during-posting"></a>Kolejność stosowania wymiarów domyślnych podczas księgowania

Ludzie często pytają o kolejność uruchamiania różnych składników. Bardzo ważna jest wiedza o kolejności stosowania wymiarów domyślnych, ponieważ to zachowanie wpływa na podejście do konfigurowania.

> [!NOTE]
> Ta informacja dotyczy tylko stosowania wymiarów domyślnych w aplikacji. W przypadku importowania danych za pomocą programu Microsoft Excel lub struktury zarządzania danymi zachowanie się różni.

### <a name="example-1"></a>Przykład 1

**Struktura konta**

| Konto główne            | Jednostka biznesowa           | Dział              | Centrum kosztu             |
|-------------------------|-------------------------|-------------------------|-------------------------|
| Wszystkie wartości są dozwolone. | Wszystkie wartości są dozwolone. | Wszystkie wartości są dozwolone. | Wszystkie wartości są dozwolone. |

**Konto główne**

| Konto główne | Nazwisko          | Firma | Dział                                 |
|--------------|---------------|--------------|--------------------------------------------|
| 401100       | Sprzedaż produktu | USMF         | Stała — 022 Dział Sprzedaż i marketing |

Na poniższej ilustracji przedstawiono stały wymiar domyślny ustawiony na koncie głównym 401100.

[![Domyślne wymiary finansowe](./media/default-dimensions.png)](./media/default-dimensions.png)

W tym bardzo podstawowym przykładzie wprowadzimy arkusz finansowy, gdzie dla wymiaru Dział skonfigurowano używanie wartości domyślnej **023** (Operacje). Wprowadzimy i zaksięgujemy na koncie księgowym. Poniższa ilustracja pokazuje domyślny wymiar finansowy w nagłówku księgi głównej.

[![Arkusze finansowe](./media/general-journal.png)](./media/general-journal.png)

Wymiar domyślny w nagłówku arkusza spowoduje, że dział 023 będzie stosowany domyślnie do wiersza konta sprzedaży. Na poniższej ilustracji przedstawiono wiersz arkusza finansowego, gdzie jest stosowana domyślna wartość wymiaru **023** z nagłówka.

[![Załącznik arkusza](./media/journal-voucher.png)](./media/journal-voucher.png)

Jednak podczas księgowania wiersza jest stosowany wymiar stały, a wiersz jest księgowany do działu 022. Na poniższej ilustracji przedstawiono zaksięgowany załącznik, w którym do konta sprzedaży został zastosowany stały wymiar.

[![Transakcje na załączniku](./media/voucher-transactions.png)](./media/voucher-transactions.png)

### <a name="example-2"></a>Przykład 2

W tym przykładzie użyto tych samych ustawień, co w pierwszym przykładzie. Jednak dodamy drugi składnik i użyjemy wymiaru Dział jako wymiaru bilansowania. Na poniższej ilustracji **Dział** jest ustawiony jako wymiar finansowy bilansowania w księdze firmy USMF.

[![Księga](./media/ledger.png)](./media/ledger.png)

Gdy jest używana ta sama konfiguracja nagłówka arkusza i księgowana ta sama transakcja, stały wymiar jest stosowany najpierw. Następnie jest stosowana logika bilansowania w celu zagwarantowania, że każdy dział ma wpis zbilansowany. Na poniższej ilustracji przedstawiono transakcje załączników, które zawierają zapis bilansowania po zastosowaniu wymiaru stałego.

[![Transakcje na załączniku](./media/voucher-transactions2.png)](./media/voucher-transactions2.png)

### <a name="example-3"></a>Przykład 3

W tym przykładzie dodamy regułę zaawansowaną. Reguła zaawansowana określa, że jeśli są używane konto sprzedaży 401100 i dział 022 (Sprzedaż i marketing), system powinien śledzić dodatkowy segment o nazwie Odbiorca.

Ten przykład jest ważny ze względu na kolejność. Struktura konta jest ustalana po wprowadzeniu konta głównego. Po utworzeniu odwołania do konfiguracji struktury konta system może określić, że istotne są konto główne, jednostka biznesowa, dział i centrum kosztów. W tym momencie reguła zaawansowana nie została jeszcze zainicjowana, ponieważ stałe wymiary nie są stosowane, dopóki w załączniku arkusza nie zastosowano wymiarów domyślnych podczas księgowania. Na poniższej ilustracji segment Odbiorca nie jest obecny, ponieważ nie zostały spełnione kryteria reguły zaawansowanej.

[![Konto finansowe](./media/drop-down.png)](./media/drop-down.png)

Księgowanie się nie powiedzie, ponieważ na końcu procesu zastosowano stały wymiar. Funkcja weryfikacji wymiarów stwierdza, że segment Odbiorca jest wymagany, jeśli kontem głównym jest 401100, a działem 022. Księgowanie nie może nastąpić z powodu błędu sprawdzania poprawności. Na poniższej ilustracji przedstawiono komunikat, który jest wyświetlany, gdy funkcja weryfikacji wymiarów stwierdzi, że segment Odbiorca jest wymagany.

[![Szczegóły komunikatu](./media/message.png)](./media/message.png)

W tym przykładzie należy zastąpić wartość domyślną, tak aby reguła zaawansowana była inicjowana i można było wprowadzić segment Odbiorca. Jednak to rozwiązanie nie zawsze jest możliwe, a niektórzy użytkownicy nawet nie są świadomi istnienia reguł księgowania. W związku z tym ważna jest znajomość kolejności stosowania wymiarów domyślnych podczas konfigurowania planu kont.

Aby osiągnąć żądany cel w tym przykładzie, można zmienić konfigurację na kilka sposobów. Można na przykład utworzyć nową strukturę konta dla kont sprzedaży i umieścić w niej segment Odbiorca. Można także dodać więcej wierszy w istniejącej strukturze konta oraz określić konto główne i poprawne wartości działów. Następnie w dodatkowej strukturze odbiorców można utworzyć osobną strukturę konta dla kont sprzedaży, w której będzie obecny segment Odbiorca.

## <a name="additional-resources"></a>Dodatkowe zasoby 

Niektóre z poniższych zasobów odnoszą się do starszej wersji programu Finance and Operations. Jednak większość informacji na temat stosowania wymiarów domyślnych oraz pojęcia i zagadnienia są takie same, jak we wcześniejszej wersji, a odniesienia zachowują ważność.

[Zbilansowane arkusze dla księgowania międzyjednostkowego](example-balanced-journals-interunit-accounting.md)

[Planowanie planu kont](plan-chart-of-accounts.md) 

[Planowanie planu kont w systemie AX 2012 (blog)](https://blogs.msdn.microsoft.com/axsa/2014/06/12/planning-your-chart-of-accounts-in-ax-2012-part-1-of-7/) — to łącze prowadzi do 1. części siedmioczęściowej serii.

[Ustawienia domyślne wymiarów w zasadach podziałów księgowań](https://blogs.msdn.microsoft.com/ax_gfm_framework_team_blog/2013/12/16/dimension-defaulting-in-accounting-distributions-part-1-introduction/)

[Ustawienia domyślne wymiarów w strukturze wymiarów](https://blogs.msdn.microsoft.com/ax_gfm_framework_team_blog/2014/09/)

