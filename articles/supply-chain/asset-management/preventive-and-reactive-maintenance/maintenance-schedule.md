---
title: Harmonogram konserwacji
description: W tym artykule wyjaśniono harmonogram konserwacji w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectCalendarCreateWO, EntAssetObjectCalendarListPagePoolsOpen, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePreviewPart, EntAssetObjectCalendarEdit, EntAssetObjectCalendarAdjust, EntAssetObjectCalendarDiscard, EntAssetObjectCalendarInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4089400817d6dd8454c85e594eff05314d3fd72e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858019"
---
# <a name="maintenance-schedule"></a>Harmonogram konserwacji

[!include [banner](../../includes/banner.md)]

 

Harmonogram konserwacji zawiera listę wszystkich oczekiwanych planów konserwacji, zgłoszeń serwisowych i serii czynności konserwacji. Niektóre wiersze harmonogramu mogły zostać przekonwertowane na zlecenia pracy.

Cztery widoki harmonogramu konserwacji są nieco inne, w zależności od tego, które wiersze harmonogramu konserwacji mają być widoczne.

| Element menu                  | Opis zawartości                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wszystkie harmonogramy konserwacji       | Wszystkie wiersze harmonogramu konserwacji są wyświetlane.     |
| Mój harmonogram składników majątku        | Na tej liście są wyświetlane wszystkie wiersze harmonogramu konserwacji zawierające składniki majątku zainstalowane w lokalizacjach czynności konserwacyjnych, z którymi powiązany jest pracownik (skonfigurowany w [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md)). |
| Otwieranie wierszy harmonogramu konserwacji | Wiersze harmonogramu konserwacji ze stanem „utworzone” — oznacza, że nie zostały jeszcze przekształcone na zlecenie pracy lub odrzucone — są wyświetlane na tej liście.                                            |
| Otwieranie puli harmonogramów konserwacji | Na tej liście są wyświetlane wiersze harmonogramu konserwacji powiązane z pulą zleceń pracy.                                                                                                                  |

>[!NOTE]
>Jeśli wiersz harmonogramu konserwacji jest uwzględniony w kilku pulach zleceń pracy (zapoznaj się z [Pule zleceń pracy](../work-orders/work-order-pools.md)), dla każdej puli w polu **Otwieranie puli harmonogramów konserwacji** jest wyświetlany jeden rekord. W ten sposób można zoptymalizować opcje filtrowania w pulach zleceń pracy.

Aby otworzyć wierszy harmonogramu konserwacji

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Harmonogram konserwacji** > **Wszystkie harmonogramy konserwacji** lub **Otwieranie wierszy harmonogramu konserwacji** lub **Otwieranie puli harmonogramów konserwacji**.

2. Aby zaktualizować harmonogram konserwacji, należy kliknąć **Plan konserwacji** lub **Serie czynności konserwacyjnych**. 

3. Wiersz harmonogramu konserwacji można edytować, zaznaczając go i klikając przycisk **Edytuj**. Można na przykład łatwo zaktualizować poziom usług lub pracownika odpowiedzialnego za zadanie. Można edytować tylko wiersze harmonogramu konserwacji, które nie zostały jeszcze połączone ze zleceniem pracy.

4. Wiersz harmonogramu konserwacji można usunąć, zaznaczając go na stronie listy i klikając przycisk **Usuń.**

5. Wiersz harmonogramu konserwacji można odrzucić, zaznaczając go na stronie listy i klikając przycisk **Odrzuć.** Ta funkcja jest przydatna, jeśli na przykład składnik majątku ma plan obsługi technicznej 2 000 km i plan obsługi technicznej 10 000 km. Następnie użytkownik może chcieć odrzucić wiersz utworzony na podstawie planu konserwacji 2 000 km, gdy jest on zgodny z 10 000 km, 20 000 km, 30 000 km itd. Jeśli odrzucisz wiersz harmonogramu konserwacji związany z planem eksploatacji, wiersz ten nigdy nie będzie wyświetlany po zaplanowaniu planu konserwacji.

6. Można wybrać kilka wierszy planowania obsługi technicznej we **Wszystkie harmonogramy konserwacji** eksploatacji i kliknąć opcję **Pula zleceń pracy**, jeśli wszystkie wybrane wiersze mają zostać uwzględnione w tej samej puli zleceń pracy.

7. Można wybrać kilka wierszy harmonogramu obsługi we **Wszystkie harmonogramy konserwacji** lub **Otwieranie wierszy harmonogramu konserwacji** albo **Otwieranie puli harmonogramów konserwacji** i kliknąć przycisk **Koryguj harmonogram**, jeśli należy wprowadzić takie same korekty w kilku wierszach. Można zmienić oczekiwane daty rozpoczęcia i zakończenia, poziom usług oraz odpowiedzialną za nią grupę pracowników obsługi lub odpowiedzialną obsługę techniczną związane z wybranymi wierszami harmonogramu obsługi.

- Jeśli wiersz harmonogramu konserwacji został powiązany ze zleceniem pracy, identyfikator zlecenia pracy zostanie wyświetlony w polu **Zlecenie pracy**.  
- W szczegółowym widoku **Wszystkie składniki majątku** > skrócona karta **Plany konserwacji składnika majątku**, można wybierać plany konserwacji dla składnika majątku. Późniejsze usunięcie wiersza planu konserwacji lub serii czynności konserwacyjnych związanej ze składnikiem majątku w menu **Wszystkie składniki majątku** powoduje również automatyczne usunięcie wszystkich harmonogramów konserwacji ze stanem „Utworzono”, które zostały utworzone na podstawie tego planu konserwacji lub serii czynności konserwacyjnych. Przejrzyj również [Tworzenie składnika majątku](../objects/create-an-object.md)

Na poniższej ilustracji pokazano stronę z listą **Wszystkie harmonogramy konserwacji**.

![Rysunek 1.](media/16-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]