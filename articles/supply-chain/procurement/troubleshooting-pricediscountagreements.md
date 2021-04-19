---
title: Rozwiązywanie problemów z cenami, promocjami, umowami i rabatami
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z cenami, promocjami, umowami i rabatami.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 12bc3cbccb1577c278489f640299510b3ced17e7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811093"
---
# <a name="troubleshoot-prices-discounts-agreements-and-rebates"></a>Rozwiązywanie problemów z cenami, promocjami, umowami i rabatami

W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z cenami, promocjami, umowami i rabatami.

## <a name="i-cant-link-a-purchase-agreement-to-a-purchase-order-line-after-the-purchase-order-is-created"></a>Nie można połączyć umowy zakupu z wierszem zamówienia zakupu po utworzeniu zamówienia zakupu.

Umowa zakupu musi być powiązana z zamówieniem podczas tworzenia zamówienia. W przeciwnym razie wiersze zamówienia zakupu nie mogą być kojarzone z wierszami umowy zakupu.

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>Jaki czek powoduje wyświetlenie komunikatu „Zaktualizuj ceny i rabaty wprowadzone ręcznie lub na zewnętrznym dokumencie”?

Po zmianie daty wysyłki może pojawić się komunikat „Zaktualizuj ceny i rabaty wprowadzone ręcznie lub dokument zewnętrzny”. Ten komunikat jest wyświetlany, ponieważ w przypadku zmiany daty wysyłki może zostać wyzwolona inna umowa handlowa lub handlowa i spowodować zmianę ceny. Zmiana daty wysyłki może również wpłynąć na harmonogramy magazynów i inne powiązane informacje.

Komunikat jest wyzwalany po każdej zmianie którejkolwiek z dat lub innych parametrów. Komunikat ma na celu upewnienie się, że użytkownik wie o zmianach cen, które mogą nastąpić z powodu tych zmian.

Komunikat jest monitem o ocenę umowy handlowej (TAE). Aby uzyskać pełny opis, zajrzyj do [Zasady oceny umów handlowych](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).

## <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a>Przyjęcie zamówienia zakupu nie obejmuje wszystkich opłat.

### <a name="reproduce-the-issue"></a>Odtwórz ten błąd

Poniższa procedura przedstawia jeden ze sposobów odtworzenia błędu.

1. Na stronie **Parametry modułu Zaopatrzenie i sourcing** na karcie **Dostawa** upewnij się, że opcja **Generuj opłaty przy odbiorze produktu** jest ustawiona na wartość *Tak*.
1. Tworzenie zamówienia zakupu, które zawiera zmiany.
1. Potwierdź zamówienie zakupu.
1. Odbiór zamówienia zakupu.
1. Spójrz na sumę przychodu i porównaj ją z oczekiwaną sumą.
1. Zauważ, że nie wszystkie opłaty są uwzględniane w przyjęciu zamówienia zakupu.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Rozwiązanie to zależy od sposobu, w jaki skonfigurowano opłaty dodatkowe. Aby uzyskać informacje o tym, jak skonfigurować różne opłaty, aby spełnić Twoje wymagania, zobacz następujący wpis na blogu: [Księguj różne opłaty w momencie przyjęcia produktów](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).

## <a name="trade-agreement-prices-and-discounts-arent-applied-on-sales-or-purchase-order-lines-that-are-imported-through-data-management"></a>Ceny i rabaty umowy handlowej nie są stosowane w wierszach sprzedaży lub zamówienia zakupu, które są importowane za pomocą zarządzania danymi.

### <a name="issue-description"></a>Opis problemu

Umowy handlowe, które mają zastosowanie do wierszy sprzedaży lub zamówienia zakupu, nie są stosowane w wierszach importowanych za pomocą funkcji zarządzania danymi. Jednak te same umowy handlowe są stosowane do wierszy sprzedaży lub zamówienia zakupu, które są tworzone ręcznie.

### <a name="reason-for-the-issue"></a>Przyczyna problemu

Jeśli wiersze zamówienia zakupu, które są importowane za pomocą zarządzania danymi, zawierają już informacje o cenie, umowa handlowa nie zostanie ponownie oszacowana dla tych wierszy. Na przykład, jeśli **Procent rabatu dla wiersza** lub jakakolwiek cena i wartość rabatu jest ustawiona dla wiersza, umowy handlowe nie będą wyszukiwane dla tego wiersza.

### <a name="issue-workaround"></a>Obejście problemu

Takie zachowanie jest oczekiwane i podobne zarówno do zamówień sprzedaży, jak i zamówień zakupu.

Jako rozwiązanie alternatywne należy zaimportować wiersze zamówienia zakupu bez ustawiania żadnych informacji o cenach. Następnie zostaną zastosowane umowy handlowe, a wiersze zamówienia zakupu zostaną zaktualizowane na podstawie zdefiniowanych umów handlowych.

