---
title: Moduł karuzeli
description: W tym temacie opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: c2c5adc8ab2e0330f7b07e5153fd8332ab0203e5
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785244"
---
# <a name="carousel-module"></a>Moduł karuzeli

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł karuzeli służy do umieszczania wielu elementów promocyjnych w karuzeli, które mogą być przeglądane przez klientów. Jest to specjalny moduł kontenera, który obsługuje inne moduły. Na przykład sprzedawca może skorzystać z modułu karuzela na stronie głównej, aby zaprezentować wiele nowych produktów lub promocji.

Moduły główne i funkcji można dodawać w module karuzeli. Właściwości modułu karuzeli definiują sposób renderowania tych modułów.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Przykłady modułów karuzeli w e-Commerce

- Na stronie głównej można używać karuzeli, w której znajdują się wiele modułów promocyjnych.
- Na stronie szczegółów produktu można używać karuzeli, w której znajdują się wiele modułów promocyjnych.
- Karuzela może być używana na dowolnej stronie marketingowej w celu promowania wielu promocji lub produktów.

## <a name="carousel-module-properties"></a>Właściwości modułu karuzeli

| Nazwa właściwości             | Wartość                                | Opis |
|---------------------------|--------------------------------------|-------------|
| Autoodtwarzanie                  | **Prawda** lub **Fałsz**                | Jeśli wartość jest ustawiona na **prawda**, przejście między elementami w karuzeli następuje automatycznie. Jeśli wartość jest ustawiona na **fałsz**, nie następuje przejście, chyba że klient użyje klawiatury lub myszy do przechodzenia z jednego elementu do następnego. |
| Interwał przejścia slajdu | Wartość w sekundach                   | Interwał przejść między elementami. |
| Animacja przejścia      | **Slajd** lub **efekt zanikania**                | Efekt przejścia. |
| Szerokość                     | **Dopasuj do kontenera** lub **ekran wypełnienia** | Jeśli wartość jest ustawiona na **dopasowana do kontenera**, elementy wewnątrz karuzeli są ograniczone do szerokości karuzeli. Jeśli wartość jest ustawiona na **wypełnienie ekranu**, elementy nie są ograniczone do szerokości karuzeli, ale mogą przechodzić do trybu pełnoekranowego. Można zmienić wartość, aby uzyskać odpowiedni układ. |

## <a name="add-a-carousel-module-to-a-page"></a>Dodawanie modułu karuzeli do strony

Aby dodać moduł karuzeli do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Utwórz szablon strony o nazwie nazwa **szablon karuzeli**.
1. W **Głównym** gnieździe na stronie domyślnej dodaj moduł karuzeli.
1. Dodaj moduł główny do modułu karuzeli.
1. Dodaj moduł funkcji do modułu karuzeli.
1. Zaewidencjonuj szablon i opublikuj go. 
1. Za pomocą utworzonego właśnie szblonu karuzeli utwórz stronę o nazwie **strona karuzeli**.
1. W **Głównym** gnieździe na nowej stronie dodaj moduł karuzeli.
1. Umożliwia ustawienie właściwości **szerokość** modułu karuzela na **ekran wypełnienia**. 
1. Umożliwia ustawienie właściwości **animacji przejścia** na **slajd**.
1. Dodaj moduł główny do modułu karuzeli.
1. W module głównym dodaj obraz i nagłówek, a następnie wybierz opcję **Zapisz**.
1. Dodaj moduł funkcji do modułu karuzeli.
1. Umożliwia dodanie obrazu, nagłówka i akapitu tekstu w module funkcji.
1. Zapisz i zobacz podgląd strony. Na stronie powinna być wyświetlana karuzela zawierająca dwa moduły (moduł główny i moduł funkcji). Aby osiągnąć pożądany efekt, można zmienić dodatkowe właściwości dla karuzeli, głównego i modułów funkcji.
1. Zaewidencjonuj stronę i opublikuj ją.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł alertów](add-alert.md)

[Moduł zaawansowanego bloku zawartości](add-content-rich-block.md)

[Moduł umieszczania zawartości](add-content-placement-modules.md)

[Moduł funkcji](add-feature-module.md)

[Moduł bohatera](add-hero-module.md)

[Moduł odtwarzacza wideo](add-video-player.md)
