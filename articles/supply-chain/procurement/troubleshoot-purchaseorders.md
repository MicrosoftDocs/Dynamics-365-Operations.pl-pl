---
title: Rozwiązywanie problemów z zamówieniami zakupu
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z zamówieniami zakupu.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 234458f865e37a2d962aee8ab218b9521847081d
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435646"
---
# <a name="troubleshoot-purchase-orders"></a>Rozwiązywanie problemów z zamówieniami zakupu

W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z zamówieniami zakupu.

## <a name="an-action-can-be-completed-only-after-the-line-number-is-fully-distributed"></a>Akcję można wykonać tylko po pełnym rozdzieleniu numeru wiersza.

Ten problem może wystąpić z powodu niespójności w dystrybucji zamówień zakupu.

Aby odblokować ten wystawiony błąd i zresetować zamówienie zakupu do stanu *Wersji roboczej*, należy przejść do obszaru **Zaopatrzenie i sourcing \> Zadania okresowe \> Wyczyść \> Reset dystrybucji zamówienia zakupu**. Aby uzyskać więcej informacji, zajrzyj do następującego wpisu w blogu: [Rozwiązywanie błędów dystrybucji zamówienia zakupu w Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="when-purchase-orders-are-imported-through-data-management-purchase-order-line-numbers-dont-follow-the-increment-that-defined-in-system-parameters"></a>Gdy zamówienia zakupu są importowane za pomocą zarządzania danymi, numery wierszy zamówienia nie są zgodne z przyrostem zdefiniowanym w parametrach systemu.

### <a name="issue-description"></a>Opis problemu

Domyślnie automatycznie generowane numery wierszy zamówień zakupu, które są importowane za pomocą jednostki danych *Wiersze zamówienia zakupu V2*, nie używaj przyrostu numeru wiersza systemowego określonego w parametrach systemowych. Jeśli ręcznie utworzysz zamówienie zakupu i dodasz wiersze za pośrednictwem interfejsu użytkownika (UI), numery wierszy zostaną poprawnie zwiększone. Jeśli jednak używasz struktury zarządzania danymi (DMF), nie są one poprawnie zwiększane.

Ten problem występuje, ponieważ podczas importowania wierszy przez DMF, jeśli numery wierszy nie są jeszcze przypisane w importowanej encji, system używa metody DMF do ich przypisywania. Ta metoda zawsze zwiększa liczbę wierszy o jeden.

### <a name="issue-workaround"></a>Obejście problemu

Upewnij się, że żądane numery wierszy są już podane w polach numeru wiersza jednostki danych podczas importowania wierszy zamówienia zakupu. W takim przypadku DMF nie zastąpi numerów wierszy.

## <a name="a-default-tax-group-and-a-default-cash-discount-arent-filled-in-from-the-invoice-account"></a>Domyślna grupa podatków i domyślny rabat gotówkowy nie są wypełniane na podstawie konta płatnika.

Jeśli używasz konta faktury, które różni się od konta odbiorcy, domyślna grupa podatkowa i domyślny rabat gotówkowy nie są wypełniane z konta faktury podczas tworzenia zamówienia zakupu.

Jest to celowe. Domyślne wartości grupy podatków, rabatów gotówkowych i innych informacji o cenie są oparte na koncie odbiorcy, a nie na koncie faktury.

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a>Otrzymuję komunikat o błędzie „Nie ustawiono odwołania do obiektu” podczas potwierdzania zamówienia zakupu lub podczas księgowania faktury od dostawcy zgłoszony został wyjątek „Obiekt docelowy wywołania” zgłosił wyjątek.

Ten problem może wystąpić z powodu niespójności w dystrybucji zamówień zakupu.

Aby odblokować ten wystawiony błąd i zresetować zamówienie zakupu do stanu *Wersji roboczej*, należy przejść do obszaru **Zaopatrzenie i sourcing \> Zadania okresowe \> Wyczyść \> Reset dystrybucji zamówienia zakupu**. Aby uzyskać więcej informacji, zajrzyj do następującego wpisu w blogu: [Rozwiązywanie błędów dystrybucji zamówienia zakupu w Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a>Co najmniej jedna dystrybucja księgowa jest rozproszona lub niepełna.

### <a name="issue-description"></a>Opis problemu

Pojawia się następujący błąd: „Co najmniej jedna dystrybucja rozliczeń jest rozprowadzana nadmiernie lub niedostatecznie dystrybuowana”.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Ten problem może wystąpić z powodu niespójności w dystrybucji zamówień zakupu.

Aby odblokować ten wystawiony błąd i zresetować zamówienie zakupu do stanu *Wersji roboczej*, należy przejść do obszaru **Zaopatrzenie i sourcing \> Zadania okresowe \> Wyczyść \> Reset dystrybucji zamówienia zakupu**. Aby uzyskać więcej informacji, zajrzyj do następującego wpisu w blogu: [Rozwiązywanie błędów dystrybucji zamówienia zakupu w Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

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

## <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a>Zamówienia zakupu nie odzwierciedlają ustawień języka firmy.

### <a name="issue-description"></a>Opis problemu

Nazwa produktu w zamówieniu zakupu jest wyświetlana w wersji językowej systemu, a nie w języku określonym dla firmy, w której utworzono zamówienie zakupu.

### <a name="reproduce-the-issue"></a>Odtwórz ten błąd

Poniższa procedura przedstawia jeden ze sposobów odtworzenia błędu.

1. Określ język systemowy jako *EN-US* (Język angielski Stany Zjednoczone).
1. Upewnij się, że istnieje produkt, w którym obsługiwane są języki *EN-US* i *DE* (Niemiecki) dla tłumaczeń nazw produktów.
1. Zmień język firmy na *DE*.
1. W firmie, w której jako język jest ustawiona wartość *DE*, utwórz zamówienie zakupu zawierające produkt.
1. Zauważ, że nazwa produktu nadal jest wyświetlana w języku angielskim, USA (język systemowy).

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Jest to celowe. W przypadku zamówień zakupu produkt jest zawsze pokazywany w wersji językowej systemu. Język zamówienia zakupu jest używany podczas tworzenia arkusza potwierdzeń.

## <a name="the-approved-vendor-list-by-product-entity-doesnt-allow-the-effective-date-to-be-changed"></a>Lista zatwierdzonych dostawców według jednostki produktu nie zezwala na zmianę daty wprowadzenia.

### <a name="issue-description"></a>Opis problemu

Produkt ma zatwierdzonego dostawcę, który ma na przykład datę wejścia w życie 11 stycznia 2018 r. (*11/01/2018*) i datę ważności *Nigdy*. Próba zmiany daty rozpoczęcia na 10 stycznia 2018 (*10/01/2018*) lub 12 stycznia 2018 (*12/01/2018*) powoduje wyświetlenie następującego błędu:

> Nie można utworzyć rekordu na liście zatwierdzonych dostawców (PdsApproveVendorList). Wartość „Data ważności” musi być większa lub równa wartości „Data wejścia w życie”.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Można wydłużyć okres, dla którego dostawca został zatwierdzony. Obowiązują następujące zasady:

- Aby zmienić datę wejścia w życie, tak aby była wcześniejsza niż jakikolwiek z istniejących rekordów (okresów) dla dostawcy towaru, data wygaśnięcia nowego okresu musi być wcześniejsza niż wszystkie daty wygaśnięcia w istniejących rekordach.
- Aby zmienić datę wygaśnięcia, tak aby była późniejsza niż jakikolwiek z istniejących okresów, data wejścia w życie musi być późniejsza niż ostatnia data wygaśnięcia dowolnego istniejącego rekordu.
- Aby skrócić cały okres, do którego dostawca jest zatwierdzony, należy usunąć lub zmodyfikować istniejące rekordy. Alternatywnie można skorzystać z przełącznika **obcinania** podczas importu. Ten przełącznik powoduje usunięcie wszystkich istniejących rekordów z tabeli dla zatwierdzonych dostawców według towarów.

W przykładzie scenariusza opisanego w opisie zagadnienia, gdy rekord ma datę wejścia w życie *11/01/2018* oraz datę ważności *Nigdy*, można zaimportować nowy rekord z datą wejścia w życie *10/01/2018* oraz datę ważności *Nigdy*. Nie można jednak skrócić okresu, tak aby Data wejścia w życie była aktualizowana do *12/01/2018* za pomocą funkcji zarządzania danymi. Tę zmianę należy wprowadzić w interfejsie użytkownika.

## <a name="after-i-change-the-delivery-address-on-a-purchase-order-header-the-delivery-nameisnt-synced"></a>Po zmianie adresu dostawy w nagłówku zamówienia zakupu nazwa dostawy nie jest synchronizowana.

### <a name="issue-description"></a>Opis problemu

Adres w nagłówku zamówienia zakupu jest aktualizowany na adres, który nie jest adresem dostawy. Mimo że adres jest aktualizowany na zamówieniu zakupu, nazwa dostawy nie jest aktualizowana na podstawie zaktualizowanego adresu.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Jest to celowe. Wybrany adres musi być klasyfikowany jako adres dostawy. W przeciwnym razie nazwa dostawy nie zostanie zaktualizowana na podstawie wybranego adresu.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>Czy mogę znaleźć użytkownika, który anulował zamówienie zakupu?

Te informacje są śledzone tylko wtedy, gdy zamówienie zakupu podlega zarządzaniu zmianami. W przypadku korzystania z zarządzania zmianami można sprawdzić, kto przesłał tę zmianę (anulowanie) i, kto ją zatwierdził.
