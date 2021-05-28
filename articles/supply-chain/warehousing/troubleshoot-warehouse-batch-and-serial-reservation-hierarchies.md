---
title: Rozwiązywanie problemów z hierarchiami rezerwacji partii i numerów seryjnych w magazynie
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z hierarchiami rezerwacji, które używają wymiarów wsadowych lub seryjnych.
author: perlynne
ms.date: 3/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 3/12/2021
ms.openlocfilehash: 1cd4883cdd95a97f821e0103da910e2c0346a08d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022553"
---
# <a name="troubleshoot-warehouse-batch-and-serial-reservation-hierarchies"></a>Rozwiązywanie problemów z hierarchiami rezerwacji partii i numerów seryjnych w magazynie

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z hierarchiami rezerwacji, które używają wymiarów wsadowych lub seryjnych.

Aby uzyskać więcej informacji, zobacz [Elastyczne zasady rezerwacji wymiarów na poziomie magazynu](flexible-warehouse-level-dimension-reservation.md).

Hierarchia rezerwacji pozycji określa wymagania wymiarów magazynowania, które muszą być spełnione, aby przypisać lokalizację do zamówienia popytu. Wymiary te można opisać jako *wymiary powyżej lokalizacji* dla wszystkich wymiarów, które muszą zostać spełnione przed przypisanie lokalizacji, oraz *wymiarów poniżej lokalizacji* dla wymiarów, które można alokować po przypisaniu lokalizacji do zlecenia popytu. Te hierarchie rezerwacji są nazywane także hierarchiami rezerwacji *nad partiami* i *partiami poniżej*, lub hierarchiami rezerwacji *serii nadrzędnych* i *serii podrzędnych*.

Zapasy można pomyślnie zaalokować tylko wtedy, gdy nie ma przerw w wymiarach powyżej lokalizacji. Na przykład w hierarchii rezerwacji *nad partią* oczekiwano wymiarów **Lokalizacji,** **Magazyn** i **Numer partii**, które mają być określone w zamówieniu popytu. Brak dowolnego z tych wymiarów spowoduje niepowodzenie procesu alokacji. Natomiast w hierarchii rezerwacji *partia poniżej* lub *seria poniżej* może być określony w zamówieniu popytu, ale proces alokacji tego nie wymaga.

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a>Pojawia się następujący komunikat o błędzie: „Aby przypisać do grupy czynności, wiersze ładunku muszą określać wymiary powyżej lokalizacji. Aby przypisać te wymiary, zarezerwuj i ponownie utwórz wiersz ładunku”.

### <a name="issue-description"></a>Opis problemu

W przypadku użycia towaru, który ma rezerwację *partię powyżej* hierarchii rezerwacji, polecenie **Zwolnij do magazynu** na stronie **Pulpitu planowania ładunku** dla wyzwolenia ilości częściowej nie działa. Pojawia się ten komunikat o błędzie i nie utworzono żadnej pracy dla ilości częściowej.

Jeśli jednak używasz towaru, który ma hierarchię rezerwacji *partia poniżej*, możesz zwolnić ładunek dla ilości częściowej ze strony **Środowisko pracy planowania ładunku**.

### <a name="issue-cause"></a>Przyczyna problemu

Jeśli wymiar zostanie umieszczony powyżej wymiaru **Lokalizacji** w hierarchii rezerwacji, musi zostać on określony przed zwolnieniem do magazynu. Ilości częściowe nie mogą zostać zwolnione, jeśli nie określono co najmniej jednego wymiaru powyżej **Lokalizacji**.

## <a name="the-auto-reservation-prompt-for-a-batch-number-is-triggered-even-though-there-is-available-inventory"></a>Monit o automatyczną rezerwację dla numeru partii jest wyzwalany, nawet jeśli istnieją dostępne zapasy.

### <a name="issue-description"></a>Opis problemu

Gdy używasz towaru, który ma hierarchię rezerwacji *partia powyżej* w magazynie, w którym nie włączono procesów magazynowych, a rezerwacja automatyczna jest włączona, monit automatycznej rezerwacji o numer partii jest wyświetlany, nawet jeśli tylko jedna partia jest dostępne do pobrania.

Jednak w przypadku używania tego samego towaru w magazynie, w którym są włączone procesy magazynowe, monit o automatyczną rezerwację nie jest wyświetlany.

### <a name="issue-cause"></a>Przyczyna problemu

Jeśli hierarchia rezerwacji jest zdefiniowana jako *partia nad* lub *seria nad*, w zamówieniach popytu zawsze musi być określony wymiar, do których istnieje odwołanie (**Numer partii** lub **Numer seryjny**). Procesy magazynowe mogą być w stanie wypełnić informacje, jeśli jest dostępny jeden numer partii lub numer seryjny. Jednak magazyn nie jest włączony dla procesów magazynowych, użytkownik musi zawsze określić wszystkie wymiary powyżej opcji **Lokalizacja**.

## <a name="slotting-templates-that-have-the-consider-on-hand-slot-criterion-dont-consider-current-on-hand-inventory-for-batch-enabled-items"></a>Szablony gniazda, dla których kryterium Uwzględnianie dostępnych zapasów nie są uwzględniane bieżące dostępne zapasy dla towarów, dla których włączono partię.

Aby uzyskać więcej informacji, zajrzyj do [Rozpisywanie na przedziały w magazynie](warehouse-slotting.md).

### <a name="issue-description"></a>Opis problemu

Szablony gniazda, dla których kryterium *Uwzględnianie dostępnych zapasów* nie są uwzględniane bieżące dostępne zapasy dla towarów *partii powyżej*. Są one rozważane tylko wtedy, gdy numer partii jest określony w wierszu zamówienia sprzedaży.

Jednak w przypadku towarów stanu *partii poniżej* aktualny stan dostępnych zapasów jest traktowany zgodnie z oczekiwaniami.

### <a name="issue-cause"></a>Przyczyna problemu

Nagłówek szablonu schowania można zdefiniować dla strategii *Zamówione*, *Zarezerwowane* lub *Zwolniony popyt*. W strategii *Zamówiono* popytu obowiązują te same wymagania hierarchii rezerwacji, które dotyczą rezerwacji lub zwalniania do procesów magazynowych. Dlatego w przypadku towarów, które mają hierarchie rezerwacji *partia powyżej* i *seria poniżej*, numer partii lub numer seryjny musi być określony w zamówieniu popytu (sprzedaż lub przeniesienie). Strategii *Zarezerwowanego* popytu można również użyć w celu wybrania numeru partii lub numeru seryjnego przed wygenerowaniem popytu gniazda magazynowego.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
