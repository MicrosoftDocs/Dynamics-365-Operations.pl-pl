---
title: Śledzenie podróży przychodzących i wysyłek kontenerów wysyłkowych
description: W tym temacie wyjaśniono, w jaki sposób można użyć strony Śledzenie przesyłki przychodzącej do śledzenia postępów podróży i podróży kontenerów wysyłkowych.
author: sherry-zheng
manager: tfehr
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMContainerActivityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 678f2b6cda0592e0393bb15f372cb4be84778932
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501253"
---
# <a name="track-inbound-voyages-and-shipping-container-journeys"></a>Śledzenie podróży przychodzących i wysyłek kontenerów wysyłkowych

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Strona **Śledzenie przesyłki** przychodzącej pozwala śledzić postępy podróży i podróży kontenerów wysyłkowych. Każdy przejazd i podróż są rozbijane według *działań*, z których każdy ma własny wiersz na stronie. Strona ta służy do wyświetlania i wprowadzania szacowanych dat oraz rzeczywistych dat według działań.

Zwykle w zależności od ustawień w [Centrum kontroli śledzenia](delivery-information-setup.md#tracking-control-center) w tych działaniach jest automatycznie pokazywana szacowana data docelowego miejsca docelowego. Również w zależności od ustawień data końcowa zazwyczaj aktualizuje datę dostawy lub potwierdzoną datę w wierszach zamówienia zakupu. W przypadku wierszy zamówienia przeniesienia można skonfigurować system do aktualizowania daty przyjęcia.

Aby otworzyć stronę **Śledzenie przesyłek przychodzących**, przejdź do **Koszt z wyładunkiem \> Śledzenie \> Śledzenie przesyłek przychodzących**.

## <a name="filter-the-activities-list"></a>Filtrowanie listy działań

Pola **Podróży** i **Kontener wysyłkowy** można użyć w górnej części strony **Śledzenie przesyłek przychodzących**, aby przefiltrować stronę, aby wyświetlała tylko działania skojarzone z wybraną podróży i/lub kontenerem wysyłkowym.

## <a name="update-tracking-information"></a>Zaktualizuj informacje o śledzeniu

Aby zaktualizować harmonogram podróży lub podróży, wprowadź datę rozpoczęcia pierwszej czynności. Zostanie wówczas zaktualizowana szacowana data zakończenia ostatniego działania. Konfiguracja poszczególnych szablonów etapowych i podróży w [Centrum kontroli śledzenia](delivery-information-setup.md#tracking-control-center) określa szacowane czasy realizacji. Szacowane daty zakończenia używają czasu realizacji od daty rozpoczęcia działania. Następnie podczas rejestrowanie rzeczywistej daty zakończenia data rozpoczęcia następnego działania jest aktualizowana do tej samej daty, co rzeczywista data zakończenia poprzedniego działania. Rzeczywisty czas realizacji jest aktualizowany, dzięki czemu można dokonać porównania i analizy. Dodatkowe notatki można wprowadzać w polu **Notatka**.

Kolejność działań w siatce jest określana na podstawie kolejności czynności w odpowiednim szablonie podróży. Jeśli kolejność podróży się zmieni, kontrola śledzenia również zostanie włączona.

Daty dla wszystkich kontenerów można zaktualizować, wybierając opcję **Aktualizuj datę rozpoczęcia** lub **Rzeczywistą datę zakończenia** w okienku akcji. Alternatywnie możesz wprowadzić daty według kontenera na przesyłce. Dzięki temu kontenery mogą być dzielone w środowisku wielodniowym.

## <a name="buttons-on-the-action-pane"></a>Przyciski w okienku akcji

Za pomocą przycisków w okienku akcji na stronie **Śledzenia przesyłki przychodzącej** można pracować z przychodzącymi wysyłkami i podróżami. W poniższej tabeli przedstawiono dostępne przyciski.

| Przycisk | opis |
|---|---|
| Edycja | Edycja podróży lub wysyłki kontenerem wysyłkowym. |
| Nowa | Utwórz nową podróż lub wysyłkę kontenerem wysyłkowym. |
| Usuwanie | Usuń wybraną podróż lub wysyłkę kontenerem wysyłkowym. |
| Aktualizuj datę rozpoczęcia | Aktualizuj datę rozpoczęcia działania dla wszystkich kontenerów w podróży. Po zaktualizowaniu daty rozpoczęcia określonego działania lub etapu podróży kolejne szacunkowe daty rozpoczęcia są aktualizowane na podstawie określonego czasu realizacji. |
| Aktualizuj rzeczywistą datę zakończenia | Aktualizuj datę zakończenia działania dla wszystkich kontenerów w podróży. Po zaktualizowaniu daty zakończenia określonego działania, kolejne działania są aktualizowane w oparciu o określony czas realizacji. |
| Dodaj działania | Ręcznie dodaj aktywność do podróży. Można na przykład dodać działanie dotyczące fumigacji. Dodanie może spowodować zmianę potwierdzonej daty dostawy towarów na statku lub podróży. Gdy czynność jest dodawana do podróży, szacunkowe dni nie są wprowadzane do czasu zaktualizowania daty rozpoczęcia etapu podróży. |

## <a name="information-and-settings-on-the-overview-tab"></a>Informacje i ustawienia na karcie Przegląd

Na karcie **Przegląd** znajduje się lista wszystkich działań należących do podróży i/lub kontenera wysyłkowego wybranego u góry strony. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego działania.

| Pole | opis |
|---|---|
| Etap | Identyfikator etapu dla działania, zgodnie z szablonem podróży. |
| Metoda dostawy | Oczekiwana metoda realizacji działania. |
| Działanie | To pole zwykle identyfikuje zadanie lub zadanie skojarzone z działaniem. Typowe przykłady: *W drodze* i *Odprawa*. |
| opis | Dłuższy opis czynności. |
| Rozpoczęcie | W tym polu jest początkowo wyświetlana szacowana data rozpoczęcia działania. Jednak po wprowadzeniu rzeczywistej daty zakończenia poprzedniego działania jest ona rzeczywistą datą rozpoczęcia. To pole służy do określania szacowanej daty końcowej na podstawie czasu realizacji. |
| Szacowana data końcowa | Wartość w tym polu jest obliczana na podstawie daty rozpoczęcia i czasu realizacji. Zwykle nie edytujesz tej wartości bezpośrednio. |
| Rzeczywista data zakończenia | Użytkownik powinien zaktualizować to pole jak najszybciej po zakończeniu działania. Zostanie wówczas zaktualizowany rzeczywisty czas realizacji. |
| Szacowana liczba dni | Szacowany czas (w dniach) wymagany do ukończenia działania. |
| Rzeczywista liczba dni | Rzeczywisty czas (w dniach) wymagany do zakończenia działania. |
| Banknot | W tym polu można dodawać różne notatki i szczegóły dotyczące działania. |

## <a name="information-and-settings-on-the-general-tab"></a>Informacje i ustawienia na karcie Ogólne

Karta **Ogólne** zawiera informacje o nocie wybranej na karcie **Przegląd**. Powtarza się ona niektóre informacje wyświetlane na karcie **Przegląd**, ale zawiera również dodatkowe informacje o wybranej nocie.
