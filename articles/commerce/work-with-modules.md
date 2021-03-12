---
title: Praca z modułami
description: W tym temacie opisano, jak i kiedy używać modułów w Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 89d95814e892e3afcb6514ab0d0219f7b08b9c63
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000466"
---
# <a name="work-with-modules"></a>Praca z modułami

[!include [banner](includes/banner.md)]

W tym temacie opisano, jak i kiedy używać modułów w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduły są logicznymi blokami konstrukcyjnymi, które tworzą strukturę strony i mają różne cele i zakresy. Niektóre moduły są kontenerami wysokiego poziomu, a jedynym celem jest przechowywanie i organizowanie innych modułów (modułów podrzędnych). Inne moduły, takie jak prosty moduł rozmieszczenia obrazów, mają ściśle określony cel. Inne moduły, takie jak moduł karuzeli, znajdują się gdzieś między tymi dwiema kategoriami.

Domyślnie witryna Dynamics 365 Commerce zawiera bibliotekę modułów, która umożliwia osiągnięcie większości podstawowych scenariuszy e-Commerce. Korzystając z tych modułów, można utworzyć kompleksową witrynę e-Commerce. Jednak można również dostosować te moduły lub utworzyć nowe niestandardowe moduły dla konkretnych potrzeb. Jeśli użytkownik chce zbudować moduły niestandardowe, dostępny jest zestaw projektów Software Development Kit (SDK), który ułatwia tworzenie niestandardowych bibliotek modułów.

## <a name="container-modules-and-slots"></a>Moduły i gniazda kontenera

Jak wspomniano wcześniej, niektóre moduły są przeznaczone do przechowywania modułów podrzędnych. Moduły te są nazywane *kontenerami* i umożliwiają tworzenie hierarchii zagnieżdżonych modułów. Moduły kontenera zawierają *gniazda*. Gniazda służą do obsługi układu i celu modułów podrzędnych w kontenerze. Przykładem jest podstawowy moduł kontenera strony (moduł najwyższego poziomu dla dowolnej strony), który definiuje kilka ważnych gniazd:

- Gniazdo nagłówka
- Miejsce na nagłówek podrzędny
- Miejsce główne
- Gniazdo stopki
- Miejsce na stopkę podrzędną

Programista modułu definiuje te gniazda i określa, które moduły podrzędne i ile modułów podrzędnych może być bezpośrednio w nim umieszczonych. Na przykład gniazdo nagłówka może obsługiwać tylko jeden **moduł nagłówka**, podczas gdy miejsce w treści może obsługiwać nieograniczoną liczbę modułów dowolnego typu (z wyjątkiem innych modułów kontenerów stron).

W narzędziach autorskich autorzy stron nie muszą znać z góry, które moduły mogą zostać umieszczone w poszczególnych gniazdach. Gdy autorzy stron wybierają gniazdo, a następnie próbują wybrać moduł, który ma zostać dodany, zobaczą filtrowany widok typów modułów obsługiwanych dla tego gniazda.

## <a name="content-modules"></a>Moduły zawartości

Moduły zawartości zawierają zawartość i elementy multimedialne, takie jak tekst (na przykład nagłówki, akapity, łącza) lub odwołania do składników aktywów (np. obrazy, pliki wideo i pliki PDF). Typowe typy modułów treści obejmują bloki treści, bloki tekstowe i moduły banerów promocyjnych. Moduły tych trzech typów mogą zawierać tekst lub nośniki i nie wymagają żadnych modułów podrzędnych, aby coś nie było widoczne na stronie.

Większość typowych działań na stronie codzienne i tworzenie zawartości obejmuje moduły zawartości, głównie dlatego, że moduły te definiują rzeczywistą zawartość renderowaną w ich nadrzędnych modułach kontenera. Dostępnych jest wiele modułów zawartości, a zazwyczaj te moduły są zwykle ostatnimi fragmentami, które zostaną dodane do hierarchii zagnieżdżonych modułów strony.

Na poniższej ilustracji pokazano, jak moduły są zagnieżdżone w gniazdach nadrzędnego modułu kontenera.

