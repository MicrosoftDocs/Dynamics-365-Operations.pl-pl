---
title: Moduł karuzeli
description: W tym temacie opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: f279d7db0a92df9e64b1d3f6ca01c65ca1478d79
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025788"
---
# <a name="carousel-module"></a>Moduł karuzeli


[!include [banner](includes/banner.md)]

W tym temacie opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł karuzeli służy do umieszczania wielu elementów promocyjnych (w tym obrazów) w obracającej się karuzeli banerów, które mogą być przeglądane przez klientów. Na przykład sprzedawca może skorzystać z modułu karuzela na stronie głównej, aby zaprezentować wiele nowych produktów lub promocji.

Moduły główne i bloku zawartości można dodawać w module karuzeli. Właściwości modułu karuzeli definiują sposób renderowania tych modułów.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Przykłady modułów karuzeli w e-Commerce

- Na stronie głównej można używać karuzeli, w której znajdują się wiele modułów promocyjnych.
- Na stronie szczegółów produktu można używać karuzeli, w której znajdują się wiele modułów promocyjnych.
- Karuzela może być używana na dowolnej stronie marketingowej w celu promowania wielu promocji lub produktów.

## <a name="carousel-module-properties"></a>Właściwości modułu karuzeli

| Nazwa właściwości             | Wartość                 | Opis |
|---------------------------|-----------------------|-------------|
| Autoodtwarzanie                  | **Prawda** lub **Fałsz** | Jeśli wartość jest ustawiona na **prawda**, przejście między elementami w karuzeli następuje automatycznie. Jeśli wartość jest ustawiona na **fałsz**, nie następuje przejście, chyba że klient użyje klawiatury lub myszy do przechodzenia z jednego elementu do następnego. |
| Interwał przejścia slajdu | Wartość w sekundach    | Interwał przejść między elementami. |
| Typ zmiany stanu           | **Slajd** lub **efekt zanikania** | Efekt przejścia między elementami. |
| Ukryj ramię karuzeli     | **Prawda** lub **Fałsz** | Jeśli wartość jest ustawiona na **Prawda**, ramiona karuzeli i wskaźnik sekwencji są ukryte. |
| Zezwalaj na odrzucanie karuzeli    | **Prawda** lub **Fałsz** | Jeśli wartość jest ustawiona na **Prawda**, użytkownicy mogą anulować karuzelę. |

## <a name="add-a-carousel-module-to-a-page"></a>Dodawanie modułu karuzeli do strony

Aby dodać moduł karuzeli do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Utwórz szablon strony o nazwie nazwa **szablon karuzeli**.
1. W miejscu **Treść** dodaj moduł **Strona domyślna**.
1. Zaewidencjonuj szablon i opublikuj go. 
1. Za pomocą utworzonego właśnie szblonu karuzeli utwórz stronę o nazwie **strona karuzeli**.
1. W **Głównym** gnieździe na nowej stronie dodaj moduł kontenera. 
1. W okienku po prawej stronie określ wartość **Szerokości** jako **ekran wypełnienia**.
1. W obszarze **Konspekt strony** dodaj moduł karuzeli do modułu kontenerów.
1. W module kontenera dodaj moduł bloku zawartości. Umożliwia ustawienie właściwości modułu blok zawartości przez udostępnienie **nagłówka**, **łącza**, **układu** i innych właściwości.
1. Dodaj i skonfiguruj inny moduł bloku zawartości.
1. W razie potrzeby skonfiguruj dodatkowe właściwości dla modułu karuzeli.
1. Zapisz i zobacz podgląd strony. Na stronie powinna być wyświetlana karuzela zawierająca dwa moduły (moduł główny i moduł funkcji). Aby osiągnąć pożądany efekt, można zmienić dodatkowe właściwości dla karuzeli, głównego i modułów funkcji.
1. Zakończ edytowanie strony i opublikuj go.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł baneru promocyjnego](add-alert.md)

[Moduł bloku zaawansowanej zawartości](add-content-rich-block.md)

[Moduł bloku zawartości](add-hero-module.md)

[Moduł odtwarzacza wideo](add-video-player.md)
