---
title: "Omówienie zamówień zakupu"
description: "W tym artykule podano ogólne informacje dotyczące zamówień zakupu oraz łącza do dodatkowych artykułów, które odnoszą się do różnych etapów pokonywanych przez zamówienie zakupu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PurchTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 93083
ms.assetid: e9b7bc5b-1d7e-4ec2-97be-d655274b0613
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: aed1a411aaefeebb96c2b922afc2e3e7f82cdbb7
ms.lasthandoff: 03/31/2017


---

# <a name="purchase-order-overview"></a>Omówienie zamówień zakupu

W tym artykule podano ogólne informacje dotyczące zamówień zakupu oraz łącza do dodatkowych artykułów, które odnoszą się do różnych etapów pokonywanych przez zamówienie zakupu.

Zamówienie zakupu jest dokumentem, który reprezentuje umowę z dostawcą na zakup towarów lub usług. Dokument ten pomaga również monitorować przyjęcia produktów dokonywane względem zamówienia, a później księgować faktury od dostawcy wystawiane przez niego za zamówienie.  

Strona **Zamówienia zakupu** zawiera przegląd dostępnych zamówień i umożliwia ich modyfikowanie. Po otwarciu zamówienia zakupu można wybrać widok **Nagłówek**, który zawiera informacje określane tylko jeden raz dla każdego zamówienia, takie jak szczegóły dostawcy. Alternatywnie można wybrać widok **Wiersze**, w którym można modyfikować wiersze zamówienia. Zazwyczaj użytkownik przełączy się między tymi dwoma widokami tak jak można zmodyfikować POs. Opłaty nie są wyświetlane bezpośrednio na **zamówienia zakupu** stronie, ale są dostępne za pośrednictwem menu w wierszach i nagłówku zamówienia.  

Istnieje wiele raportów, gdzie można przeglądać informacje o zamówieniach zakupu, przyjęciach produktów i fakturach od dostawców. Raporty te znajdują się w modułach **Zaopatrzenie i sourcing** i **Rozrachunki z dostawcami**.  

Obszary robocze **Przygotowanie zamówienia zakupu** i **Przyjęcie i obsługa zamówienia zakupu** umożliwiają wyświetlanie list zamówień zakupu w różnych stanach zaawansowania. Zawierają one również podsumowanie czynności, które należy podjąć. Obszar roboczy **Przygotowanie zamówienia zakupu** koncentruje się na tworzeniu i weryfikowaniu zamówienia zakupu, prowadzeniu zamówienia przez proces zatwierdzenia oraz potwierdzaniu z dostawcą. **Zakupu, przyjęcie zamówienia i kontynuacji** obszaru roboczego koncentruje się na przetwarzanie przyjęcia towarów lub usług z punktu sprzedaży. Obejmuje on listy, które dają wgląd w przyjęć zaległe lub że wkrótce będą do oddania przez dostawcę. Te obszary robocze nie są wykorzystywane do wykonywania pokrewnych operacji przyjęć do magazynu. Te czynności są wykonywane za pomocą stron w modułach **Zarządzanie zapasami** i **Zarządzanie magazynem**. Przetwarzanie faktur od dostawców powinno się odbywać za pomocą obszaru roboczego **Wprowadzanie faktur od dostawcy**, a płatności obsługiwać za pomocą obszaru roboczego **Płatności dostawcy**.  

Poniższe artykuły zawierają omówienie różnych etapów, przez które przechodzi zamówienia zakupu:

-   [Tworzenie zamówienia zakupu](purchase-order-creation.md)
-   [Zatwierdzanie i potwierdzanie zamówienia zakupu](purchase-order-approval-confirmation.md)
-   [Przyjęcie produktów względem zamówień zakupu](product-receipt-against-purchase-orders.md)
-   [Przegląd faktur od dostawcy](/dynamics365/operations/financials/accounts-payable/vendor-invoices-overview)

## <a name="types-of-purchase-orders"></a>Typy zamówień zakupu
Istnieją trzy typy organizacji producentów. Podczas tworzenia zamówienia zakupu, należy określić typ. Na stronie **Parametry modułu Zaopatrzenie i sourcing** można skonfigurować domyślny typ nowych zamówień.

