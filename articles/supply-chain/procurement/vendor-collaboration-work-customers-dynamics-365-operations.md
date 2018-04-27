---
title: "Współpraca dostawców z odbiorcami"
description: "W tym temacie opisano używanie portalu współpracy z dostawcami w programie Microsoft Dynamics 365 for Finance and Operations do pracy z zamówieniami zakupu i monitorowania zapasów konsygnacyjnych."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 4252112272e2f86c2c18dc399a713bf652e4228e
ms.contentlocale: pl-pl
ms.lasthandoff: 03/26/2018

---

# <a name="vendor-collaboration-with-customers"></a>Współpraca z odbiorcami przy użyciu modułu Współpraca z dostawcami

[!INCLUDE [banner](../includes/banner.md)]

W tym temacie opisano używanie portalu współpracy z dostawcami do zarządzania współpracą z odbiorcami w programie Microsoft Dynamics 365 for Finance and Operations. Dostawcy mogą ukończyć szereg procesów biznesowych z następujących obszarów roboczych:

- **Potwierdzenie zamówienia zakupu** — monitorowanie i odpowiadanie na zamówienia zakupu.
- **Składanie ofert przez dostawców** — wyświetlanie zapytań ofertowych (ZO) i odpowiadanie na nie przez wprowadzanie ofert.
- **Informacje o dostawcy** — wyświetlanie i aktualizowanie danych głównych dostawcy.
- **Fakturowanie** — praca z fakturami. Ten temat nie dotyczy obszaru roboczego **Fakturowanie**. Aby uzyskać więcej informacji o tym obszarze roboczym, zobacz [Obszar roboczy fakturowania w portalu współpracy z dostawcami](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md).

Dostawcy mogą także monitorować informacje o zapasach konsygnacyjnych.

## <a name="working-with-pos-in-the-purchase-order-confirmation-workspace"></a>Praca z zamówieniami zakupu w obszarze roboczym Potwierdzenie zamówienia zakupu.

Obszar roboczy **Potwierdzenie zamówienia zakupu** pozwala odpowiadać na zamówienia zakupu wysłane Ci do przeglądu. Umożliwia także wyświetlanie informacji o zamówieniach zakupu oczekujących na interwencję odbiorcy oraz zamówieniach zakupu, które zostały potwierdzone, ale są nadal otwarte.

W obszarze roboczym **Potwierdzenie zamówienia zakupu** istnieją trzy listy:

- **Zamówienia zakupu do przeglądu** — na tej liście znajdują się zamówienia sprzedaży, które zostały Ci wysłane i oczekują na Twoją odpowiedź. Po udzieleniu odpowiedzi zamówienia są usuwane z listy. Jeśli odbiorca wyśle Ci nową wersję zamówienia zakupu, zanim udzielisz odpowiedzi na poprzednią wersję, zobaczysz tylko najnowszą wersję.
- **Oczekiwanie na akcję odbiorcy** — ta lista zawiera wszystkie zamówienia zakupu, na jest już Twoja odpowiedź, ale których odbiorca jeszcze nie potwierdził. Jeśli zaakceptujesz zamówienie zakupu, możesz je monitorować na tej liście, dopóki jego stan nie zmieni się na **Potwierdzone**. Jeśli odrzucisz zamówienie zakupu lub zaakceptujesz je ze zmianami, możesz je monitorować w tym miejscu, dopóki klient nie wyśle nowej wersji.
- **Otwarte potwierdzone zamówienia zakupu** — ta lista zawiera wszystkie zamówienia zakupu dla swojego klienta, które znajdują się w stanie **Potwierdzone**. Kiedy produkty lub usługi zostaną całkowicie przyjęte względem zamówienia zakupu, zamówienia jest usuwane z listy.

Do pracy z zamówieniami zakupu można użyć następujących stron:

- **Zamówienia zakupu do przeglądu** — ta strona zawiera te same informacje, co lista **Zamówienia zakupu do przeglądu** w obszarze roboczym. Zobacz opis we wcześniejszej części tego tematu.
- **Historia potwierdzeń zamówień zakupu przez dostawcę** — ta strona zawiera wszystkie zamówienia zakupu i wszystkie ich wersje, które zostały wysłane do dostawcy. Zawiera także wszystkie odpowiedzi otrzymane od dostawcy.
- **Otwarte potwierdzone zamówienia zakupu** Ta strona zawiera te same informacje, co lista **Otwarte potwierdzone zamówienie zakupu** w obszarze roboczym. Zobacz opis we wcześniejszej części tego tematu.
- **Wszystkie potwierdzone zamówienia zakupu** — ta strona zawiera wszystkie zamówienia zakupu, które zostały potwierdzone. Zamówienia zakupu na tej stronie obejmują zamówienia zakupu, dla których odebrano produkty lub usługi. Ta lista może służyć do monitorowania, za które zamówienia zakupu można wysłać faktury.

### <a name="responding-to-pos"></a>Odpowiadanie na zamówienia zakupu

