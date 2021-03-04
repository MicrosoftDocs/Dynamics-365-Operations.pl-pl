---
title: Moduł bloku zawartości
description: W tym temacie opisano moduły bloku zawartości i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7a8b1c214ba31b7c47cecbe67bef493f5fa450fc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414879"
---
# <a name="content-block-module"></a>Moduł bloku zawartości


[!include [banner](includes/banner.md)]

W tym temacie opisano moduły bloku zawartości i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł bloku zawartości jest używany do marketingowych produktów lub promocji przy użyciu kombinacji obrazów i tekstu. Na przykład sprzedawca może dodać moduł bloku zawartości do strony głównej witryny e-Commerce, aby promować nowy produkt i zwrócić uwagę odbiorców.

Moduł bloku zawartości jest sterowany przez dane z systemu zarządzania zawartością (CMS). Jest to samodzielny moduł, który nie zależy od innych modułów na stronie. Moduł bloku zawartości można umieścić na dowolnej stronie witryny, w której detalista chce dokonać obrotu lub promować coś (na przykład produktów, sprzedaży lub funkcji).

## <a name="examples-of-content-block-module-in-e-commerce"></a>Przykłady modułów bloku zawartości w e-Commerce

- Moduł bloku zawartości może być używany na stronie głównej witryny e-Commerce w celu wyróżnienia promocji i nowych produktów.
- Moduł bloku zawartości może być używany na stronie Szczegóły produktu w celu zaprezentowania informacji o produkcie.
- W module bloku zawartości można umieścić wiele modułów bohatera w celu wyróżnienia wielu produktów lub promocji.

## <a name="content-block-modules-and-themes"></a>Moduły i motywy bloków zawartości

Moduły bloku zawartości mogą obsługiwać różne układy i style oparte na motywie. Na przykład kompozycja Fabrikam obsługuje trzy warianty układu modułu bloku zawartości: Hero, funkcja i kafelek. Układ Hero pokazuje obraz w tle z nakładką tekstową. Układ funkcji pokazuje obraz i tekst obok siebie. Układ kafelków umożliwia stosowanie wielu bloków zawartości w formacie kafelka.

Ponadto motyw może udostępniać różne właściwości dla każdego układu. Programista motywu może utworzyć więcej układów o większej liczbie stylów przy użyciu modułu bloku zawartości.

Poniższy obraz przedstawia przykład modułu bloku zawartości z układem Hero.

![Przykład modułu bohatera](./media/Hero.PNG)

Poniższy obraz przedstawia przykład modułu bloku zawartości z układem funkcji.

![Przykłady modułów funkcji](./media/Feature.PNG)

## <a name="content-block-module-properties"></a>Właściwości modułu bloku zawartości

| Nazwa właściwości  | Wartości | Opis |
|----------------|--------|-------------|
| Wizerunek          | Plik obrazu | Obraz może służyć do pokazania produktu lub promocji. Obraz można przekazać do galerii obrazów lub można użyć istniejącego obrazu. |
| Nagłówek        | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Każdy moduł bohatera może mieć nagłówek. Domyślnie w nagłówku jest używany znacznik nagłówka **H2**. Jednak znacznik można zmienić, aby spełniał wymagania dotyczące dostępności. |
| Akapit      | Tekst akapitu | Moduły bohatera obsługują tekst akapitu w formacie RTF. Obsługiwane są pewne podstawowe funkcje tekstu sformatowanego, takie jak pogrubiony, podkreślony, kursywa i hiperłącza. Niektóre z tych możliwości mogą być zastąpione przez motyw strony stosowany do modułu. |
| Link           | Tekst łącza, adres URL łącza, dostęp do bogatych aplikacji internetowych (ARIA) **i Otwórz łącze na nowej karcie** | Moduły bohatera obsługują łącza do jednego lub wielu „wywołań akcji”. Jeśli zostanie dodane łącze, tekst łącza, adres URL i etykieta ARIA są wymagane. Etykiety ARIA powinny być opisowe w celu spełnienia wymagań dotyczących ułatwień dostępu. Łącza można tak skonfigurować, aby były otwierane na nowej karcie. |

## <a name="content-block-module-properties-exposed-by-the-fabrikam-theme"></a>Właściwości modułu bloku zawartości dostępne w motywie Fabrikam 

| Nazwa właściwości  | Wartości | Opis |
|----------------|--------|-------------|
| Umiejscowienie tekstu | **Lewo**, **Prawo**, **Środek** | Właściwość ta określa pozycję tekstu w odniesieniu do obrazu. Dotyczy tylko układu Hero. |
| Motyw tekstu     | **Jasny** lub **ciemny** | Schemat kolorów może zostać zdefiniowany dla tekstu na podstawie obrazu tła. Na przykład, jeśli obraz ma ciemne tło, można zastosować motyw jasny, aby tekst był bardziej widoczny i spełniał proporcje kolorów dla celów ułatwień dostępu. Dotyczy tylko układu Hero.|
| Umiejscowienie obrazu       | **Lewy**, **prawy** | Właściwość ta określa, czy obraz powinien znajdować się po lewej czy po prawej stronie tekstu. Dotyczy tylko układu funkcji.  |

## <a name="add-a-content-block-module-to-a-new-page"></a>Dodawanie modułu zaawansowanego bloku zawartości do nowej strony

Aby dodać moduł bohatera do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Szablonów** i utwórz szablon strony o nazwie **Szablon bloku zawartości**.
1. W **Głównym** gnieździe na stronie domyślnej dodaj moduł bohatera.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Za pomocą utworzonego właśnie szablonu Hero utwórz stronę o nazwie **Strona bloku zawartości**.
1. Na domyślnej stronie wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** w obszarze **Wybierz moduły** wybierz moduł bohatera i wybierz przycisk **OK**.
1. W drzewie konspektu po lewej wybierz moduł bloku zawartości.
1. W panelu właściwości po prawej wybierz **Dodaj obraz**. Następnie należy wybrać istniejący obraz lub przekazać nowy obraz.
1. Wybierz **Nagłówek**.
1. W oknie dialogowym **nagłówek** dodaj tekst nagłówka, wybierz poziom nagłówka, a następnie kliknij przycisk **OK**.
1. W obszarze **tekst sformatowany**,dodaj tekst w miarę potrzeb.
1. Wybierz **Dodaj łącze**.
1. W oknie dialogowym **Łącze** dodaj tekst łącza, adres URL łącza oraz etykietę Aria dla łącza, a następnie kliknij przycisk **OK**.
1. Wybierz układ **Hero**.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować. 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł transparentu promocyjnego](add-alert.md)

[Moduł karuzeli](add-carousel.md)

[Moduł bloku tekstu](add-content-rich-block.md)

[Moduł odtwarzacza wideo](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]