---
title: Moduł zaawansowanego bloku zawartości
description: W tym temacie opisano moduły zaawansowanego bloku zawartości i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 27dabb425b3c9a3015ffc54ff3c0e50b7ee11749
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785428"
---
# <a name="content-rich-block-module"></a>Moduł zaawansowanego bloku zawartości

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano moduły zaawansowanego bloku zawartości i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł zaawansowanego bloku zawartości jest specjalnym kontenerem, w którym można umieścić co najmniej jeden element zaawansowanego bloku zawartości. Dla zawartości tekstowej na stronie używany jest moduł zaawansowanego bloku zawartości. Ta zawartość może mieć wartość informacyjną lub promocyjną.

Moduły zaawansowanego bloku zawartości są sterowane danymi z systemu zarządzania zawartością (CMS) i mogą być umieszczane na dowolnej stronie. Są to moduły autonomiczne, które nie są zależne od kontekstu strony ani innych modułów.

## <a name="examples-of-content-rich-block-modules-in-e-commerce"></a>Przykłady modułów zaawansowanego bloku zawartości w e-Commerce

Moduły zaawansowanego bloku zawartości mogą być używane w następujący sposób:

* W celu zaprezentowania funkcji produktu na stronie Szczegóły produktu.
* Do celów informacyjnych na dowolnej stronie. Można na przykład wyjaśnić zalety programów lojalnościowych, opisać zasady wysyłki i zwrotów, odpowiedzi na często zadawane pytania lub dostarczyć zawartość „o nas”.
* , Aby dodać niestandardowe komunikaty na stronie szczegółów produktu. (na przykład „bezpłatna wysyłka zamówień o wartości ponad $50”).
* Dla roszczeń i szczegółów dotyczących kontaktu na stronach szczegółów produktu, na stronach koszyka, na stronach do realizacji transakcji oraz na innych stronach (np. „Wysyłka i zwroty podlegają zasadom sklepu”).

## <a name="content-rich-block-module-properties"></a>Właściwości modułu zaawansowanego bloku zawartości

| Nazwa właściwości     | Wartość                                 | Właściwość |
|-------------------|---------------------------------------|----------|
| Liczba kolumn | Liczba z zakresu od **1** do **4**     | Liczba kolumn w bloku bogatym zawartości. Może zawierać do czterech kolumn. |
| Szerokość             | **Wypełnij kontener** lub **ekran wypełnienia** | Jeśli wartość jest ustawiona na **Wypełnij kontener**, elementy wewnątrz kontenera są ograniczone do szerokości kontenera. Jeśli wartość jest ustawiona na **wypełnienie ekranu**, elementy nie są ograniczone do szerokości kontenera, ale mogą przechodzić do trybu pełnoekranowego. Można zmienić wartość, aby uzyskać odpowiedni układ. |

## <a name="content-rich-block-item-module-properties"></a>Właściwości modułu elementu zaawansowanego bloku zawartości

| Nazwa właściwości | Wartość          | Opis |
|---------------|----------------|-------------|
| Akapit     | Tekst akapitu | Tekst towarzyszący każdego elementu zaawansowanego bloku zawartości. Obsługiwane są pewne podstawowe funkcje tekstu sformatowanego, takie jak pogrubiony, podkreślony i kursywa. |

## <a name="add-a-content-rich-block-module-to-a-page"></a>Dodawanie modułu zaawansowanego bloku zawartości do strony

Aby dodać moduł zaawansowanego bloku zawartości do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Utwórz szablon strony o nazwie nazwa **szablon zawartości**.
1. W **Głównym** gnieździe na stronie domyślnej dodaj moduł zaawansowanego bloku zawartości.
1. Zaewidencjonuj szablon i opublikuj go.
1. Za pomocą utworzonego właśnie szblonu zawartości utwórz stronę o nazwie **strona zawartości**.
1. W **Głównym** gnieździe na nowej stronie dodaj moduł zaawansowanego bloku zawartości.
1. W właściwościach modułu zaawansowanego bloku zawartości określ liczbę kolumn równą **2**.
1. W module zaawansowanego bloku zawartości wybierz opcję **Dodaj moduł** i dodaj element zaawansowanego bloku zawartości (na przykład **Element1**).
1. W nowym elemencie zaawansowanego bloku zawartości dodaj tekst akapitu.
1. W module zaawansowanego bloku zawartości wybierz opcję **Dodaj moduł** i dodaj element zaawansowanego bloku zawartości (na przykład **Element2**).
1. W nowym elemencie zaawansowanego bloku zawartości dodaj tekst akapitu.
1. Zapisz stronę i wyświetl podgląd zmian. W widoku dwóch kolumn powinny być widoczne dwa bloki zaawansowanej zawartości.
1. Zaewidencjonuj stronę i opublikuj ją.

> [!NOTE]
> Jeśli zostanie dodany element trzeciego bloku zaawansowanej zawartości, zostanie on umieszczony w stosie poniżej dwóch wcześniej dodanych elementów. Zmieniając liczbę kolumn i elementów w kontenerze, można uzyskać różne układy dla zawartości tekstowej.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł alertów](add-alert.md)

[Moduł karuzeli](add-carousel.md)

[Moduł umieszczania zawartości](add-content-placement-modules.md)

[Moduł funkcji](add-feature-module.md)

[Moduł bohatera](add-hero-module.md)

[Moduł odtwarzacza wideo](add-video-player.md)

