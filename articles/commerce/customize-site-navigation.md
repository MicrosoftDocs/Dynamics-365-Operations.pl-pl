---
title: Dostosowywanie nawigacji w witrynie
description: W tym temacie opisano sposób tworzenia dostosowanej hierarchii nawigacji w trybie online do organizowania produktów w celu ich przejrzenia w witrynie Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5bc50243ac3845adc60bfc173fc532fb28f3cdf6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799356"
---
# <a name="customize-site-navigation"></a>Dostosowywanie nawigacji w witrynie

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób tworzenia dostosowanej hierarchii nawigacji w trybie online do organizowania produktów w celu ich przejrzenia w witrynie Microsoft Dynamics 365 Commerce.

Sklepy online zazwyczaj umożliwiają klientom odkrywanie produktów i przeglądanie ich w różnych kategoriach produktów. Ta możliwość jest zazwyczaj udostępniana przez karty u góry strony lub przez pasek nawigacyjny po lewej stronie. W Dynamics 365 Commerce można tworzyć strukturę hierarchii nawigacji między kategoriami i produkty uwzględnione w różnych kategoriach oraz zarządzać tymi strukturami.

## <a name="create-a-channel-navigation-hierarchy"></a>Tworzenie hierarchii nawigacji kanału

Aby utworzyć hierarchię nawigacji kanału, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Retail i Commerce \> Produkty i kategorie \> Zarządzanie kategoriami i produktami**.
1. Wybierz **Hierarchie kategorii**, a następnie wybierz opcję **Nowy**.
1. Nazwij hierarchię.

    > [!NOTE]
    > Tworzona Kategoria najwyższego poziomu jest węzłem głównej kategorii. Nie będzie on pokazywany w witrynie. Aby utworzyć hierarchię kategorii, w której w witrynie jest wyświetlany jeden węzeł najwyższego poziomu, należy utworzyć nazwę kategorii i nazwać ją jako podrzędną dla kategorii głównej.

1. Wybierz opcję **Nowy węzeł kategorii** i nadaj nazwę kategorii.
1. W razie konieczności kontynuuj tworzenie elementów równorzędnych i podrzędnych.

Teraz można przypisywać produkty do każdej kategorii utworzonej w ramach kategorii najwyższego poziomu.

## <a name="customize-the-order-of-categories"></a>Dostosowywanie kolejności kategorii

Kategorie definiowane przez użytkownika są domyślnie wyświetlane w kolejności alfabetycznej w witrynie. Można jednak również dostosować kolejność wyświetlania kategorii.

## <a name="assign-a-category-hierarchy-type"></a>Przypisywanie typu hierarchii kategorii

1. Wybierz kolejno opcje **Retail i Commerce \> Produkty i kategorie \> Zarządzanie kategoriami i produktami**.
1. Wybierz **Hierarchie kategorii**.
1. Następnie w okienku akcji na karcie **Hierarchie kategorii** w grupie **Konfiguracja** wybierz opcję **Powiązanie typu hierarchii**.
1. Wybierz pozycję **Nowy**.
1. W polu **Typ hierarchii kategorii** wybierz opcję **Hierarchia nawigacji kanału**.
1. W polu **hierarchia kategorii** wybierz utworzoną wcześniej hierarchię nawigacji kanałów.

## <a name="publish-new-or-updated-navigation-hierarchies"></a>Opublikuj nowe lub zaktualizowane hierarchie nawigacji

Aby uczynić hierarchię nawigacji dostępną w Twoim sklepem online, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Kategorie kanału sprzedaży i atrybuty produktów**.
1. W drzewie po lewej stronie wybierz sklep internetowy.
1. Wybierz **Publikowanie aktualizacji kanału**.
1. Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.
1. Na liście znajdź i zaznacz **Zadanie 1040**.
1. Wybierz opcję **Uruchom teraz**.
1. Powtórz kroki 5 i 6 dla zadań 1070 i 1150.

## <a name="show-categories-on-your-site"></a>Wyświetlanie kategorii w witrynie

Aby wyświetlić hierarchię kategorii w witrynie sklep online, należy dodać moduł menu nawigacji w odpowiedniej lokalizacji w szablonie lub fragmencie. W module menu nawigacji zostanie wyświetlona hierarchia nawigacji, pod warunkiem, że hierarchia nawigacji zostanie opublikowana w kanale, z którym jest związana ta witryna.

> [!NOTE]
> Moduł menu nawigacji, który jest dołączony do biblioteki modułów, umożliwia użytkownikom poruszanie się wyłącznie do kategorii, które nie mają podkategorii. Jeśli odbiorcy powinni mieć możliwość nawigowania do kategorii, które mają podkategorie, należy dostosować Moduł menu nawigacji.

## <a name="add-custom-navigation-options"></a>Dodawanie niestandardowych opcji nawigacji

W menu nawigacji można dodać opcje nawigacji, które nie należą do hierarchii kategorii produktów. Na przykład na końcu listy kategorii produktów można dodać element **Skontaktuj się z nami** wskazujący na stronę kontaktową utworzoną dla witryny.

Aby dodać niestandardowe opcje nawigacji do menu nawigacji, należy wykonać następujące kroki.

1. W szablonie lub fragmencie, który chcesz dostosować, wybierz moduł menu nawigacji.
1. W okienku właściwości na karcie **Dane** wybierz **Dodaj pozycję**, aby utworzyć nowy element nawigacji w systemie Content Management System (CMS).
1. Wprowadź tekst łącza i adres URL
1. Powtórz kroki 2 i 3, aby dodać kolejne opcje nawigacji niestandardowej.
1. Po zakończeniu wybierz opcję **Zapisz**, aby zapisać szablon lub fragment, a następnie wybierz przycisk **Zakończ edycję**, aby go zaewidencjonować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie szablonów i układów](templates-layouts-overview.md)

[Praca z szablonami](work-with-templates.md)

[Praca z układami predefiniowanymi](work-with-layouts.md)

[Praca z fragmentami](work-with-fragments.md)

[Praca z modułami](work-with-modules.md)

[Tworzenie adresu URL strony](create-page-url.md)

[Praca z grupami publikowania](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
