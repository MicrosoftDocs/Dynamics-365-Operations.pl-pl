---
title: Moduł nagłówka
description: W tym temacie opisano moduły nagłówka i sposób ich tworzenia w Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: cc98419077f6f563ea2265d4e68ba809971cfbd6
ms.sourcegitcommit: ff93b8f6a11993f2cd00be2da7aa77ef0d950ab8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885485"
---
# <a name="header-module"></a>Moduł nagłówka

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano moduły nagłówka i sposób ich tworzenia w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł nagłówka jest specjalnym kontenerem używanym do obsługiwania wszystkich modułów, które będą wyświetlane w nagłówku strony. Może to być na przykład logo witryny, łącza do hierarchii nawigacji, łącza do innych stron w witrynie oraz na pasku wyszukiwania.

Moduł nagłówka jest automatycznie optymalizowany dla urządzenia, na którym jest oglądana witryna (czyli urządzenie stacjonarne lub urządzenie przenośne). Na przykład na urządzeniu przenośnym pasek nawigacji jest zwinięty do przycisku **Menu** (który jest czasami nazywany *menu hamburgerowym*).

## <a name="properties-of-a-header"></a>Właściwości nagłówka

Podobnie jak większość ogólnych kontenerów, moduł nagłówka obsługuje właściwości **nagłówka** i **szerokości**.

Moduł nagłówka ma wiele gniazd. Na przykład istnieją gniazda dla komunikatu informacyjnego, menu nawigacji, logo, paska wyszukiwania, ikony koszyka, ikony listy życzeń i informacji o koncie. Każde gniazdo obsługuje określony zbiór modułów.

## <a name="modules-that-are-available-in-a-header-module"></a>Moduły dostępne w module nagłówka

W module nagłówka mogą być używane następujące moduły:

- **Menu nawigacji** — menu nawigacji reprezentuje hierarchię nawigacji kanału i inne statyczne łącza nawigacji. Hierarchię nawigacji kanału można skonfigurować w Dynamics 365 Retail. Skonfigurowane elementy zostaną wyświetlone jako nawigacja w nagłówkach. Ponadto można konfigurować statyczne łącza nawigacji oraz łącza względne do innych stron w witrynie e-Commerce. Nagłówek może być wyrównany do lewej, do prawej lub do środka.
- **Ikona koszyka** — ikona koszyka jest specjalną ikoną, która reprezentuje koszyk. Jest ona wyświetlana w nagłówku i wskazuje liczbę pozycji w koszyku. Łącze do strony koszyka powinno towarzyszyć ikonie koszyka, dzięki czemu odbiorcy mogą zostać przekierowani do strony koszyka podczas interakcji z tą ikoną.
- **Ikona listy życzeń** — ikona listy życzeń jest wyświetlana w nagłówku i wskazuje liczbę towarów, które zostały dodane do listy życzeń odbiorcy. Łącze do strony życzeń powinno towarzyszyć tej ikonie, dzięki czemu odbiorcy mogą zostać przekierowani do strony życzeń podczas interakcji z tą ikoną.
- **Moduł rejestracji** — w nagłówku jest wyświetlany moduł rejestrowania. Klienci mogą zalogować się do konta lub zarejestrować się w celu uwzględnienia konta. Jeśli odbiorca jest już zalogowany, można tak skonfigurować moduł, aby pokazywał łącza do strony konta, strony historii zamówień lub innej strony.
- **Moduł logo** — ten moduł pokazuje logo reprezentujące sprzedawcę i markę. Jest to obraz, który ma łącze. Łącze jest zazwyczaj skonfigurowane w taki sposób, aby zostało przekierowaniem na stronę główną, dlatego klienci mogą szybko powrócić do strony głównej z dowolnej strony w witrynie.
- **Alert** — w nagłówku jest wyświetlany alert i jest on używany do wyświetlania komunikatu w wierszu, który ma zastosowanie do wszystkich stron w witrynie. Na przykład alert może zawierać komunikat, na przykład „sprzedaż roczna kończy się za 2 dni”.
- **Pasek wyszukiwania** — pasek wyszukiwania umożliwia użytkownikom wprowadzanie kryteriów wyszukiwania, co pozwala na wyszukiwanie produktów. Moduł musi być skonfigurowany z adresem URL strony wyników wyszukiwania. Można skonfigurować parametr ciągu kwerendy (wartość domyślna to **„q”**). Na pasku wyszukiwania jest zaproponowane gniazdo automatycznego sugerowania, w którym należy dodać moduł automatycznego sugerowania.
- **Automatyczne sugerowanie** — moduł automatycznego sugerowania pokazuje automatycznie sugerowane wyniki. Wyniki mogą być słowami kluczowymi, produktami lub kategoriami, w których wyszukiwany jest termin wyszukiwania.

## <a name="create-a-header-module"></a>Tworzenie modułu nagłówka

Aby utworzyć moduł nagłówka, należy wykonać następujące czynności.

1. Utwórz fragment strony zawierający moduł nagłówka.
1. Dodaj moduły do gniazd w module nagłówka.
1. Umożliwia zaktualizowanie ustawień dla każdego modułu.
1. Zapisz jako fragment strony. 
1. Zaewidencjonuj stronę i opublikuj ją.

Aby zagwarantować, że nagłówek ma się pojawiać na każdej stronie, należy wykonać poniższe kroki na każdym szablonie strony utworzonym dla witryny.

1. Na stronie domyślne dodaj fragment strony zawierający moduł nagłówka do nagłówka w głównym gnieździe.
1. Zapisz szablon. 
1. Zaewidencjonuj szablon i opublikuj go.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)