Zamówienia zakupu wysłane Ci przez odbiorcę do przeglądu są wyświetlane w obszarze roboczym **Potwierdzenie zamówienia zakupu** i na stronie **Zamówienia zakupu do przeglądu**. Po otwarciu zamówienia zakupu można je zaakceptować, odrzucić lub zaakceptować ze zmianami. W nagłówku zamówienia zakupu lub w poszczególnych wierszach mogą istnieć załączniki. Ponadto można dołączyć informacje do swojej odpowiedzi w nagłówku zamówienia zakupu lub w poszczególnych wierszach. Na przykład możesz zasugerować użycie towaru zastępczego w jednym z wierszy.

Możesz wyświetlić podgląd zamówienia zakupu i wydrukować je jako plik PDF za pomocą opcji **Podgląd/drukuj**. Można także użyć akcji **Wyświetl wymiary**, aby ukryć lub wyświetlić następujące kolumny wymiarów: **Oddział**, **Magazyn**, **Kolor**, **Rozmiar**, **Styl** i **Konfiguracja**. 

Jeśli użyjesz opcji **Zaakceptuj ze zmianami**, możesz zaakceptować lub odrzucić poszczególne wiersze. W wierszach można także wprowadzać następujące zmiany:

- Zmiana dat lub ilości. Aby zaktualizować potwierdzoną datę dostawy we wszystkich wierszach, użyj opcji **Aktualizuj datę dostawy** w nagłówku zamówienia zakupu.
- Podział wierszy dla różnych dat dostawy lub ilości.
- Zastąpienie towaru. W sekcji **Szczegóły wiersza** wprowadź opis i numer towaru w polu **Zewnętrzny**.

Nie można zmienić informacji o cenach ani opłat, ale za pomocą notatek można zasugerować ich modyfikacje.

Jeśli odbiorca wyśle Ci nową wersję zamówienia, będzie ona miała sufiks wersji wskazujący, że jest to zmodyfikowana wersja zamówienia zakupu, które zostało wcześniej wysłane. Strona **Historia potwierdzeń zamówień zakupu przez dostawcę** pozwala śledzić historię każdego zamówienia.

## <a name="monitoring-consignment-inventory"></a>Monitorowanie zapasów konsygnacyjnych

Jeśli używasz zapasów konsygnacyjnych, możesz w interfejsie współpracy z dostawcami wyświetlać informacje na następujących stronach:

- **Zamówienia zakupu zużywające zapasy konsygnacyjne** — zamówienia zakupu dla zapasów konsygnacyjnych są generowane, gdy odbiorca przejmuje własność zapasów. Zamówienia zakupu konsygnacyjnego są widoczne tylko na tej stronie. Nie są one umieszczane na stronie **Wszystkie potwierdzone zamówienia zakupu**.
- **Produkty odebrane z zapasów konsygnacyjnych** — na tej stronie znajduje się lista wszystkich transakcji, w których własność produktów została przeniesiona na firmę zużywającą zapasy. Możesz używać tych informacji do fakturowania odbiorcy.
- **Dostępne zapasy konsygnacyjne** — na tej stronie są pokazane dostępne zapasy konsygnacyjne będące własnością Twojej firmy, które znajdują się na stanie w magazynie odbiorcy.

## <a name="working-with-rfqs-in-the-vendor-bidding-workspace"></a>Praca z ZO w obszarze roboczym Składanie ofert przez dostawców

Obszar roboczy **Składanie ofert przez dostawców** umożliwia wyświetlenie ZO, do których zaproszono Twoją firmę w celu udzielenia odpowiedzi. Możesz także odpowiedzieć na ZO. 

Obszar roboczy pokazuje także wszystkie uzyskane lub utracone ZO. Ponadto, jeżeli system jest skonfigurowany dla sektora publicznego, ten obszar roboczy zawiera dostępne publicznie ZO.

### <a name="viewing-rfqs"></a>Przeglądanie ZO

Otwórz obszar roboczy **Składanie ofert przez dostawców**, aby uzyskać dostęp do następujących informacji:

- Wybierz opcję **Nowe zaproszenia do składania ofert**, aby zobaczyć ZO, do których zaproszono Twoją firmę w celu udzielenia odpowiedzi. W tym miejscu można wyświetlić ZO i rozpocząć proces składania oferty. Można także sprawdzić zmienione ZO, dla których należy przesłać nową ofertę.
- Wybierz opcję **Zwrócone oferty**, aby zobaczyć ZO, które odbiorca zwrócił Ci, aby umożliwić podanie dodatkowych informacji lub zaktualizować ofertę.
- Wybierz opcję **Oferty w toku**, aby zobaczyć ZO, nad którymi Twoja firma lub osoba ją reprezentująca pracuje, ale jeszcze ich nie przesłała.
- Wybierz opcję **Wybrane oferty**, aby zobaczyć, gdy klient przyznał co najmniej jedną pozycję wiersza w Twojej ofercie.
- Wybierz opcję **Przegrane oferty**, aby zobaczyć oferty, w których wszystkie wiersze zostały odrzucone.
- Wybierz łącze **Zapytania ofertowe**, aby zobaczyć listę zaproszeń ZO oraz wszelkie przesłane oferty wszystkich odbiorców. Strona **Zapytania ofertowe** zawiera listę wszystkich ZO, w które zaangażowany jest dostawca. Można wyszukiwać według stanu.
- Wybierz łącze **Odrzucone oferty**, aby zobaczyć listę wszystkich ZO, w których osoba kontaktowa dostawcy nie złożyła oferty.