## <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a>Rabat dostawcy nie jest kumulowany na podstawie faktur.

### <a name="issue-description"></a>Opis problemu

Jeśli faktury, które zostały zaksięgowane, mają różne terminy płatności, te faktury nie są uwzględniane w wygenerowanych rabatach dostawców.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Zgodnie z projektem termin płatności nie jest brany pod uwagę przy obliczaniu rabatu dla dostawcy. Rozważ dostosowanie systemu, tak aby termin płatności i związek z fakturą były bardziej widoczne w odniesieniu do faktycznego rabatu dostawcy.

## <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a>Ceny jednostkowe w zamówieniach zakupu nie są obliczane na podstawie konwersji jednostek.

### <a name="issue-description"></a>Opis problemu

Po zmianie jednostki w zamówieniu zakupu ceny umowy handlowej nie są ponownie obliczane zgodnie z definicjami konwersji jednostek.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Ceny są zawsze uzyskiwane z umów handlowych (lub innych ustawień cen w systemie, takich jak umowy sprzedaży lub ceny towarów) i są ustalane dla jednostki.

Jeśli jednostka została zmieniona w wierszu zamówienia, system wyszukuje cenę nowej jednostki i stosuje tę cenę. Jeśli dla jednostki nie zostanie znaleziona żadna cena, system nie zastosuje ceny. Konwersji jednostek nie można użyć do przeliczenia ceny na inną jednostkę. Teoretycznie cena jednego pola o wartości 10 może nie być równa dziesięć razy więcej niż cena jednego pola.

### <a name="issue-workaround"></a>Obejście problemu

Jednym ze sposobów obejścia tego problemu jest zagwarantowanie, że istnieją umowy handlowe dla oczekiwanych jednostek, które będą używane w wierszach zamówień dla towaru.

## <a name="currency-conversion-issues-occur-with-trade-agreements"></a>Problemy z konwersją walut występują w umowach handlowych.

Ceny w umowach handlowych nie są przeliczane zgodnie z walutą, jeśli waluta jest inna w zamówieniu zakupu.

Funkcja *Waluty ogólnej* umożliwia definiowanie cen i rabatów tylko w jednej walucie. Następnie można dokonać konwersji na inne waluty w razie konieczności. Ponadto po zakończeniu konwersji funkcja może automatycznie stosować przyjazne zaokrąglanie.

## <a name="when-i-open-the-purchase-agreement-page-in-a-line-view-mode-i-cant-personalize-the-page-by-adding-the-price-unit-field-in-the-overview-of-the-line"></a>Kiedy otwieram stronę Umowa zakupu w trybie widoku liniowego, nie mogę spersonalizować strony, dodając pole Jednostka ceny w przeglądzie wiersza.

W personalizacjach nie można dołączać niektórych pól udostępnionych w strukturze umowy. To ograniczenie występuje z powodu zaimplementowanego modelu danych. Nie można więc personalizować pola **Jednostka cenowa**.

## <a name="the-maximum-limit-from-a-purchase-agreement-isnt-effective-on-a-purchase-requisition"></a>Maksymalny limit z umowy zakupu nie obowiązuje w zapotrzebowaniu zakupu.

### <a name="issue-description"></a>Opis problemu

Jeśli zapotrzebowanie zakupu jest połączone z umową zakupu, maksymalny limit z umowy zakupu nie obowiązuje w zapotrzebowaniu zakupu. Domyślne informacje o cenie są wprowadzane poprawnie, ale więcej niż maksymalny limit z umowy zakupu może zostać zamówiony w zapotrzebowaniu zakupu.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

To zachowanie jest oczekiwane. Zapotrzebowania nie zawsze są zatwierdzane, więc ilość lub kwota nie powinna być rezerwowana w umowie zakupu. Z tego powodu nie będzie można spełnić limitu maksymalnego z umowy zakupu.

## <a name="trade-agreements-can-be-created-from-rejected-rfqs-therefore-the-system-doesnt-prevent-trade-agreement-journals-from-being-created-if-the-rfq-line-hasnt-been-accepted"></a>Umowy handlowe można tworzyć na podstawie odrzuconych zapytań ofertowych. Dlatego system nie zapobiega tworzeniu arkuszy umów handlowych, jeśli wiersz ZO nie został zaakceptowany.

Możesz tworzyć umowy handlowe dla dowolnych odpowiedzi na zapytanie ofertowe (ZO), niezależnie od tego, czy zostały zaakceptowane, czy odrzucone. Aby uzyskać więcej informacji, zobacz [Omówienie zapytań ofertowych (ZO)](request-quotations.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]