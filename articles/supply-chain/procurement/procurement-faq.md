---
title: Zaopatrzenie — często zadawane pytania
description: Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące funkcji zaopatrzenia w aplikacji Supply Chain Management
author: kamaybac
ms.date: 05/31/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 09c99b88bc47609158805cdba1291ae462cda178
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477257"
---
# <a name="procurement-faq"></a>Zaopatrzenie — często zadawane pytania

[!include [banner](../includes/banner.md)]

Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące funkcji zaopatrzenia w aplikacji Supply Chain Management.

## <a name="can-i-show-only-purchase-orders-that-i-created"></a>Czy mogę wyświetlić utworzone przeze mnie zamówienia zakupu?

Ta funkcja jest obecnie niedostępna.

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a>Czy mogę zarezerwować zapasy i utworzyć transakcje dla zarejestrowanych zapasów w zamówieniu zakupu?

### <a name="issue-description"></a>Opis problemu

Nawet jeśli towary znajdują się w stanie *Zarejestrowano* zamówienia zakupu, nadal można zarezerwować zapasy. Innymi słowy, transakcje można tworzyć na podstawie zarejestrowanych zapasów.

### <a name="reproduce-the-issue"></a>Odtwórz ten błąd

Poniższa procedura przedstawia jeden ze sposobów odtworzenia błędu.

1. Umożliwia tworzenie zamówienia zakupu.
2. Zarejestruj wiersz zamówienia zakupu.
3. Zauważ, że można generować rezerwacje lub transakcje dla zarejestrowanych zapasów.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Jest to celowe. Oczekuje się, że zarejestrowane towary zostały fizycznie odebrane w magazynie lub zapasach i dlatego są one dostępne do rezerwacji.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>Czy mogę znaleźć użytkownika, który anulował zamówienie zakupu?

Te informacje są śledzone tylko wtedy, gdy zamówienie zakupu podlega zarządzaniu zmianami. W przypadku korzystania z zarządzania zmianami można sprawdzić, kto przesłał tę zmianę (anulowanie) i, kto ją zatwierdził.

## <a name="why-cant-i-link-a-purchase-agreement-to-an-existing-purchase-order"></a>Dlaczego nie można połączyć umowy zakupu z istniejącym zamówieniem zakupu?

Umowa zakupu musi być powiązana z zamówieniem podczas tworzenia zamówienia. W przeciwnym razie wiersze zamówienia zakupu nie mogą być kojarzone z wierszami umowy zakupu.

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>Jaki czek powoduje wyświetlenie komunikatu „Zaktualizuj ceny i rabaty wprowadzone ręcznie lub na zewnętrznym dokumencie”?

Po zmianie daty wysyłki może pojawić się komunikat „Zaktualizuj ceny i rabaty wprowadzone ręcznie lub dokument zewnętrzny”. Ten komunikat jest wyświetlany, ponieważ w przypadku zmiany daty wysyłki może zostać wyzwolona inna umowa handlowa lub handlowa i spowodować zmianę ceny. Zmiana daty wysyłki może również wpłynąć na harmonogramy magazynów i inne powiązane informacje.

Komunikat jest wyzwalany po każdej zmianie którejkolwiek z dat lub innych parametrów. Komunikat ma na celu upewnienie się, że użytkownik wie o zmianach cen, które mogą nastąpić z powodu tych zmian.

Komunikat jest monitem o ocenę umowy handlowej (TAE). Aby uzyskać pełny opis, zajrzyj do [Zasady oceny umów handlowych](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).

## <a name="why-cant-i-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>Dlaczego nie mogę zaksięgować więcej niż jednej faktury dla wiersza zamówienia zakupu zawierającego pozycje oparte na kategorii?

Ilość jest obowiązkowa, jeśli chcesz zaksięgować faktury. Dlatego jeśli zafakturowano całą ilość w wierszu tylko dla części kwoty, nie będzie można zafakturować pozostałej kwoty na innej fakturze.
