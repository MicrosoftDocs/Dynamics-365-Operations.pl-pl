---
title: Alerty
description: "Ten temat zawiera ogólne informacje alertach w programie Microsoft Dynamics 365 for Finance and Operations. Alerty pozwalają na bieżąco uzyskiwać informacje o zdarzeniach, które chcesz śledzić podczas dnia pracy."
author: tjvass
manager: AnnBe
ms.date: 07/16/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 38309e986c1d284ed63be760745b20a5415adb4c
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---

# <a name="alerts"></a>Alerty

[!include [banner](../includes/banner.md)]

## <a name="about-alerts"></a>Alerty — informacje
Alerty stanowią system powiadamiania o zdarzeniach krytycznych w programie Microsoft Dynamics 365 for Finance and Operations. Alerty pozwalają na bieżąco uzyskiwać informacje o zdarzeniach, które chcesz śledzić podczas dnia pracy. Można łatwo utworzyć własny zbiór reguł alertów dotyczących zaległych dostaw, usuniętych zamówień, zmian cen oraz innych zdarzeń, na które należy reagować.

W środowisku planowania zasobów przedsiębiorstwa (ERP) istnieje kilka typowych scenariuszy, gdzie można używać funkcji alertów zawartych w programie Finance and Operations. Oto kilka przykładów.

### <a name="scenario-1-create-an-alert-rule-for-new-sales-orders"></a>Scenariusz 1: tworzenie reguły alertu dla nowych zamówień sprzedaży
1. Otwórz stronę **Wszystkie zamówienia sprzedaży**.
2. W okienku akcji na karcie **Opcje** w grupie **Udostępnij** wybierz opcję **Utwórz alert niestandardowy**.
3. W oknie dialogowym **Utwórz regułę alertu** na skróconej karcie **Prześlij mi alert, gdy** w polu **Zdarzenie** zaznacz opcję **Rekord został utworzony**.

### <a name="scenario-2-create-an-alert-rule-for-postponement-of-a-delivery-date"></a>Scenariusz 2: tworzenie reguły alertu dla opóźnienia daty dostawy
1. Otwórz stronę **Wszystkie zamówienia zakupu**.
2. Zaznacz identyfikator zamówienia zakupu, aby przejdź do szczegółów zamówienia zakupu.
3. Rozwiń skróconą kartę **Nagłówek zamówienia zakupu**.
4. W okienku akcji na karcie **Opcje** w grupie **Udostępnij** wybierz opcję **Utwórz alert niestandardowy**.
5. W oknie dialogowym **Utwórz regułę alertu** na skróconej karcie **Prześlij mi alert, gdy** w polu **Pole** zaznacz opcję **Data dostawy**.
6. W polu **Zdarzenie** wybierz wartość **odroczono**.
    
Po zamknięciu okna dialogowego **Utwórz regułę alertu** reguła pojawi się na stronie **Zarządzaj regułami alertów**. Można użyć strony **Zarządzaj regułami alertów**, aby zaktualizować istniejące reguły alertów. Na przykład można zmodyfikować wyzwalacze zdarzeń oraz zaktualizować powiadomienia o zdarzeniach i daty ważności. Aby otworzyć stronę **Zarządzaj regułami alertów**, użyj przycisku **Prześlij mi alert** znajdującego się na karcie **Opcje** w okienku akcji.

## <a name="what-occurs-when-an-alert-rule-is-created"></a>Co się dzieje po utworzeniu reguły alertu?
Podczas tworzenia reguł alertów można skojarzyć wstępnie zdefiniowane zdarzenie z określonym polem. Może ono dotyczyć na przykład nadejścia dnia określonego w polu lub zmiany zawartości pola. Alternatywnie można skojarzyć zdarzenie z rekordami na konkretnej stronie. Na przykład rekord jest tworzony lub usuwany.

Gdy wybrane zdarzenie nastąpi dla określonego pola lub rekordu na stronie, zostanie Ci wysłany alert. Na przykład można utworzyć regułę, w której skojarzysz pole **Data dostawy** określonego wiersza zamówienia zakupu ze zdarzeniem **ta kwota była należna pewien czas temu**. Ustawiasz przedział czasu na pięć dni. W takim przypadku alert zostanie wysłany 5 dni po dacie dostawy towarów z tego wiersza zamówienia zakupu.

Ponadto reguły alertów można doprecyzować, ustawiając warunki. Na przykład możesz otrzymywać alerty o nowych zamówieniach zakupu, które są tworzone dla określonych kont dostawców.

## <a name="preparing-for-an-alert"></a>Przygotowywanie się do odbierania alertów
Przed utworzeniem reguły alertu musisz zdecydować, kiedy i w jakich sytuacjach chcesz otrzymywać alerty. Gdy już wiesz, o którym zdarzeniu chcesz otrzymywać powiadomienia, w programie Finance and Operations odszukaj stronę, na której pojawiają się dane wywołujące zdarzenie. Zdarzeniem może być nadejście określonego dnia lub wystąpienie konkretnej zmiany. W związku z tym należy odnaleźć stronę, gdzie jest podana data, znajduje się modyfikowane pole lub widać nowo tworzony rekord. Mając te informacje, można utworzyć regułę alertu.

## <a name="components-of-an-alert-rule"></a>Składniki reguły alertu
Reguła alertu ma pięć składników:

- **Zdarzenie** — zdarzeniem wyzwalającym regułę alertu może być nadejście określonego dnia lub wystąpienie konkretnej zmiany. Zdarzenia definiuje się na skróconej karcie **Wyślij alerty e-mail dotyczące zmian stanu zadania** w oknie dialogowym **Utwórz regułę alertu**.
- **Warunek** — na skróconej karcie **Prześlij mi alert dla** w oknie dialogowym **Utwórz regułę alertu** można wybrać zakres warunku, aby kontrolować, kiedy otrzymujesz alerty o zdarzeniach. Regułę można zastosować tylko do bieżącego rekordu lub do wszystkich rekordów widocznych na stronie. Jeśli reguła jest stosowana do wielu firm, można w opcji **Na poziomie organizacji** ustawić wartość **Tak**.
- **Wygaśnięcie reguły** — na skróconej karcie **Przesyłaj mi alerty do** w oknie dialogowym **Utwórz regułę alertu** można określić, jak długo reguła alertu powinna być aktywna.
- **Zawartość** — na skróconej karcie **Prześlij mi alert za pomocą** w oknie dialogowym **Utwórz regułę alertu** można określić tekst tematu i treść wiadomości, które mają być używane w komunikatach alarmowych.
- **Użytkownik** — na skróconej karcie **Adresat alertu** w oknie dialogowym **Utwórz regułę alertu** można określić, który użytkownik powinien otrzymywać komunikaty alarmowe. Domyślnie jest zaznaczony Twój identyfikator użytkownika.

    > [!NOTE]
    > Dostęp do tej opcji mają tylko administratorzy organizacji.

## <a name="email-notifications-from-alerts"></a>Powiadomienia pocztą e-mail z alertów
Funkcja powiadomień pocztą e-mail z alertów nie jest jeszcze obsługiwana. Zostanie wprowadzona w jednej z przyszłych aktualizacji.

