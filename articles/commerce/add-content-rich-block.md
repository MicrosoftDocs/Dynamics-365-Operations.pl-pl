---
title: Moduł bloku zaawansowanej zawartości
description: W tym temacie opisano moduły bloku zaawansowanej zawartości i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: c6527ad00e74fa105f3873036eb56557b98b05aa
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414876"
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

Poniższy obraz pokazuje przykład modułu bloku tekstu, który jest używany na stronie głównej.

![Przykład modułu bloku tekstu](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a>Właściwości modułu bloku zaawansowanej zawartości

| Nazwa właściwości     | Wartość                                            | opis |
|-------------------|--------------------------------------------------|-------------|
| Tekst sformatowany         | Tekst sformatowany                                        | Tekst akapitu. Obsługiwane są pewne podstawowe funkcje tekstu sformatowanego, takie jak pogrubiony, podkreślony i kursywa. |
| Niestandardowa nazwa klasy | Nazwa klasy arkuszy stylów kaskadowych (CSS)        | Nazwa niestandardowej klasy CSS, którą projektant chce sformatować w tym module. Nazwa klasy powinna być zdefiniowana w pakiecie kompozycji. |
| Rozmiar czcionki         | **Małe**, **średnie**, **duże** lub **XL** | Wybierz rozmiar czcionki treści. |

## <a name="add-a-text-block-module-to-a-page"></a>Dodawanie bloku zaawansowanej zawartości do nowej strony

Aby dodać moduł blokuzaawansowanej zawartości do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** przejdź do **Szablon zawartości**.
1. W gnieździe **Treść** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Strona domyślna** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Wybierz szablon** wybierz opcję **Szablon zawartości**. W sekcji **Nazwa strony** przejdź do **Strona zawartości**, a następnie wybierz przycisk **OK**.
1. Na nowej stronie wybierz gniazdo **Główne**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W okienku właściwości modułu kontenerów określ właściwość **Szerokość** na **Wypełnij kontener**.
1. W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **AddDodaj moduł** wybierz moduł **Blok tekstu** i wybierz przycisk **OK**. 
1. W okienku właściwości modułu blok tekstu Dodaj tekst do pola **Tekst sformatowany**.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł transparentu promocyjnego](add-alert.md)

[Moduł karuzeli](add-carousel.md)

[Moduł bloku zawartości](add-hero-module.md)

[Moduł odtwarzacza wideo](add-video-player.md)

