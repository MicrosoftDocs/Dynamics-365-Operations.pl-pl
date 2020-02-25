---
title: Praca z modułami
description: W tym temacie opisano, jak i kiedy używać modułów w Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/31/2020
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
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 769d6754fa944830b989d657e0dad9cc42212932
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025886"
---
# <a name="work-with-modules"></a>Praca z modułami

W tym temacie opisano, jak i kiedy używać modułów w Microsoft Dynamics 365 Commerce.


[!include [banner](includes/banner.md)]

## <a name="overview"></a>Omówienie

Moduły są logicznymi blokami konstrukcyjnymi, które tworzą strukturę strony i mają różne cele i zakresy. Niektóre moduły są kontenerami wysokiego poziomu, a jedynym celem jest przechowywanie i organizowanie innych modułów (modułów podrzędnych). Inne moduły, takie jak prosty moduł rozmieszczenia obrazów, mają ściśle określony cel. Inne moduły, takie jak moduł karuzeli, znajdują się gdzieś między tymi dwiema kategoriami.

Domyślnie witryna Dynamics 365 Commerce zawiera bibliotekę w module zestaw początkowy, która umożliwia osiągnięcie większości podstawowych scenariuszy e-Commerce. Korzystając z tych modułów, można utworzyć kompleksową witrynę e-Commerce. Jednak można również dostosować te moduły lub utworzyć nowe niestandardowe moduły dla konkretnych potrzeb. Jeśli użytkownik chce zbudować moduły niestandardowe, dostępny jest zestaw projektów Software Development Kit (SDK), który ułatwia tworzenie niestandardowych bibliotek modułów.

## <a name="container-modules-and-slots"></a>Moduły i gniazda kontenera

Jak wspomniano wcześniej, niektóre moduły są przeznaczone do przechowywania modułów podrzędnych. Moduły te są nazywane *kontenerami* i umożliwiają tworzenie hierarchii zagnieżdżonych modułów. Moduły kontenera zawierają *gniazda*. Gniazda służą do obsługi układu i celu modułów podrzędnych w kontenerze. Przykładem jest podstawowy moduł kontenera strony (moduł najwyższego poziomu dla dowolnej strony), który definiuje kilka ważnych gniazd:

- Gniazdo nagłówka
- Gniazdo treści
- Gniazdo stopki

Programista modułu definiuje te gniazda i określa, które moduły podrzędne i ile modułów podrzędnych może być bezpośrednio w nim umieszczonych. Na przykład gniazdo nagłówka może obsługiwać tylko jeden **moduł nagłówka**, podczas gdy miejsce w treści może obsługiwać nieograniczoną liczbę modułów dowolnego typu (z wyjątkiem innych modułów kontenerów stron).

W narzędziach autorskich autorzy stron nie muszą znać z góry, które moduły mogą zostać umieszczone w poszczególnych gniazdach. Gdy autorzy stron wybierają gniazdo, a następnie próbują wybrać moduł, który ma zostać dodany, zobaczą filtrowany widok typów modułów obsługiwanych dla tego gniazda.

## <a name="content-modules"></a>Moduły zawartości

Moduły zawartości zawierają zawartość i elementy multimedialne, takie jak tekst (na przykład nagłówki, akapity, łącza) lub odwołania do składników aktywów (np. obrazy, pliki wideo i pliki PDF). Przykłady typowych typów modułów zawartości **bohatera**, **funkcji** i **baner**. Moduły tych trzech typów mogą zawierać tekst lub nośniki i nie wymagają żadnych modułów podrzędnych, aby coś nie było widoczne na stronie.

Większość typowych działań na stronie codzienne i tworzenie zawartości obejmuje moduły zawartości, głównie dlatego, że moduły te definiują rzeczywistą zawartość renderowaną w ich nadrzędnych modułach kontenera. Dostępnych jest wiele modułów zawartości, a zazwyczaj te moduły są zwykle ostatnimi fragmentami, które zostaną dodane do hierarchii zagnieżdżonych modułów strony.

Na poniższej ilustracji pokazano, jak moduły są zagnieżdżone w gniazdach nadrzędnego modułu kontenera.

