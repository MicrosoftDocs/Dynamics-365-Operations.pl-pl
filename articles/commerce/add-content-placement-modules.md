---
title: Moduł umieszczania zawartości
description: W tym temacie omówiono moduły rozmieszczania treści i elementów umieszczania treści oraz opisano sposób dodawania ich do stron witryny w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 1b64e930628c969334ff6e643ba23b77445e6e4c
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785307"
---
# <a name="content-placement-module"></a>Moduł umieszczania zawartości

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie omówiono moduły rozmieszczania treści i elementów umieszczania treści oraz opisano sposób dodawania ich do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł umieszczania zawartości to specjalny kontener, w którym inne moduły mogą być umieszczone wewnątrz określonego układu. Moduły umieszczania zawartości obsługują następujące typy modułów jako moduły podrzędne: element umieszczania zawartości, pozycja powitalna konta, pozycja zamówienia konta, pozycja listy życzeń konta oraz pozycja profilu konta.

Moduły umieszczania zawartości pobierają dane z obsługiwanych przez nie modułów podrzędnych. Z tego względu moduły umieszczania zawartości mogą być używane na różne sposoby, w zależności od dodawanych do niej modułów.

Moduły elementów umieszczania treści używają zarówno obrazów, jak i tekstu do prezentacji promocji, zasad i funkcji produktu. Na przykład na stronie głównej można użyć modułu elementów umieszczania zawartości, aby wyświetlić zasady sklepu lub informacje o wysyłce. Moduły umieszczania zawartości są sterowane danymi z systemu zarządzania zawartością (CMS) i mogą być umieszczane na dowolnej stronie. Można je jednak używać tylko wewnątrz modułu umieszczania zawartości.

## <a name="examples-of-content-placement-modules-in-e-commerce"></a>Przykłady modułów umieszczania zawartości w e-Commerce

* Moduły umieszczania zawartości, które zawierają moduły elementów do umieszczania zawartości, mogą być używane na stronach głównych lub marketingowych w celu zaprezentowania funkcji produktu, promocji, zasad sklepu, informacji o wysyłce oraz innych informacji za pośrednictwem obu obrazów i tekstu.
* Moduły umieszczania zawartości, które zawierają moduły elementów do umieszczania zawartości, mogą być używane na stronach szczegółów produktu w celu zaprezentowania funkcji produktu.
* Na stronach zarządzania kontami można używać modułów umieszczania zawartości zawierających elementy powitalne konta lub moduły towarów z zamówieniami konta.

## <a name="content-placement-module-properties"></a>Właściwości modułu rozmieszczania treści

| Nazwa właściwości | Wartość | Opis |
|---------------|-------|-------------|
| Szerokość         | **Dopasuj do kontenera** lub **ekran wypełnienia** | Jeśli wartość jest ustawiona na **Dopasuj do kontenera**, elementy w module rozmieszczania treści są ograniczone do szerokości modułu rozmieszczania treści. Jeśli wartość jest ustawiona na **wypełnienie ekranu**, elementy nie są ograniczone do szerokości modułu rozmieszczania treści, ale mogą przechodzić do trybu pełnoekranowego. |

## <a name="content-placement-item-module-properties"></a>Właściwości modułu elementu rozmieszczania treści

| Nazwa właściwości | Wartość | Opis |
|---------------|-------|-------------|
| Nagłówek       | Tekst nagłówka i znaczniki nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Każdy moduł elementu rozmieszczenia zawartości może mieć nagłówek. Właściwość **nagłówek** obsługuje znaczniki nagłówków. Domyślnie jest używany znacznik nagłówka **H2**, ale znacznik nagłówka jest używany, ale tag nagłówka można zmienić, aby spełnić wymagania dotyczące dostępności. |
| Akapit     | Tekst akapitu | Moduły elementu rozmieszczania zawartości obsługują tekst akapitu w formacie RTF. Obsługiwane są pewne podstawowe funkcje tekstu sformatowanego, takie jak pogrubiony, podkreślony, kursywa i hiperłącza. Niektóre z tych możliwości mogą być zastąpione przez motyw strony stosowany do modułu. |
| Wizerunek         | Plik obrazu | Obraz może być skojarzony z tekstem. |
| Link          | Połącz adres URL i tekst łącza | Do tekstu można dodać łącze umożliwiające przekierowanie użytkowników do konkretnej strony. |
| Rozmiar kafelka     | Liczba z zakresu od **1** do **12** | Dla każdego elementu umieszczania zawartości Właściwość określa liczbę gniazd, które powinny wypełnić element w module umieszczania zawartości. Maksymalny rozmiar modułu umieszczania zawartości wynosi 12 gniazd. Jeśli całkowity rozmiar segmentu dla pierwszych *n* elementów w module umieszczania zawartości przekracza 12 gniazd, towary są przepakowane do następnego wiersza. |

## <a name="add-a-content-placement-module-that-contains-a-content-placement-item-module-to-a-page"></a>Dodaj moduł umieszczania zawartości zawierający moduł elementu umieszczania zawartości do strony

Aby dodać moduł umieszczania zawartości zawierający moduł elementu umieszczania zawartości do nowej strony i określić wymagane właściwości, wykonaj następujące kroki.

1. Utwórz szablon o nazwie nazwa **szablon rozmieszczania zawartości**.
1. W **Głównym** gnieździe na stronie domyślnej dodaj moduł rozmieszczania zawartości.
1. W module umieszczania treści dodaj moduł elementu umieszczania treści.
1. Zaewidencjonuj szablon i opublikuj go.
1. Za pomocą utworzonego właśnie szblonu rozmieszcznia zawartości utwórz stronę o nazwie **strona rozmieszcznia zawartości**.
1. W **Głównym** gnieździe na nowej stronie dodaj moduł rozmieszczania zawartości.
1. W module umieszczania treści dodaj moduł elementu umieszczania treści.
1. W okienku właściwości modułu elementu rozmieszczenia zawartości wybierz obraz, dodaj nagłówek, dodaj akapit, dodaj łącze, określ adres URL łącza i określ rozmiar kafelka na **6.**
1. Powtórz kroki 7 i 8, aby dodać kolejny moduł elementu rozmieszczenia zawartości o takim samym rozmiarze kafelka.
1. Zapisz i zobacz podgląd strony. Powinny być widoczne dwa elementy umieszczania zawartości widoczne obok siebie. Można dostosować Właściwość **rozmiaru kafelka** każdego modułu elementu rozmieszczenia zawartości lub dodać więcej modułów, aby uzyskać żądany układ.
1. Zaewidencjonuj stronę i opublikuj ją.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł alertów](add-alert.md)

[Moduł karuzeli](add-carousel.md)

[Moduł zaawansowanego bloku zawartości](add-content-rich-block.md)

[Moduł funkcji](add-feature-module.md)

[Moduł bohatera](add-hero-module.md)

[Moduł odtwarzacza wideo](add-video-player.md)
