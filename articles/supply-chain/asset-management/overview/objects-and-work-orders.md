---
title: Składniki majątku i zlecenia pracy
description: W tym temacie opisano składniki majątku i zlecenia pracy w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4be7d3b77f72a9d79047d31b46dcabcb2bf09d12
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351568"
---
# <a name="assets-and-work-orders"></a>Składniki majątku i zlecenia pracy

[!include [banner](../../includes/banner.md)]

 

W tym temacie opisano składniki majątku i zlecenia pracy w module Zarządzanie składnikami majątku. Składniki majątku i zlecenia pracy są centralnymi częściami modułu Zarządzanie składnikami majątku. *Składnik majątku* jest maszyną lub częścią maszyny, która wymaga ciągłej konserwacji i serwisowania. Składniki majątku mogą być tworzone w strukturze hierarchicznej i mogą być powiązane z lokalizacjami czynności konserwacyjnych. Zadania konserwacji mogą być planowane na wszystkich poziomach struktury składników majątku.

Dla każdego składnika majątku są skonfigurowane różne dane, takie jak informacje o produkcie i specyfikacja składnika majątku oraz wymagane plany konserwacji. Poniższa ilustracja przedstawia omówienie danych o składnikach majątku i przynależności składników majątku do typów zadań. Czerwony tekst jest używany dla przykładów, które pokazują dziedziczenie i zależności.

![Diagram pokazujący dane elementów składnika majątku powiązane z typami stanowisk.](media/05-overview-image.png)

Każde zlecenie pracy ma typ zlecenia, np. konserwacja zapobiegawcza, konserwacja naprawcza lub inspekcja. Zlecenie pracy zawiera jedno lub więcej zadań zlecenia pracy. Każde zadanie zlecenia pracy definiuje zadanie, które należy wykonać na składniku majątku i pokrewnym typie zadania. Przykłady powiązanych typów stanowisk obejmują remont po 10 000 km, 50 000 km, 1 roku oraz inspekcję bezpieczeństwa. Jedno zlecenie pracy może być powiązane z wieloma składnikami majątku.

Na poniższej ilustracji przedstawiono omówienie kluczowych danych w zleceniu pracy.

![Diagram przedstawiający kluczowe dane w zleceniu pracy.](media/06-overview-image.png)

Zlecenie pracy może być powiązane z innym zamówieniem pracy, a typy zadań mogą zawierać kolejne zadania, tworzące zlecenie pracy. Ogólnie, nie istnieją żadne zależności między zleceniami pracy. Dzięki temu mogą one zmienić swój stan cyklu życia zlecenia pracy i mogą być planowane niezależnie od siebie.

Zlecenia pracy mogą być tworzone na różne sposoby, które odnoszą się do konserwacji korekcyjnej, zapobiegawczej lub reaktywnej. Można także ręcznie tworzyć zlecenia pracy. Na poniższej ilustracji przedstawiono omówienie procesu automatycznego lub ręcznego tworzenia zleceń pracy.

![Diagram pokazujący automatyczne lub ręczne tworzenie zleceń pracy.](media/07-overview-image.png)

Aby zaplanować i uruchomić zadanie konserwacji w zleceniu pracy, należy wykonać kilka czynności. Na poniższej ilustracji przedstawiono omówienie przetwarzania w zleceniu pracy.

![Diagram pokazujący przegląd przetwarzania zlecenia pracy.](media/08-overview-image.png)

> [!NOTE]
> Generalnie w trakcie pracy w Dynamics 365 Supply Chain Management i module **Zarządzania składnikami majątku** wybierz opcję **Nowy**, aby utworzyć nowy rekord, wybierz **Edytuj**, aby zaktualizować istniejący rekord, a następnie wybierz **Zapisz**, aby zapisać nowy lub edytować dane.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]