![Moduły zagnieżdżone](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a>Dodaj lub usuń moduły

W poniższych procedurach opisano sposób dodawania i usuwania modułów.

### <a name="add-a-module"></a>Dodaj moduł

Aby dodać moduł do boksu lub kontenera na stronie, wykonaj następujące kroki.

1. W panelu konturu po lewej stronie lub bezpośrednio w głównym obszarze roboczym wybierz kontener lub boks, do którego można dodać moduł podrzędny.

    > [!NOTE]
    > Projektant modułu definiuje listę typów modułów, które można dodać do określonego gniazda modułu. Autorzy szablonów mogą następnie doprecyzować dozwolone opcje modułu, aby zagwarantować spójną optymalizację pod kątem wyszukiwarek (SEO) i wydajność tworzenia dla wszystkich stron utworzonych na podstawie określonego szablonu. Po dodaniu modułu do miejsca, okno dialogowe **Dodaj moduł** jest automatycznie filtrowane, więc pokazuje tylko te moduły, które są obsługiwane w wybranym kontenerze lub gnieździe. Ta lista dozwolonych modułów jest określana przez szablon strony lub definicję modułu kontenera.

1. Jeśli korzystasz z okienka konturu, wybierz wielokropek (**...**) obok nazwy modułu, a następnie wybierz pozycję **Dodaj moduł**. W przypadku używania kontrolek bezpośrednio na obszarze roboczym wybierz symbol plus (**+**) w pustym gnieździe lub obok aktualnie wybranego modułu, a następnie wybierz pozycję **Dodaj moduł**.

    > [!NOTE]
    > Jeśli kontener lub gniazdo nie obsługuje nowych modułów podrzędnych, opcja **Dodaj moduł** jest niedostępna.

1. W oknie dialogowym **Dodaj moduł** wybierz moduł, który chcesz dodać do swojej strony.

    > [!TIP]
    > **Blok zawartości** jest dobrym typem modułu dla początkujących do pracy z systemem.

1. Wybierz przycisk **OK**, aby dodać wybrany moduł do wybranego kontenera lub gniazda na stronie.

### <a name="remove-a-module"></a>Usuń moduł

Aby usunąć moduł z gniazda lub kontenera na stronie, wykonaj następujące kroki.

1. W panelu konturu po lewej stronie wybierz wielokropek (**...**) obok nazwy modułu do usunięcia, a następnie wybierz symbol kosza. Alternatywnie, w głównym obszarze roboczym możesz wybrać symbol kosza na pasku narzędzi wybranego modułu.
1. Po wyświetleniu monitu o potwierdzenie zamiaru usunięcia modułu wybierz przycisk **OK**.

## <a name="move-a-module-to-a-new-position"></a>Przenieś moduł w nowe miejsce

Aby przenieść moduł w nowe miejsce na stronie, należy skorzystać z dowolnej z poniższych metod.

### <a name="move-a-module-using-the-outline-pane"></a>Przenoszenie modułu za pomocą okienka konturu

Aby przenieść moduł za pomocą okienka konturu, wykonaj następujące kroki.

1. Wybierz i przytrzymaj moduł, który chcesz przenieść w okienku konspektu, a następnie przeciągnij moduł do nowego położenia w konturu. Niebieska linia w konspekcie i na kanwie wskazuje miejsce, w którym można umieścić moduł.
1. Zwolnij moduł, aby przenieść go do nowego miejsca.

### <a name="move-a-module-directly-within-the-canvas"></a>Przenoszenie modułu bezpośrednio w obszarze roboczym

Aby przenieść moduł bezpośrednio w obszarze roboczym, wykonaj następujące kroki.

1. Wybierz moduł, który chcesz przenieść w kanwie. 
1. Wybierz symbol strzałki skierowanej w górę lub w dół na pasku narzędzi modułu, a następnie przeciągnij strzałkę w nowe miejsce na stronie. Niebieska linia na płótnie i kontur wskazuje, gdzie można umieścić moduł. Jeśli modułu nie można przesunąć w górę lub w dół, ten symbol strzałki będzie wyszarzony. 
1. Zwolnij moduł, aby przenieść go do nowego miejsca.

### <a name="move-a-module-using-the-ellipsis-menu"></a>Przenoszenie modułu za pomocą menu elipsy

Aby przenieść moduł za pomocą manu elipsy, wykonaj następujące kroki.

1. Umożliwia wybranie modułu w konturze lub obszarze roboczym.
1. Wybierz wielokropek (**...**) obok nazwy modułu w okienku konturu lub na pasku narzędzi modułu na kanwie.
1. Jeśli moduł może być przesunięty w górę lub w dół w kontenerze lub gnieździe, zostaną wyświetlone opcje **Przenoszenia w górę** lub **W dół**. Wybierz odpowiednią opcję przenoszenia, aby przenieść moduł w górę lub w dół w stosunku do jego elementów równorzędnych.

## <a name="configure-modules"></a>Konfiguracja modułów

Poniższe procedury opisują sposób konfigurowania modułów zawartości i kontenera.

### <a name="configure-a-content-module"></a>Konfiguruj moduł zawartości

Aby skonfigurować moduł zawartości na stronie, wykonaj następujące kroki.

1. W okienku konspektu z lewej strony rozwiń drzewo i wybierz jakikolwiek moduł zawartości (np. **Blok zawartości**). Alternatywnie możesz wybrać moduł w głównym obszarze roboczym.
1. W okienku właściwości modułu po prawej stronie wprowadź właściwości dla dowolnych kontrolek modułu.
1. Na pasku poleceń wybierz **Zapisz**. Spowoduje to również odświeżenie kanwy podglądu.

### <a name="edit-module-text-properties"></a>Edytuj właściwości tekstu modułu

Właściwości tekstu modułu, które nie są tylko do odczytu, można edytować bezpośrednio na kanwie.

Aby edytować właściwości tekstu modułu, wykonaj następujące kroki.

1. Wybierz kontrolkę tekstu w obszarze roboczym, a następnie umieść kursor w miejscu, w którym chcesz edytować tekst.
1. Wpisz treść tekstu.
1. Wybierz gdziekolwiek poza zawartością tekstową, aby kontynuować edytowanie innej zawartości.

### <a name="inline-image-selection"></a>Wybór obrazu wbudowanego

Obrazy modułów, które nie są tylko do odczytu, można zmienić bezpośrednio z obszaru roboczego.

Aby wybrać nowy obraz dla modułu zawartości, wykonaj następujące kroki.

1. Kliknij dwukrotnie obraz w obszarze roboczym. Spowoduje to wyświetlenie okna selektor nośników.
1. Znajdź i wybierz nowy obraz, którego chcesz użyć, a następnie kliknij przycisk **OK**. Nowy obraz jest teraz odwzorowany na kanwie.

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

