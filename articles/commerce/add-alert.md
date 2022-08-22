---
title: Moduł transparentu promocyjnego
description: W tym artykule opisano moduł baneru promocyjnego i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
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
ms.openlocfilehash: fbde146923d1448e382cbf2458880f7e300f605c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279743"
---
# <a name="promo-banner-module"></a>Moduł transparentu promocyjnego

[!include [banner](includes/banner.md)]

W tym artykule opisano moduł baneru promocyjnego i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

Moduły baneru promocyjnego służą do wyświetlania wbudowanych komunikatów informacyjnych na stronie. Można ich używać do wyświetlania promocji na poziomie całej witryny wyświetlanych na wszystkich stronach witryny e-Commerce. 

Moduły baneru promocyjnego obsługują wiadomość SMS i łącze. Jeśli do modułu baneru promocyjnego jest dodawanych wiele wiadomości, staje się on wiodącym banerem karuzeli, który pozwoli klientom przechodzić między wszystkimi wiadomościami. 

Moduły baneru promocyjnego są sterowane danymi z systemu zarządzania zawartością (CMS) i mogą być umieszczane na dowolnej stronie.

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a>Przykłady użycia banerów promocyjnych w e-commerce

W nagłówku witryny można używać banerów promocyjnych do wyświetlania promocji lub komunikatów w całej witrynie, tak jak w poniższych przykładach.

„Roczna wyprzedaż kończy się za 10 dni”

„Zaoszczędź na zakupach do szkoły. Kup teraz.”

„Wyprzedaż na Święto Dziękczynienia!” 

Poniższy obraz przedstawia przykład baneru promocyjnego.

![Przykład modułu baneru promocyjnego.](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a>Właściwości modułu baneru promocyjnego

| Nazwa właściwości             | Wartość                              | opis |
|---------------------------|------------------------------------|-------------|
| Wiadomości transparentu           | Tekst i łącza                     | Szeroki wybór tekstu i łączy. |
| Autoodtwarzanie                  | **Prawda** lub **Fałsz**              | Wartość wskazująca, czy komunikaty są automatycznie przetwarzane, jeśli skonfigurowano wiele wiadomości. |
| Interwał przejścia slajdu | Liczba milisekund (ms)      | Interwał używany do cyklicznego przechodzenia między wiadomościami. |
| Zezwól na odrzucanie             | **Prawda** lub **Fałsz**              | Jeśli wartość jest ustawiona na **Prawda**, odbiorcy mogą anulować alert. |
| Pokazuj flipper karuzeli     | **Prawda** lub **Fałsz**              | Wartość wskazująca, czy mają być pokazywane flippery karuzeli, dzięki czemu odbiorcy mogą ręcznie przechodzić między różnymi elementami baneru. |
| Wyrównanie tekstu            | **Prawo**, **Lewo** lub **Środek** | Wyrównanie tekstu w module baner promocyjny. |
| Łącze                      | Adres URL                              | Adres URL opcjonalnego linku. |
|Wyrównanie tekstu             | **Prawo**, **Lewo** lub **Środek** | Ta właściwość jest dostępna jako rozszerzenie motywu w motywie Adventure Works. Pozwala użytkownikowi ustawić wyrównanie tekstu w banerze promocyjnym. |

> [!IMPORTANT]
> Kompozycja Adventure Works jest dostępna w Dynamics 365 Commerce w wersji 10.0.20.

## <a name="add-a-promo-banner-module-to-a-page"></a>Dodawanie modułu baneru promocyjnego do nowej strony 

Aby dodać moduł baneru promocyjnego do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon baneru promocyjnego**, a następnie wybierz **OK**.
1. W obszarze **Konspekt strony** dodaj moduł **Domyślna strona** do gniazda **Treść**. 
1. Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować. 
1. Za pomocą utworzonego właśnie szblonu alertu utwórz stronę o nazwie **Strona baneru promocyjnego**. 
1. W **Głównym** gnieździe na nowej stronie dodaj moduł kontenera. 
1. W okienku po prawej stronie określ wartość **Szerokości** jako **Wypełnij kontener**.
1. W obszarze **Konspekt strony** dodaj moduł baneru promocyjnego do modułu kontenerów.
1. W ustawieniach modułu banery promocyjnego dodaj co najmniej jedną wiadomość baneru. Każda wiadomość może zawierać tekst razem z łączem. Inne właściwości można edytować, jeśli moduł ma być dostosowany dalej.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. W górnej części strony powinien pojawić się alert z dodanym tekstem.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

> [!NOTE]
> Baner jest zazwyczaj używany w gnieździe nagłówka strony lub w gnieździe podnagłówków.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł karuzeli](add-carousel.md)

[Moduł bloku tekstu](add-content-rich-block.md)

[Moduł bloku zawartości](add-hero-module.md)

[Moduł odtwarzacza wideo](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
