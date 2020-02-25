---
title: Moduł bloku zaawansowanej zawartości
description: W tym temacie opisano moduły bloku zaawansowanej zawartości i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: fc5b2fa35633b1ce7f7ffefacec318e14fa8db3f
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025604"
---
# <a name="text-block-module"></a>Moduł bloku zaawansowanej zawartości


[!include [banner](includes/banner.md)]

W tym temacie opisano moduły bloku zaawansowanej zawartości i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł bloku tekstu to moduł służący do dodawania zawartości tekstowej. Ta zawartość może mieć wartość informacyjną lub promocyjną.

Moduły bloku zaawansowanej zawartości są sterowane danymi z systemu zarządzania zawartością (CMS) i mogą być umieszczane na dowolnej stronie. Są to moduły autonomiczne, które nie są zależne od kontekstu strony ani innych modułów.

## <a name="examples-of-text-block-modules-in-e-commerce"></a>Przykłady modułów bloku zaawansowanej zawartości w e-Commerce

Moduły bloku zaawansowanej zawartości mogą być używane w następujący sposób:

* W celu zaprezentowania funkcji produktu na stronie Szczegóły produktu.
* Do celów informacyjnych na dowolnej stronie. Można na przykład wyjaśnić zalety programów lojalnościowych, opisać zasady wysyłki i zwrotów, odpowiedzi na często zadawane pytania lub dostarczyć zawartość „o nas”.
* , Aby dodać niestandardowe komunikaty na stronie szczegółów produktu. (na przykład „bezpłatna wysyłka zamówień o wartości ponad $50”).
* Dla roszczeń i szczegółów dotyczących kontaktu na stronach szczegółów produktu, na stronach koszyka, na stronach do realizacji transakcji oraz na innych stronach (np. „Wysyłka i zwroty podlegają zasadom sklepu”).

## <a name="text-block-module-properties"></a>Właściwości modułu bloku zaawansowanej zawartości

| Nazwa właściwości     | Value                                            | Opis |
|-------------------|--------------------------------------------------|-------------|
| Tekst sformatowany         | Tekst sformatowany                                        | Tekst akapitu. Obsługiwane są pewne podstawowe funkcje tekstu sformatowanego, takie jak pogrubiony, podkreślony i kursywa. |
| Niestandardowa nazwa klasy | Nazwa klasy arkuszy stylów kaskadowych (CSS)        | Nazwa niestandardowej klasy CSS, którą projektant chce sformatować w tym module. Nazwa klasy powinna być zdefiniowana w pakiecie kompozycji. |
| Rozmiar czcionki         | **Małe**, **średnie**, **duże** lub **XL** | Wybierz rozmiar czcionki treści. |

## <a name="add-a-text-block-module-to-a-page"></a>Dodawanie bloku zaawansowanej zawartości do nowej strony

Aby dodać moduł blokuzaawansowanej zawartości do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Utwórz szablon strony o nazwie nazwa **szablon zawartości**. 
1. W miejscu **Treść** dodaj moduł **Strona domyślna**.
1. Zakończ edytowanie szablonu i opublikuj go.
1. Za pomocą utworzonego właśnie szblonu zawartości utwórz stronę o nazwie **strona zawartości**.
1. W **Głównym** gnieździe na nowej stronie dodaj moduł kontenera.
1. W okienku właściwości modułu kontenerów określ właściwość **Szerokość** na **Wypełnij kontener**.
1. W module bloku zaawansowanej zawartości dodaj moduł kontenera. 
1. W okienku właściwości modułu blok tekstu Dodaj tekst do pola **Tekst sformatowany**.
1. Zakończ edytowanie strony i opublikuj go.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł baneru promocyjnego](add-alert.md)

[Moduł karuzeli](add-carousel.md)

[Moduł bloku zawartości](add-hero-module.md)

[Moduł odtwarzacza wideo](add-video-player.md)

