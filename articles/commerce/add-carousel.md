---
title: Moduł karuzeli
description: W tym artykule opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 8bf9f7294dfbb4e16814dbdfb27bf646fcb5f4b1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275835"
---
# <a name="carousel-module"></a>Moduł karuzeli

[!include [banner](includes/banner.md)]

W tym artykule opisano moduły karuzeli i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

Moduł karuzeli służy do umieszczania wielu elementów promocyjnych (w tym obrazów) w obracającej się karuzeli banerów, które mogą być przeglądane przez klientów. Na przykład sprzedawca może skorzystać z modułu karuzela na stronie głównej, aby zaprezentować wiele nowych produktów lub promocji.

Moduły główne i bloku zawartości można dodawać w module karuzeli. Właściwości modułu karuzeli definiują sposób renderowania tych modułów.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Przykłady modułów karuzeli w e-Commerce

- Na stronie głównej można używać karuzeli, w której znajdują się wiele modułów promocyjnych.
- Na stronie szczegółów produktu można używać karuzeli, w której znajdują się wiele modułów promocyjnych.
- Karuzela może być używana na dowolnej stronie marketingowej w celu promowania wielu promocji lub produktów.

Poniższy obraz pokazuje przykład modułu karuzeli, który jest używany na stronie głównej. Ten moduł karuzeli zawiera wiele elementów bloków zawartości.

![Przykład modułu karuzeli.](./media/Hero.PNG)

## <a name="carousel-module-properties"></a>Właściwości modułu karuzeli

| Nazwa właściwości             | Wartość                 | opis |
|---------------------------|-----------------------|-------------|
| Autoodtwarzanie                  | **Prawda** lub **Fałsz** | Jeśli wartość jest ustawiona na **prawda**, przejście między elementami w karuzeli następuje automatycznie. Jeśli wartość jest ustawiona na **fałsz**, nie następuje przejście, chyba że klient użyje klawiatury lub myszy do przechodzenia z jednego elementu do następnego. |
| Interwał przejścia slajdu | Wartość w sekundach    | Interwał przejść między elementami. |
| Typ zmiany stanu           | **Slajd** lub **efekt zanikania** | Efekt przejścia między elementami. |
| Ukryj ramię karuzeli     | **Prawda** lub **Fałsz** | Jeśli wartość jest ustawiona na **Prawda**, ramiona karuzeli i wskaźnik sekwencji są ukryte. |
| Zezwalaj na odrzucanie karuzeli    | **Prawda** lub **Fałsz** | Jeśli wartość jest ustawiona na **Prawda**, użytkownicy mogą anulować karuzelę. |

## <a name="add-a-carousel-module-to-a-page"></a>Dodawanie modułu karuzeli do strony

Aby dodać moduł karuzeli do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon karuzeli**, a następnie wybierz **OK**.
1. W miejscu **Treść** dodaj moduł **Strona domyślna**.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.  
1. Za pomocą utworzonego właśnie szblonu karuzeli utwórz stronę o nazwie **Strona karuzeli**.
1. W **Głównym** gnieździe na nowej stronie dodaj moduł kontenera. 
1. W okienku po prawej stronie określ wartość **Szerokości** jako **ekran wypełnienia**.
1. W obszarze **Konspekt strony** dodaj moduł karuzeli do modułu kontenerów.
1. W module kontenera dodaj moduł bloku zawartości. Umożliwia ustawienie właściwości modułu blok zawartości przez udostępnienie **nagłówka**, **łącza**, **układu** i innych właściwości.
1. Dodaj i skonfiguruj inny moduł bloku zawartości.
1. W razie potrzeby skonfiguruj dodatkowe właściwości dla modułu karuzeli.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. Na stronie powinna być wyświetlana karuzela zawierająca dwa moduły (moduł główny i moduł funkcji). Aby osiągnąć pożądany efekt, można zmienić dodatkowe właściwości dla karuzeli, głównego i modułów funkcji.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł transparentu promocyjnego](add-alert.md)

[Moduł bloku tekstu](add-content-rich-block.md)

[Moduł bloku zawartości](add-hero-module.md)

[Moduł odtwarzacza wideo](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
