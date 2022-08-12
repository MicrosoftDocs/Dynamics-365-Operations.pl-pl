---
title: Omówienie alertów (zawiera wideo)
description: Ten artykuł zawiera ogólne informacje o alertach. Alerty pozwalają na bieżąco uzyskiwać informacje o zdarzeniach, które chcesz śledzić podczas dnia pracy.
author: RichdiMSFT
ms.date: 09/04/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: b81eb8e0be4c7d7357a6b8b7b5f0ac025b9ab8ca
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2022
ms.locfileid: "9124267"
---
# <a name="alerts-overview"></a>Omówienie alertów

[!include [banner](../includes/banner.md)]

## <a name="about-alerts"></a>Alerty — informacje
Alerty stanowią system zgłaszania zdarzeń krytycznych w systemie. Alerty pozwalają na bieżąco uzyskiwać informacje o zdarzeniach, które chcesz śledzić podczas dnia pracy. Można łatwo utworzyć własny zbiór reguł alertów dotyczących zaległych dostaw, usuniętych zamówień, zmian cen oraz innych zdarzeń, na które należy reagować.

W środowisku planowania zasobów przedsiębiorstwa (ERP) istnieje kilka typowych scenariuszy, gdzie można używać funkcji alertów. Oto kilka przykładów.

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

Przed utworzeniem reguły alertu musisz zdecydować, kiedy i w jakich sytuacjach chcesz otrzymywać alerty. Gdy już wiesz, o którym zdarzeniu chcesz otrzymywać powiadomienia, odszukaj stronę, na której pojawiają się dane wywołujące zdarzenie. Zdarzeniem może być nadejście określonego dnia lub wystąpienie konkretnej zmiany. W związku z tym należy odnaleźć stronę, gdzie jest podana data, znajduje się modyfikowane pole lub widać nowo tworzony rekord. Mając te informacje, można utworzyć regułę alertu.

## <a name="components-of-an-alert-rule"></a>Składniki reguły alertu

Reguła alertu ma pięć składników:

- **Zdarzenie** — zdarzeniem wyzwalającym regułę alertu może być nadejście określonego dnia lub wystąpienie konkretnej zmiany. Zdarzenia definiuje się na skróconej karcie **Wyślij alerty e-mail dotyczące zmian stanu zadania** w oknie dialogowym **Utwórz regułę alertu**.
- **Warunek** — na skróconej karcie **Prześlij mi alert dla** w oknie dialogowym **Utwórz regułę alertu** można wybrać zakres warunku, aby kontrolować, kiedy otrzymujesz alerty o zdarzeniach. Regułę można zastosować tylko do bieżącego rekordu lub do wszystkich rekordów widocznych na stronie. Jeśli reguła jest stosowana do wielu firm, można w opcji **Na poziomie organizacji** ustawić wartość **Tak**.
- **Wygaśnięcie reguły** — na skróconej karcie **Przesyłaj mi alerty do** w oknie dialogowym **Utwórz regułę alertu** można określić, jak długo reguła alertu powinna być aktywna.
- **Zawartość** — na skróconej karcie **Prześlij mi alert za pomocą** w oknie dialogowym **Utwórz regułę alertu** można określić tekst tematu i treść wiadomości, które mają być używane w komunikatach alarmowych.
- **Użytkownik** — na skróconej karcie **Adresat alertu** w oknie dialogowym **Utwórz regułę alertu** można określić, który użytkownik powinien otrzymywać komunikaty alarmowe. Domyślnie jest zaznaczony Twój identyfikator użytkownika.

    > [!NOTE]
    > Dostęp do tej opcji mają tylko administratorzy organizacji.

## <a name="videos"></a>Filmy wideo

### <a name="how-to-use-alerts-to-monitor-filtered-data"></a>Sposób używania alertów do monitorowania filtrowanych danych

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3DWZ3]

Film wideo [Sposób używania alertów do monitorowania filtrowanych danych](https://youtu.be/ZYKMcv6kl9s) (pokazany powyżej) znajduje się [na liście odtwarzania aplikacji finansowych i operacyjnych](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej na platformie YouTube.

### <a name="alert-rule-options"></a>Opcje reguł alertów

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E4PV]

Film wideo [Opcje reguł alertów](https://youtu.be/cpzimwOjicM) (widoczny powyżej) jest zawarty na [liście odtwarzania aplikacji finansowych i operacyjnych](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej na platformie YouTube.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