| Typ zamówienia zakupu        | Opis                                                                                                                                                                                                                                                                           |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| W arkuszu        | Ten typ umożliwia tworzenie wersji roboczej zamówienia zakupu. Ten typ nie ma wpływu na ilości zapasów ani nie generuje transakcji magazynowych. Wiersze arkusza zamówienia zakupu nie są uwzględniane w planowaniu głównym.                                                                                                       |
| Zamówienie zakupu | Ten typ umożliwia tworzenie zamówień zakupu, gdy zamówienia mają być potwierdzane z dostawcą, ponieważ zamówienia są przetwarzane z użyciem przyjęcia i fakturowania, zanim dostawca otrzyma płatność. Tego rodzaju zamówienie zakupu jest najczęściej stosowane.                                                                          |
| Zwrot towaru | Tego typu należy używać przy zwracaniu towarów do dostawcy. Ten typ zamówienia wymaga podania numeru autoryzacji zwrotu materiałów (RMA) otrzymanego od dostawcy. Numer RMA podaje się na karcie **Ogólne** w ustawieniach zamówienia zakupu. Wiersze zamówienia muszą mieć ilości ujemne. |

## <a name="purchase-order-statuses"></a>Stany zamówień zakupu
Zamówienia zakupu zawierają kilka pól stanu, które wskazują postęp realizacji zamówienia. Wszystkie te pola są widoczne w widoku zamówienia **Nagłówek**, a niektóre z nich są również widoczne w siatce przeglądu wszystkich zamówień. Pole **Stan** pokazuje stan dotyczący ilości w zamówieniu. Dostępne są następujące wartości:

-   **Otwarte zamówienie** — Zamówienia zostały utworzone i podano ilości w zamówieniu.
-   **Otrzymane** — Niektóre ilości zostały odebrane, ale nie są jeszcze zafakturowane.
-   **Zafakturowane** — Cała ilość w zamówieniu została zafakturowana. **Uwaga:** Jeśli zamówienie zostało *częściowo* zafakturowane, żaden ze stanów — **Otrzymane** ani **Zafakturowane** — nie jest właściwy. W związku z tym zamówienie nadal będzie miało stan **Otwarte zamówienie**.
-   **Anulowane** — Zamówienie zostało potwierdzone, ale później anulowane. W związku z tym ten stan wskazuje, że nie ma już żadnych otwartych ilości w zamówieniu.

Pole **Stan dokumentu** ułatwia szybkie przeglądanie postępu realizacji zamówienia pod względem dokumentów, które zostały przetworzone. Pokazuje stan najnowszego dokumentu, który został sfinalizowany dla zamówienia. Dostępne są następujące wartości:

-   **Brak** — Dla zamówienia jeszcze przetworzono żadnego dokumentu.
-   **Zapytanie dotyczące zakupu** — Wygenerowano zapytanie dotyczące zakupu, a zamówienie oczekuje na informacje zwrotne od dostawcy.
-   **Zamówienie zakupu** — Przetworzono potwierdzenie zamówienia.
-   **Dokument przyjęcia produktów** — Dla zamówienia przetworzono przyjęcie produktów.
-   **Faktura** — Wystawiono fakturę do zamówienia.

Pole **Stan zatwierdzenia** jest używane, gdy zamówienie zakupu przechodzi przez proces lub przepływ pracy weryfikacji. Dostępne są następujące wartości:

-   **Wersja robocza**, **W trakcie przeglądu** i **Odrzucone** — Te stany są używane tylko w przypadku, gdy dla zamówienia zakupu jest stosowany przepływ pracy zatwierdzania.
-   **Zatwierdzone** — Ten stan jest przypisywany zamówieniom o ukończonym przepływie pracy zatwierdzania. Zamówienia tworzone bez używania przepływu pracy zatwierdzania otrzymują status **Zatwierdzone** natychmiast.
-   **W trakcie analizy zewnętrznej** — Ten stan jest używany w scenariuszach, gdy do dostawcy jest wysyłane zapytanie o zakup, tak aby dostawca mógł potwierdzić warunki zamówienia zakupu. Ten stan jest również używany w procesie inicjowanym przez akcję **Żądanie potwierdzenia**. W tym procesie dostawca jest proszony o potwierdzenie warunków zamówienia zakupu poprzez nawiązanie połączenia z systemem Twojej firmy i zarejestrowanie, czy potwierdza czy też odrzuca zamówienie.
-   **Potwierdzone** — To stan przypisywany po potwierdzeniu zamówienia. Zazwyczaj ten stan jest ostatnim stanem zatwierdzania przypisywanym do zamówienia.


<a name="see-also"></a>Informacje dodatkowe
--------

[Purchase order creation](purchase-order-creation.md)

[Zatwierdzanie i potwierdzanie zamówienia zakupu](purchase-order-approval-confirmation.md)

[Przyjęcie produktów względem zamówień zakupu](product-receipt-against-purchase-orders.md)

[Przegląd faktur od dostawcy](/dynamics365/operations/financials/accounts-payable/vendor-invoices-overview)