### <a name="working-with-rfqs-that-are-publicly-available"></a>Praca z publicznie dostępnymi ZO

Osoby pracujące w sektorze publicznym mogą zobaczyć otwarte i wygasłe ZO udostępnione publicznie.

- Wybierz łącze **Otwarte opublikowane zapytania ofertowe**, aby zobaczyć listę otwartych ZO dostępnych publicznie. Otwarte ZO to takie, które jeszcze nie wygasło. Datę i godzinę ważności można znaleźć w nagłówku ZO.

    Jeżeli zaproszono Cię do złożenia oferty, to samo ZO można znaleźć na stronie **Nowe zaproszenia do składania ofert**. Czasami chcesz złożyć ofertę w otwartym ZO, ale nie zaproszono Cię do złożenia oferty. W takim przypadku możesz zaprosić się samodzielnie,pod warunkiem, że odbiorca włączył samodzielne zapraszanie dotyczące sprawy ZO.

- Wybierz łącze **Zamknięte opublikowane zapytania ofertowe**, aby zobaczyć listę zamkniętych ZO dostępnych publicznie. Zamknięte ZO to takie, które wygasło. Datę i godzinę ważności można znaleźć w nagłówku ZO.

    Zamknięte ZO zawiera wszystkie oferty dostawców do poziomu wiersza. Przyznawanie lub odrzucanie ofert jest uwzględniane w zamkniętym ZO. Dostępne są także wszystkie załączniki zawarte w ofercie.

**Uwaga:** Ta funkcja jest dostępna tylko wtedy, gdy włączono konfigurację sektora publicznego.

### <a name="bidding"></a>Składanie ofert

- Kliknij przycisk **Oferta**, aby rozpocząć składanie oferty w ZO.

    Jeżeli edycja pól oferty jest włączona w nagłówkach i wierszach ZO, można wprowadzić ofertę bezpośrednio w siatce wierszy. Należy także uwzględnić wszelkie dodatkowe informacje o ofercie, które należy dodać w szczegółach wiersza.

    Po rozpoczęciu pracy nad ofertą zostanie ona wyświetlona w sekcji **Oferty w toku**.

    Ofertę można zapisać w dowolnej chwili przed upłynięciem daty ważności. Następnie można powrócić do niej później w celu zakończenia i przesłania. Po przesłaniu oferty można ją wycofywać i aktualizować do upłynięcia daty ważności.

- Wybierz opcję **Resetuj na podstawie ZO**, aby zresetować dane wprowadzone dla oferty i przywrócić pierwotne ZO. Można zresetować nagłówek lub wiersz.
- Wybierz opcję **Dodaj alternatywę** lub **Usuń alternatywę** w siatce wierszy, aby pracować z alternatywami.

    Niektóre ZO zezwalają na oferty alternatywne. Oferty alternatywne można określić tylko dla wierszy typu **Kategoria**, ponieważ nie można dodawać określonych towarów jako alternatyw. 

- Wybierz opcję **Załącznik ZO** lub **Załącznik wierszy RFQ**, aby otworzyć załącznik dodany przez odbiorcę do ZO. Wybierz opcję **Załączniki ofert** lub **Załączniki wierszy ofert**, aby przekazać załączniki razem z ofertą.

    Mogą istnieć kwestionariusze, na które należy odpowiedzieć przed złożeniem oferty.

- Wybierz opcję **Odrzuć**, jeżeli nie chcesz składać oferty. Po wybraniu opcji **Odrzuć** nie można wycofać akcji ani wprowadzić oferty.

Jeśli ZO zostało zmienione, należy wprowadzić nową ofertę. Informacje o poprawce można znaleźć na karcie **Poprawki** strony ZO. Zmienione ZO są widoczne na stronie **Nowe zaproszenia do składania ofert**.

## <a name="accessing-vendor-master-data-in-the-vendor-information-workspace"></a>Uzyskiwanie dostępu do danych głównych odbiorcy w obszarze roboczym Informacje o dostawcy

Jako dostawca możesz uzyskać dostęp do części informacji, które klient przechowuje w rekordzie głównym dostawcy. Pozwala to zapewnić aktualność informacji. Aby zaktualizować informacje, musisz mieć rolę administratora dostawcy (zewnętrznego).

Dostępne informacje to nazwa dostawcy, adres, informacje kontaktowe, osoby kontaktowe i ich informacje kontaktowe, numery identyfikacyjne, numery identyfikacji podatkowej, kategorie zaopatrzenia zatwierdzone do sprzedaży odbiorcy przez dostawcę oraz informacje o certyfikatach.

## <a name="see-also"></a>Informacje dodatkowe

[Zarządzanie użytkownikami portalu współpracy z dostawcami](manage-vendor-collaboration-users.md)