![Moduły zagnieżdżone](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a>Dodaj lub usuń moduły

W poniższych procedurach opisano sposób dodawania i usuwania modułów.

### <a name="add-a-module"></a>Dodaj moduł

Aby dodać moduł do boksu lub kontenera na stronie, wykonaj następujące kroki.

1. W okienku konspektu z lewej strony wybierz kontener lub gniazdo, do którego można dodać moduł podrzędny.

    > [!NOTE]
    > Projektant modułu definiuje listę typów modułów, które można dodać do określonego gniazda modułu. Autorzy szablonów mogą następnie dostosować dozwolone opcje modułu, aby zapewnić spójną optymalizację aparatu wyszukiwania (SEO) i wydajność tworzenia dla wszystkich stron stron, które zostały utworzone na podstawie określonego szablonu.

1. Wybierz przycisk wielokropka (**...**) dla modułu, a następnie wybierz opcję **Dodaj moduł**. Zostanie wyświetlone okno dialogowe **Dodaj moduł**. To okno dialogowe jest automatycznie filtrowane, więc pokazuje tylko te moduły, które są obsługiwane w wybranym kontenerze lub gnieździe. Lista modułów jest określana na podstawie szablonu strony lub definicji modułu kontenerów.

    > [!NOTE]
    > Jeśli kontener lub gniazdo nie obsługuje nowych modułów podrzędnych, opcja **Dodaj moduł** jest niedostępna.

1. W oknie dialogowym wyszukaj i wybierz moduł, który chcesz dodać do swojej strony.

    > [!TIP]
    > **Funkcje** i **bohater** są dobrymi typami modułów dla początkujących do pracy z systemem.

1. Wybierz przycisk **OK**, aby dodać wybrany moduł do wybranego kontenera lub gniazda na stronie.

### <a name="remove-a-module"></a>Usuń moduł

Aby usunąć moduł z gniazda lub kontenera na stronie, wykonaj następujące kroki.

1. W okienku konspektu z lewej strony wybierz przycisk wielokropka obok nazwy modułu do usunięcia, a następnie wybierz ikonkę kosza na śmieci.
1. Po wyświetleniu monitu o potwierdzenie zamiaru usunięcia modułu wybierz przycisk **OK**.

## <a name="configure-modules"></a>Konfiguracja modułów

Poniższe procedury opisują sposób konfigurowania modułów zawartości i kontenera.

### <a name="configure-a-content-module"></a>Konfiguruj moduł zawartości

Aby skonfigurować moduł zawartości na stronie, wykonaj następujące kroki.

1. W okienku konspektu z lewej strony rozwiń drzewo i wybierz jakikolwiek moduł zawartości (np. **funkcji**, **bohater** lub **baner**).
1. W okienku właściwości po prawej stronie Znajdź elementy sterujące treścią i ustawieniami modułu.
1. Wprowadź właściwości dla żądanych formantów modułu.
1. Na pasku poleceń wybierz pozycję **Zapisz**. Spowoduje to również odświeżenie kanwy podglądu.

### <a name="configure-a-container-module"></a>Konfigurowanie modułu kontenera

Aby skonfigurować moduł kontenera na stronie, wykonaj następujące kroki.

1. Wybierz moduł kontenera na stronie (np. karuzela lub moduł kontener płynny).
1. W okienku właściwości po prawej stronie rozwiń formanty zagnieżdżone, zaznaczając nagłówki i ustawiając wymagane wartości kontrolne.
1. W okienku konspektu po lewej wybierz przycisk wielokropka obok nazwy kontenera lub dowolnych szczelin w kontenerze, a następnie wybierz **Dodaj moduł**. Następnie Dodaj moduły podrzędne do wybranego kontenera. Aby uzyskać więcej informacji, zobacz sekcję [Praca z modułami](#add-a-module) we wcześniejszej części tego tematu.
1. Jeśli w kontenerze nadrzędnym istnieje wiele modułów podrzędnych jako elementy równorzędne, można zmienić kolejność wyświetlania w kontenerze nadrzędnym. Wybierz przycisk wielokropek dla modułu, a następnie użyj przycisków strzałki w górę i strzałki w dół.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie szablonów i układów](templates-layouts-overview.md)

[Praca z szablonami](work-with-templates.md)

[Praca z układami predefiniowanymi](work-with-layouts.md)

[Praca z fragmentami](work-with-fragments.md)

[Dodawanie modułu kontenera do strony](add-container-module.md)

[Praca z grupami publikowania](publish-groups.md)

