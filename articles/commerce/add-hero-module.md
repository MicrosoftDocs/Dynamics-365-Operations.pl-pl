---
title: Moduł bohatera
description: W tym temacie opisano moduły bohatera i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: c43704992e9759e7207f1b1c9bc958449daa6d1d
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785404"
---
# <a name="hero-module"></a>Moduł bohatera

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano moduły bohatera i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł bohatera jest używany do marketingowych produktów lub promocji przy użyciu kombinacji obrazów i tekstu. Na przykład sprzedawca może dodać moduł bohatera do strony głównej witryny e-Commerce, aby promować nowy produkt i zwrócić uwagę odbiorców.

Moduł bohatera jest sterowany przez dane z systemu zarządzania zawartością (CMS). Jest to samodzielny moduł, który nie zależy od innych modułów na stronie. Moduł Hero można umieścić na dowolnej stronie witryny, w której detalista chce dokonać obrotu lub promować coś (na przykład produktów, sprzedaży lub funkcji).

## <a name="examples-of-hero-module-in-e-commerce"></a>Przykłady modułów bohatera w e-Commerce

- Moduł bohatera może być używany na stronie głównej witryny e-Commerce w celu wyróżnienia promocji i nowych produktów.
- Moduł bohatera może być używany na stronie Szczegóły produktu w celu zaprezentowania informacji o produkcie.
- W module bohatera można umieścić wiele modułów bohatera w celu wyróżnienia wielu produktów lub promocji.

## <a name="hero-module-properties"></a>Właściwości modułu bohatera

| Nazwa właściwości  | Wartości | Opis |
|----------------|--------|-------------|
| Wizerunek          | Plik obrazu | Obraz może służyć do pokazania produktu lub promocji. Obraz można przekazać do galerii obrazów lub można użyć istniejącego obrazu. |
| Nagłówek        | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Każdy moduł bohatera może mieć nagłówek. Domyślnie w nagłówku jest używany znacznik nagłówka **H2**. Jednak znacznik można zmienić, aby spełniał wymagania dotyczące dostępności. |
| Akapit      | Tekst akapitu | Moduły bohatera obsługują tekst akapitu w formacie RTF. Obsługiwane są pewne podstawowe funkcje tekstu sformatowanego, takie jak pogrubiony, podkreślony, kursywa i hiperłącza. Niektóre z tych możliwości mogą być zastąpione przez motyw strony stosowany do modułu. |
| Link           | Tekst łącza, adres URL łącza, dostęp do bogatych aplikacji internetowych (ARIA) **i Otwórz łącze na nowej karcie** | Moduły bohatera obsługują łącza do jednego lub wielu „wywołań akcji”. Jeśli zostanie dodane łącze, tekst łącza, adres URL i etykieta ARIA są wymagane. Etykiety ARIA powinny być opisowe w celu spełnienia wymagań dotyczących ułatwień dostępu. Łącza można tak skonfigurować, aby były otwierane na nowej karcie. |
| Umiejscowienie tekstu | **Lewy górny**, **prawy górny**, **górny środkowy**, **lewy dolny**, **dolny prawy**, **dolny środkowy**, **lewy środkowy**, **prawy środkowy** lub **środkowy** | Właściwość ta określa pozycję obrazu w odniesieniu do tekstu. Jeśli na przykład zaznaczona jest opcja po **prawej** stronie, obraz pojawi się po prawej stronie tekstu. |
| Motyw tekstu     | **Jasny** lub **ciemny** | Schemat kolorów może zostać zdefiniowany dla tekstu na podstawie obrazu tła. Na przykład, jeśli obraz ma ciemne tło, można zastosować motyw jasny, aby tekst był bardziej widoczny i spełniał proporcje kolorów dla celów ułatwień dostępu. |
| Gradient       | **Prawda** lub **Fałsz** | Gradient można zastosować do obrazu w celu spełnienia współczynnika kontrastu kolorów w celach ułatwień dostępu. |

## <a name="add-a-hero-module-to-a-new-page"></a>Dodawanie modułu bohatera do nowej strony

Aby dodać moduł bohatera do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Szablonów**i utwórz szablon strony o nazwie **szablon bohatera**.
1. W **Głównym** gnieździe na stronie domyślnej dodaj moduł bohatera.
1. Zaewidencjonuj szablon i opublikuj go.
1. Za pomocą utworzonego właśnie szblonu bohatera utwórz stronę o nazwie **strona bohatera**.
1. Na domyślnej stronie wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** w obszarze **Wybierz moduły** wybierz moduł bohatera i wybierz przycisk **OK**.
1. W drzewie konspektu po lewej wybierz moduł bohatera.
1. W panelu właściwości po prawej wybierz **Dodaj obraz**. Następnie należy wybrać istniejący obraz lub przekazać nowy obraz.
1. Wybierz **Nagłówek**.
1. W oknie dialogowym **nagłówek** dodaj tekst nagłówka, wybierz poziom nagłówka, a następnie kliknij przycisk **OK**.
1. W obszarze **tekst sformatowany**,dodaj tekst w miarę potrzeb.
1. Wybierz **łącze dodaj akcję**.
1. W oknie dialogowym **łącze akcji** dodaj tekst łącza, adres URL łącza oraz etykietę Aria dla łącza, a następnie kliknij przycisk **OK**.
1. Zapisz stronę i wyświetl podgląd zmian.
1. Zaewidencjonuj stronę i opublikuj ją.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł alertów](add-alert.md)

[Moduł karuzeli](add-carousel.md)

[Moduł zaawansowanego bloku zawartości](add-content-rich-block.md)

[Moduł umieszczania zawartości](add-content-placement-modules.md)

[Moduł funkcji](add-feature-module.md)

[Moduł odtwarzacza wideo](add-video-player.md)
